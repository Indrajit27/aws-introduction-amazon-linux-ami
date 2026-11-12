# Introduction to an Amazon Linux AMI

## Overview

This repository documents a beginner-level AWS hands-on lab covering SSH access to an Amazon Linux EC2 instance and the Linux manual-page system.

The lab is designed to build familiarity with the Linux command-line interface and the standard help system.

## Learning objectives

- Connect to an Amazon Linux EC2 instance using SSH.
- Understand the purpose of the `man` command.
- Navigate and search Linux manual pages.
- Identify the main sections of a manual page.

## AWS environment

The lab environment provides an EC2 Command Host in a public subnet. The lab also includes an Amazon VPC and public subnet.

**AWS services and concepts**
- Amazon EC2
- Amazon VPC
- Amazon Linux AMI
- SSH key-pair authentication
- Linux shell and manual pages

## Task 1: Connect to the EC2 instance

### Windows (PuTTY)

1. Start the lab and wait until its status is ready.
2. Open the AWS Management Console using the lab-provided link.
3. In the lab's **Details** panel, choose **Show**.
4. Download the provided `labsuser.ppk` private key and note the instance's `PublicIP`.
5. Open PuTTY and enter `ec2-user@<PublicIP>` as the host.
6. Keep port `22` and connection type `SSH`.
7. Under **Connection → SSH → Auth → Credentials**, select `labsuser.ppk`.
8. Open the session and accept the host-key prompt when connecting for the first time.

Use only the credentials and public IP supplied by the active lab session. Do not commit private keys, passwords, or other credentials to this repository.

### macOS / Linux (OpenSSH)

Download the lab-provided `labsuser.pem` key, move to its directory, and restrict its permissions:

```bash
cd ~/Downloads
chmod 400 labsuser.pem
```

Connect using the public IP shown in the lab's **Details** panel:

```bash
ssh -i labsuser.pem ec2-user@<public-ip>
```

At the first connection prompt, verify/accept the host key as appropriate for the lab environment.

## Task 2: Explore Linux manual pages

Open the manual page for the manual-page utility:

```bash
man man
```

Review the main headings:

| Heading | Purpose |
|---|---|
| NAME | Command name and short purpose |
| SYNOPSIS | Command syntax and usage format |
| DESCRIPTION | Detailed explanation of the command |
| OVERVIEW | General concepts and usage information, when present |
| EXAMPLES | Example command usage, when present |
| FILES | Related files, when present |
| OPTIONS | Available command options |
| SEE ALSO | Related manual pages and commands |

Not every manual page contains every heading.

### Navigation and search

| Key | Action |
|---|---|
| Up / Down arrows | Move through the page |
| Space | Move forward one screen |
| `b` | Move back one screen |
| `/keyword` | Search forward for a keyword |
| `n` | Go to the next match |
| `N` | Go to the previous match |
| `q` | Exit the manual page |

For example, while viewing `man man`, enter `/search`, press Enter, and use `n` to find the next match. Press `q` to return to the shell.

## Additional command-line practice

The following commands are useful for basic Linux system orientation:

```bash
whoami
hostname
pwd
uname -a
ls -la
history
man ls
```

See [Linux command notes](docs/linux-commands.md) for a quick reference.

## Key takeaways

- SSH provides encrypted remote command-line access to Linux servers.
- SSH key permissions and private-key handling are important.
- The `man` utility provides detailed documentation for Linux commands.
- Manual pages can be navigated and searched from the terminal.

## Lab completion checklist

- [ ] Started the Vocareum lab and opened the AWS console.
- [ ] Connected to the Amazon Linux EC2 instance using SSH.
- [ ] Opened and reviewed `man man`.
- [ ] Practiced searching and navigating a manual page.
- [ ] Exited the manual page and ended the lab.

## Security note

Never upload `.pem` or `.ppk` private keys, AWS credentials, account identifiers, or lab-specific secrets to GitHub. The lab's temporary resources and IP address should not be treated as permanent infrastructure.

## Lab source

AWS Academy / Vocareum lab: **Introduction to an Amazon Linux Amazon Machine Image (AMI)**.
