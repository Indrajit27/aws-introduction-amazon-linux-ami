# Linux Command Line

## Overview

This repository includes notes for an AWS Academy / Vocareum lab that introduces basic Linux command-line operations on an Amazon Linux EC2 instance.

**Estimated duration:** 30 minutes

## Learning objectives

- Run commands to learn about the current system and shell session.
- Search and reuse previously entered Bash commands.

## Lab environment

The lab provides temporary AWS console access and an Amazon Linux EC2 instance. AWS service actions may be restricted to those required by the lab.

Start the lab, wait for **Lab status: ready**, and open the AWS Management Console using the lab-provided link.

## Task 1: Connect to the Amazon Linux EC2 instance using SSH

Use the credentials and public IP displayed in the lab's **Details → Show** panel.

### Windows with PuTTY

1. Download the lab-provided `labsuser.ppk` private key.
2. Note the instance's `PublicIP`.
3. Open PuTTY.
4. Configure the SSH connection using the EC2 public IP and the `labsuser.ppk` key. Follow the AWS instructions for connecting to a Linux instance using PuTTY.
5. Connect to the instance and accept the first-connection host-key prompt when appropriate.

### macOS / Linux with OpenSSH

1. Download the lab-provided `labsuser.pem` private key and note the `PublicIP`.
2. Change to the directory containing the key. For example:

   ```bash
   cd ~/Downloads
   ```

3. Restrict the key's permissions:

   ```bash
   chmod 400 labsuser.pem
   ```

4. Connect to the instance, replacing the placeholder with the lab's public IP:

   ```bash
   ssh -i labsuser.pem ec2-user@<public-ip>
   ```

5. Type `yes` at the first-connection prompt when asked to trust the remote SSH host. Key-based authentication should not require an account password.

**Security:** Never commit `.pem` or `.ppk` files, credentials, or temporary lab IP details to GitHub.

## Task 2: Run familiar Linux commands

Run these commands in the connected terminal, in the order shown in the lab.

| Command / action | Purpose |
|---|---|
| Type `whoa`, then press Tab | Demonstrates shell command completion to `whoami` |
| `whoami` | Displays the current username |
| `hostname -s` | Displays the short hostname |
| `uptime -p` | Displays system uptime in a readable format |
| `who -H -a` | Displays logged-in user and session information |
| `TZ=America/New_York date` | Displays the date and time for New York |
| `TZ=America/Los_Angeles date` | Displays the date and time for Los Angeles |
| `cal -j` | Displays the current month's calendar using Julian day numbers |
| `cal -s` | Displays a Sunday-first calendar |
| `cal -m` | Displays a Monday-first calendar |
| `id ec2-user` | Displays the user ID, group ID, and group membership for `ec2-user` |

The timezone commands rely on the system clock being configured correctly. The lab notes that an incorrect system time can produce incorrect displayed times.

## Task 3: Use Bash history and search

### View command history

Run:

```bash
history
```

Review the list and check whether the commands from Task 2 appear.

### Search previous commands

1. Press **Ctrl+R** to start reverse history search.
2. Type `TZ` to search for a previous command containing that text.
3. Use the terminal's editing/navigation keys to review or edit the recalled command.
4. The lab instructs you to use Tab completion during this exercise.

### Repeat the most recent command

Run:

```bash
date
!!
```

The `!!` history expansion repeats the most recently entered command. In this example, it runs `date` again.

## Lab completion

The lab's final step is to select **End Lab**, confirm with **Yes**, and close the completion panel.

## Practice checklist

Mark each item only after performing it in the lab.

- [ ] Started the lab and opened the AWS Management Console.
- [ ] Connected to the Amazon Linux EC2 instance over SSH.
- [ ] Ran `whoami`, `hostname -s`, and `uptime -p`.
- [ ] Ran `who -H -a` and the timezone-specific `date` commands.
- [ ] Practiced `cal -j`, `cal -s`, `cal -m`, and `id ec2-user`.
- [ ] Viewed Bash history with `history`.
- [ ] Used reverse history search with **Ctrl+R**.
- [ ] Repeated the previous command with `!!`.
- [ ] Ended the lab.

## Source

AWS Academy / Vocareum lab: **Linux Command Line**.
