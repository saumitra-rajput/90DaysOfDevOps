# Day 21 – Shell Scripting Cheat Sheet: Build Your Own Reference Guide

## Task
---

## Challenge Tasks
### Task 8 
# My Cheat sheet

| Topic | Key Syntax | Example |
|-------|------------|----------|
| Shebang | `#!/bin/bash` | `#!/bin/bash` |
| Run Script | `chmod +x file.sh` | `./script.sh` |
| Variable | `VAR="value"` | `NAME="DevOps"` |
| Use Variable | `"$VAR"` | `echo "$NAME"` |
| User Input | `read var` | `read -p "Enter name: " name` |
| Argument | `$1`, `$2` | `./script.sh ram` |
| Argument Count | `$#` | `if [ $# -lt 1 ]; then` |
| All Arguments | `"$@"` | `for arg in "$@"; do` |
| Exit Code | `$?` | `echo $?` |
| If Condition | `if [ condition ]; then` | `if [ -f file ]; then` |
| String Compare | `[ "$a" = "$b" ]` | `if [ "$name" = "ram" ]; then` |
| Integer Compare | `[ "$num" -gt 5 ]` | `if [ "$num" -gt 5 ]; then` |
| File Check | `-f`, `-d`, `-e` | `if [ -d /var/log ]; then` |
| Logical AND | `&&` | `[ -f file ] && echo "Exists"` |
| Logical OR | `||` | `[ -f file ] || echo "Missing"` |
| For Loop | `for i in list; do` | `for i in 1 2 3; do` |
| C-Style Loop | `for ((i=0;i<5;i++))` | `for ((i=1;i<=5;i++)); do` |
| While Loop | `while [ condition ]; do` | `while read line; do` |
| Function | `name() { ... }` | `greet() { echo "Hi"; }` |
| Return Status | `return 0` | `return 1` |
| Grep | `grep pattern file` | `grep -i "error" log.txt` |
| Awk | `awk '{print $1}' file` | `awk -F: '{print $1}' /etc/passwd` |
| Sed | `sed 's/old/new/g' file` | `sed -i 's/foo/bar/g' config.txt` |
| Cut | `cut -d: -f1 file` | `cut -d, -f2 data.csv` |
| Sort | `sort -n` | `sort -rn file.txt` |
| Uniq | `uniq -c` | `sort file | uniq -c` |
| WC | `wc -l` | `wc -l file.txt` |
| Tail | `tail -f file` | `tail -f app.log` |
| Debug Mode | `set -x` | `set -euo pipefail` |
| Trap | `trap 'cmd' EXIT` | `trap cleanup EXIT` |



### Task 1: Basics
Document the following with short descriptions and examples:
1. Shebang (`#!/bin/bash`) — what it does and why it matters

- It tells our terminal to use specific shell
- if somebody use./ to run the script terminal will get confuse which intrepreter to use.
- but if run with bash test.sh with writing shebang it will work.

2. Running a script — `chmod +x`, `./script.sh`, `bash script.sh`

- `chmod +x ` before we can execute the script it needs to have x executeable permision
- `./script.sh` ./ we use to run scripts which has shebang #!/bin/bash
- `bash script.sh` bash is like telling terminal to use bash shell to run scripts


3. Comments — single line (`#`) and inline  

- Commeting is very important for any script to make it more readable and tell user what is does, why and how.

4. Variables — declaring, using, and quoting (`$VAR`, `"$VAR"`, `'$VAR'`)

- If you use a variable → wrap it in double quotes.

- `$VAR` : shell treat as it is. If it varibale has spacing it will be treated as two different words
example: hello world --- two words
- `"$VAR"` : In double quotes it take it as a string One single value.
- `'$VAR'`: Print exactly what’s written. echo '$VAR' output var

5. Reading user input — `read`
- read can take user's input as an arguments
- read -p "enter your name" name ----can be used to store variable

6. Command-line arguments — `
./my.sh ram sita hanuman
- `$0` script name my.sh
- `$1` first argument ram
- `$#`total number of arguments : 3
- `$@`print all arguments: ram sita hanuman
- `$?` exit status of Last Command (0 → Success Non-zero → Error)

---

### Task 2: Operators and Conditionals

Document with examples:

1. String comparisons — Used inside [ ] or [[ ]]

- `=` equal if [ "$name" = "ram" ]; then
- `!=` not equal if [ "$name" != "sita" ]; then
- `-z` check if the variable is empty if [ -z "$var" ]; then
- `-n` string is not empty if [ -n "$var" ]; then

2. Integer comparisons — Only for numbers.

- `-eq`  equal if [ "$num" -gt 5 ]; then
- `-ne` not equal
- `-lt` less than
- `-gt` greater than
- `-le` less than equal to
- `-ge` greater than equal to


