# Linux Command Quick Reference

These commands are useful for basic orientation on an Amazon Linux EC2 instance.

| Command | Purpose |
|---|---|
| `pwd` | Print the current working directory |
| `ls` | List directory contents |
| `ls -la` | List all entries, including hidden files, with details |
| `whoami` | Print the current username |
| `hostname` | Display the system hostname |
| `uname -a` | Display kernel and system information |
| `date` | Display the system date and time |
| `clear` | Clear the terminal display |
| `history` | Display command history |
| `man man` | Open the manual for the `man` utility |
| `man ls` | Open the manual for `ls` |
| `man pwd` | Open the manual for `pwd` |

## Manual-page navigation

| Key / Input | Purpose |
|---|---|
| `Space` | Next screen |
| `b` | Previous screen |
| `Up` / `Down` | Move one line |
| `/keyword` | Search forward |
| `n` | Next search match |
| `N` | Previous search match |
| `q` | Quit the manual page |

## Example practice sequence

```bash
whoami
hostname
pwd
uname -a
ls -la
man ls
```

These are reference notes; mark commands as completed only after running them in your lab session.
