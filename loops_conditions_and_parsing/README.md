# Shell, loops, conditions and parsing

Bash scripts practising loops (`for`, `while`, `until`), conditions (`if`, `elif`, `else`, `case`),
file test operators, `cut`, `IFS` with `read`, and log parsing with `awk`.

All scripts start with `#!/usr/bin/env bash`, have a comment on line 2 explaining what they do,
are executable, and are meant to pass Shellcheck.

## Files

| File | Description |
|---|---|
| `1-for_best_school` | Displays "Best School" 10 times (for loop) |
| `2-while_best_school` | Displays "Best School" 10 times (while loop) |
| `3-until_best_school` | Displays "Best School" 10 times (until loop) |
| `4-if_9_say_hi` | Displays "Best School" 10 times, with "Hi" after the 9th (while + if) |
| `5-4_bad_luck_8_is_your_chance` | Loops 1 to 10: "bad luck" on 4, "good luck" on 8 (while + if/elif/else) |
| `6-superstitious_numbers` | Numbers 1 to 20 with bad luck messages for 4, 9 and 17 (while + case) |
| `7-clock` | Displays hours 0 to 12 and minutes 1 to 59 (nested while) |
| `8-for_ls` | Lists the current directory showing only the part of each name after the first dash (for + cut) |
| `9-to_file_or_not_to_file` | Reports whether the `school` file exists, is empty, and is a regular file (if/else) |
| `10-fizzbuzz` | FizzBuzz from 1 to 100 |
| `11-read_and_cut` | Displays username, user id and home directory from `/etc/passwd` (while + cut) |
| `12-tell_the_story_of_passwd` | Tells a story from `/etc/passwd` (while + IFS) |
| `13-lets_parse_apache_logs` | Displays `IP HTTP_CODE` from `apache-access.log` (awk) |
| `14-dig_the-data` | Counts occurrences of each `IP HTTP_CODE`, highest first (awk + sort + uniq) |
| `apache-access.log` | Log file used by tasks 13 and 14 |

## Usage

```bash
chmod +x ./*
./1-for_best_school
./13-lets_parse_apache_logs | tail -n 10
```
