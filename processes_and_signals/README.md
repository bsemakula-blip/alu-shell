# Shell, processes and signals

Bash scripts practising PIDs, process listing, killing processes, signals (`trap`) and init scripts.

All scripts start with `#!/usr/bin/env bash`, have a comment on line 2 explaining what they do,
are executable, and are meant to pass Shellcheck.

## Files

| File | Description |
|---|---|
| `0-what-is-my-pid` | Displays its own PID |
| `1-list_your_processes` | Lists all processes, all users, user-oriented format, with hierarchy (`ps auxf`) |
| `2-show_your_bash_pid` | Shows the process list lines containing `bash` (no `pgrep`) |
| `3-show_your_bash_pid_made_easy` | Shows PID and name of processes containing `bash` (no `ps`) |
| `4-to_infinity_and_beyond` | Displays "To infinity and beyond" forever, with `sleep 2` |
| `5-dont_stop_me_now` | Stops `4-to_infinity_and_beyond` using `kill` |
| `6-stop_me_if_you_can` | Stops `4-to_infinity_and_beyond` without `kill` or `killall` |
| `7-highlander` | Like task 4, but prints "I am invincible!!!" on SIGTERM instead of dying |
| `67-stop_me_if_you_can` | Copy of task 6 that targets `7-highlander` |
| `8-beheaded_process` | Kills `7-highlander` with SIGKILL, which cannot be trapped |
| `10-process_and_pid_file` | Writes its PID to `/var/run/myscript.pid` and handles SIGTERM, SIGINT and SIGQUIT |
| `manage_my_process` | Writes "I am alive!" to `/tmp/my_process` every 2 seconds |
| `11-manage_my_process` | Init script: `start`, `stop`, `restart` for `manage_my_process`, with a PID file in `/var/run/my_process.pid` |

## Testing the signal tasks

Use two terminals. Run the target script in terminal 0 and the killer script in terminal 1.
Tasks 10 and 11 write to `/var/run`, so run them with `sudo`.

```bash
chmod +x ./*
# terminal 0
./7-highlander
# terminal 1
./67-stop_me_if_you_can
```

The two signals that cannot be caught or ignored are SIGKILL and SIGSTOP.