3. File test operators — 
- `-f` : check the file exists ``` if [ -f "app.log" ]; then ```
- `-d` : check the directory exists ```  if [ -d "/var/log" ]; then ```
- `-e`: file or directory exists both ``` if [ -f "test.txt" ]; then ```
- `-r`: readable or not ``` if [ -r "app.log" ]; then ```
- `-w`: write permission or not ``` if [ -w "app.log" ]; then ```
- `-x`: executeable or not ``` if [ -w "app.log" ]; then ```
- `-s`: file is not empty (size > 0) ``` if [ -s "app.log" ]; then ```

4. `if`, `elif`, `else` syntax

```
num=10

if [ "$num" -gt 10 ]; then
  echo "Greater"
elif [ "$num" -eq 10 ]; then
  echo "Equal"
else
  echo "Less"
fi

```
5. Logical operators — 
- `&&`: and Both must be true
```
if [ -f "app.log" ] && [ -r "app.log" ]; then
  echo "File exists and readable"
fi
```
- `||`: or One must be true.
```
[ -f "app.log" ] || echo "File not found"

```
- `!`: not case
```
if [ ! -f "app.log" ]; then
  echo "File does not exist"
fi
```


6. Case statements — `case ... esac`
- Took assistance from GPT

- Used for multiple conditions (cleaner than many elifs).
```
read -p "Enter option: " opt

case "$opt" in
  start)
    echo "Starting service"
    ;;
  stop)
    echo "Stopping service"
    ;;
  restart)
    echo "Restarting service"
    ;;
  *)
    echo "Invalid option"
    ;;
esac

```

---

### Task 3: Loops
Document with examples:
1. `for` loop — 
- list-based : 

    - A) List-Based for Loop (for name in ram sita hanuman)
    - B) Loop using arguments (for arg in "$@")

- C-style :
    - for (( i=1; i<=5; i++ ))

2. `while` loop
- Runs while condition is true.
```
count=1

while [ "$count" -le 5 ]
do
  echo "Count: $count"
  ((count++))
done

```

3. `until` loop  (opposite of while)
- Runs until condition becomes true
```
count=1

until [ "$count" -gt 5 ]
do
  echo "Count: $count"
  ((count++))
done

```

4. Loop control —
- `break`: Exit Loop
```for i in 1 2 3 4 5
do
  if [ "$i" -eq 3 ]; then
    break
  fi
  echo "$i"
done

```

- `continue`: Skip Current Iteration
```
for i in 1 2 3 4 5
do
  if [ "$i" -eq 3 ]; then
    continue
  fi
  echo "$i"
done

```

5. Looping over files — `for file in *.log`
- This loops over all .log files in current directory.

```
for file in *.log
do
  echo "Processing $file"
done

```
6. Looping over command output — `while read line`
```

while read -r line
do
  if [[ "$line" == *ERROR* ]]; then
    echo "Error found: $line"
  fi
done < app.log

```

---

### Task 4: Functions
Document with examples:
1. Defining a function — `function_name() { ... }`
```
belo() {
  echo "Hello Saumitra!"
}

```
2. Calling a function
- inside the same scripting let say test.sh has functions you will type `belo`
- calling in other script : source /path/test.sh
3. Passing arguments to functions —
Inside functions, arguments work like script arguments.
- `$1`:
```
greet() {
  echo "Hello $1"
}

greet Saumitra
```

- `$2` inside functions
```
add() {
  echo "First: $1"
  echo "Second: $2"
}

add 10 20
```
- multi argument passing inside funcition
```
print_all() {
  echo "All args: $@"
}

print_all ram sita hanuman
```

4. Return values — 
- `return`: return sends an exit status (0–255)
    - return is NOT for returning strings.
    - It only returns numbers (exit codes).
    ```
    check_even() {
    if (( $1 % 2 == 0 )); then
        return 0
    else
        return 1
    fi
    }

    check_even 4
    echo $?
    ```
    > output :0 means success.

- `echo` : If you want to return actual data:
    ```
    get_name() {
    echo "Saumitra"
    }

    name=$(get_name)
    echo "Name is $name"
    ```
    > output : Name is Saumitra


5. Local variables — Without local, variables become global.
- `local`:
    -  Without local:
    ```
    test_func() {
    var="Hello"
    }

    test_func
    echo "$var"
    ```
    > output: Hello  Variable leaked outside function.

    - With local:
    ```
    test_func() {
    local var="Hello"
    }

    test_func
    echo "$var"
    ```
    >output: blank 
    - local restricts variable scope
    - Prevents accidental overwriting
    - Best practice in production scripts


---

