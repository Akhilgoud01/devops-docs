# 🔎 Text Processing: grep, sed, awk

> **In one line:** `grep` finds lines, `sed` edits lines, and `awk` works with columns, and together they turn huge log files into answers in seconds.

## 🧠 Simple explanation

Imagine a giant book with a million lines. `grep` is a **highlighter** that finds lines with a word. `sed` is a **find-and-replace pen**. `awk` is a **spreadsheet tool** that splits each line into columns so you can add them up or pick some.

Linux commands pass text to each other with pipes, like a factory conveyor belt.

```mermaid
flowchart LR
    LOG["access.log"] --> G["grep: keep matching lines"]
    G --> A["awk: pick the column"]
    A --> S["sort"]
    S --> U["uniq -c: count"]
    U --> OUT["Top results"]
```

## 🔑 Key concepts

- **Stream:** text flowing through a command. **stdin** in, **stdout** out, **stderr** errors.
- **Regular expression (regex):** a pattern language for matching text (`^start`, `end$`, `.` any char, `*` repeat, `[0-9]` a digit).
- **Field:** a column in a line. `awk` calls them `$1`, `$2`, ... and `$0` is the whole line.
- **Delimiter:** the character separating fields (space, comma, colon).

## 🛠️ Hands-on

Sample file `access.log`:

```text
10.0.0.5 - - [31/Oct/2026:10:00:01] "GET /index.html" 200 512
10.0.0.7 - - [31/Oct/2026:10:00:02] "GET /login" 500 128
10.0.0.5 - - [31/Oct/2026:10:00:03] "POST /api/pay" 502 64
10.0.0.9 - - [31/Oct/2026:10:00:04] "GET /index.html" 200 512
```

### grep

```bash
grep "500" access.log              # lines containing 500
grep -i "error" app.log            # ignore case
grep -n "login" access.log         # show line numbers
grep -v "200" access.log           # invert: lines NOT matching
grep -c "GET" access.log           # count matching lines
grep -r "password" /etc/myapp/     # search a whole folder recursively
grep -E "50[0-9]" access.log       # extended regex: 500-509
grep -A2 -B2 "ERROR" app.log       # 2 lines After and Before the match
```

### sed

```bash
sed 's/http/https/' urls.txt                # replace first match on each line
sed 's/http/https/g' urls.txt               # replace all matches
sed -i 's/DEBUG/INFO/' config.ini           # edit file in place
sed -i.bak 's/DEBUG/INFO/' config.ini       # edit in place and keep a backup
sed -n '5,10p' file.txt                     # print only lines 5 to 10
sed '/^#/d' config.conf                     # delete comment lines
sed '/^$/d' file.txt                        # delete empty lines
```

### awk

```bash
awk '{print $1}' access.log                     # first column (the IP)
awk '$9 >= 500 {print $0}' access.log           # lines where column 9 is 500 or more
awk -F: '{print $1, $7}' /etc/passwd            # custom delimiter: colon
awk '{sum += $NF} END {print sum}' access.log   # add up the last column
awk '{count[$1]++} END {for (ip in count) print ip, count[ip]}' access.log
```

Note: in the sample log, the status code is the second to last field, so adjust column numbers to match your log format.

### Combine them: real DevOps questions

Top 5 IP addresses hitting the server:

```bash
awk '{print $1}' access.log | sort | uniq -c | sort -rn | head -5
```

How many 5xx errors?

```bash
grep -E '" 5[0-9]{2} ' access.log | wc -l
```

Unique error messages today:

```bash
grep "ERROR" app.log | sed 's/^[^ ]* [^ ]* //' | sort | uniq -c | sort -rn
```

Extract a value from JSON-ish text (use `jq` for real JSON):

```bash
curl -s https://api.example.com/health | jq '.status'
```

### Other helpful tools

```bash
cut -d, -f1,3 data.csv        # pick columns 1 and 3 from a CSV
sort -k2 -n data.txt          # sort by 2nd column, numerically
uniq -c                       # count repeated lines (input must be sorted)
tr 'a-z' 'A-Z' < file.txt     # change letters to uppercase
xargs                         # build commands from input
tee out.txt                   # show output AND save it
```

## ⚠️ Common mistakes

- **Using `uniq` without `sort`.** It only merges neighbors.
- **`sed -i` without a backup** on important files. Use `-i.bak` first.
- **Not quoting patterns.** The shell may expand `*` or `$`. Use single quotes.
- **Assuming column numbers** without looking at the real data.
- **Parsing JSON or YAML with grep/sed.** Use `jq` or `yq` instead.
- **Forgetting `-E`** when using `+`, `?`, or `|` in grep patterns.

## ✅ Quick recap

- `grep` finds, `sed` replaces, `awk` handles columns.
- Pipe them with `sort | uniq -c | sort -rn` to build a "top N" report.
- Single-quote your patterns and test on a copy before `sed -i`.
- Use `jq` for JSON.

⬅️ Previous: [04 - Package Management and cron](04-package-management-and-cron.md) | ➡️ Next: [06 - SSH and Troubleshooting Performance](06-ssh-and-troubleshooting-performance.md)
