# 0x0B. SSH

## Description

This project is part of the ALX System Engineering & DevOps track.  
It covers **SSH (Secure Shell)** basics, key-based authentication, SSH configuration, and using Puppet for automated configuration.  
The goal is to connect securely to a remote Ubuntu 20.04 LTS server using RSA keys instead of passwords.

---

## Learning Objectives

By the end of this project, you should be able to explain to anyone:

- **General**
  - What is a server
  - Where servers usually live
  - What is SSH
  - How to create an SSH RSA key pair
  - How to connect to a remote host using an SSH RSA key pair
  - The advantage of using `#!/usr/bin/env bash` instead of `/bin/bash`

---

## Resources

- [SSH essentials](https://www.ssh.com/academy/ssh)
- [Public Key Authentication for SSH](https://www.ssh.com/academy/ssh/public-key-authentication)
- [How Secure Shell Works](https://www.ssh.com/academy/ssh/protocol)
- `man ssh`
- `man ssh-keygen`
- `man env`

---

## Project Requirements

- Environment: Ubuntu 20.04 LTS
- All scripts must:
  - Be executable
  - Start with `#!/usr/bin/env bash`
  - Contain a comment describing their purpose
- No plagiarism
- Files must end with a newline

---

## Files

| File                       | Description                                                                                       |
| -------------------------- | ------------------------------------------------------------------------------------------------- |
| `0-use_a_private_key`      | Connects to a server using the private key `~/.ssh/school` with the `ubuntu` user.                |
| `1-create_ssh_key_pair`    | Generates a 4096-bit RSA key pair named `school` with passphrase `betty`.                         |
| `2-ssh_config`             | SSH client configuration to use `~/.ssh/school` and disable password authentication.              |
| _Server Setup_             | Adds provided ALX public key to `~/.ssh/authorized_keys` to allow grader access.                  |
| `100-puppet_ssh_config.pp` | Puppet script to configure SSH client to use `~/.ssh/school` and disable password authentication. |

---

## Usage

### 0. Use a private key

```bash
./0-use_a_private_key
```