### Task 5: Text Processing Commands
Document the most useful flags/patterns for each:
1. `grep` — search patterns
- `-i` : for case insensitive
- `-r`: for Recursive search `grep -r "ERROR" /var/log`
- `-c`: count matches
- `-n`: print with the line numbers/  Show line numbers
- `-v`: Invert match/ Shows lines NOT containing INFO `grep -v "INFO" app.log`
- `-E`: Extended regex/ Matches multiple patterns.`grep -E "ERROR|CRITICAL" app.log`
2. `awk` —
- print columns : `awk '{print $1}' app.log`
- field separator: Custom Field Separator (-F) Split by : `awk -F ":" '{print $1}' /etc/passwd`
- patterns: `awk '/ERROR/ {print $0}' app.log`
- `BEGIN/END` 
```
awk 'BEGIN {print "Start"} /ERROR/ {count++} END {print "Total Errors:", count}' app.log

```
3. `sed` — Stream Editor
- substitution: Replace first occurrence per line. `sed 's/ERROR/WARNING/' app.log`
- delete lines: Delete lines containing INFO. `sed '/INFO/d' app.log`
- in-place edit: Modifies file directly  In-Place Edit (-i) `sed -i 's/old/new/g' file.txt`
4. `cut` — 
- extract columns by delimiter
    - d → delimiter

    - f → field number
    ```
    cut -d ":" -f1 /etc/passwd
    ```
5. `sort` — 
- alphabetical: `sort file.txt`
- numerical: `sort -n numbers.txt`
- reverse: `sort -r file.txt`
- unique: `sort -u file.txt`
6. `uniq` — Requires sorted input.
- deduplicate:
- count
    - remove deduplicate:` sort file.txt | uniq`
    - Count duplicates (-c): `sort file.txt | uniq -c`
    - Only duplicates (-d): `sort file.txt | uniq -d`

7. `tr` — translate/delete characters
- Convert lowercase to uppercase: `echo "hello" | tr 'a-z' 'A-Z'`
- Delete characters (-d): `echo "hello123" | tr -d '0-9'`

8. `wc` — 

- line: `wc -l file.txt`
- word: `wc -w file.txt`
- char: `wc -c file.txt`

9. `head` / `tail` — 
- first/last N lines: `head -5 file.txt` and `tail -5 file.txt`
- follow mode: Live log streaming. `tail -f app.log`

---

### Task 6: Useful Patterns and One-Liners
Include at least 5 real-world one-liners you find useful. Examples:
- Find and delete files older than N days
```
find /var/log -type f -name "*.log" -mtime +7 -print
find /var/log -type f -name "*.log" -mtime +7 -delete
```
- Count lines in all `.log` files
```
wc -l *.log
```
- Replace a string across multiple files
```
sed -i 's/ERROR/WARNING/g' *.log
```
- Check if a service is running
```
systemctl is-active nginx
```
- Monitor disk usage with alerts
```
df -h | awk '$5+0 > 80 {print "Warning: High disk usage on " $6}'
```
- Parse CSV or JSON from command line
    - example file
    name,age,city
    ram,25,delhi
    ```
    awk -F "," '{print $1}' file.csv
    ```

- Tail a log and filter for errors in real time
    - Case insensitive: -i
    - --line-buffered ensures real-time output
    ```
    tail -f app.log | grep -i --line-buffered "error"

    ```
    - Kill Process Using Most Memory
    ```ps aux --sort=-%mem | head -5
    ```

---

### Task 7: Error Handling and Debugging
Document with examples:
1. Exit codes — What is an Exit Code?

Every command returns a number:
0 → Success

Non-zero → Error

- `$?`: Last Command Status
- `exit 0`: # Success
- `exit 1`:  # Failure
2. `set -e` — exit on error
3. `set -u` — treat unset variables as error
4. `set -o pipefail` — catch errors in pipes
5. `set -x` — debug mode (trace execution)
6. Trap — `trap 'cleanup' EXIT`

---

### Task 8: Bonus — Quick Reference Table
Create a summary table like this at the top of your cheat sheet:

| Topic | Key Syntax | Example |
|-------|-----------|---------|
| Variable | `VAR="value"` | `NAME="DevOps"` |
| Argument | `$1`, `$2` | `./script.sh arg1` |
| If | `if [ condition ]; then` | `if [ -f file ]; then` |
| For loop | `for i in list; do` | `for i in 1 2 3; do` |
| Function | `name() { ... }` | `greet() { echo "Hi"; }` |
| Grep | `grep pattern file` | `grep -i "error" log.txt` |
| Awk | `awk '{print $1}' file` | `awk -F: '{print $1}' /etc/passwd` |
| Sed | `sed 's/old/new/g' file` | `sed -i 's/foo/bar/g' config.txt` |

---

## Format Guidelines

Your cheat sheet should be:
- Written in **Markdown** (`.md`)
- Organized with **clear headings** for each section
- Include **code blocks** with syntax highlighting (` ```bash `)
- Keep explanations **short** — 1-2 lines max per item
- Focus on **practical examples** over theory
- Something **you would actually refer back to** on the job

