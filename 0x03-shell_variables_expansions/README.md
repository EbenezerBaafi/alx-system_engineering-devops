# Shell Alias Script

## Description
This project contains a Bash script that creates a shell alias. The script demonstrates how aliases can override default command behavior by aliasing `ls` to `rm *`.

## ⚠️ WARNING
**This script is EXTREMELY DANGEROUS and is intended for EDUCATIONAL PURPOSES ONLY.**

When sourced, this script will cause the `ls` command to delete all files in the current directory instead of listing them. This can result in permanent data loss.

**DO NOT use this script in:**
- Production environments
- Directories with important files
- Any location where data loss would be problematic

## Files
- `0-alias` - Bash script that creates the alias

## Requirements
- Bash shell (GitBash, Linux terminal, macOS terminal, or WSL)
- Unix-like environment

## Usage

### Setup
1. Create a test directory with dummy files:
```bash
mkdir -p /tmp/0x03
cd /tmp/0x03
touch file1 file2
```

2. Copy the `0-alias` script to this directory

3. Source the script to load the alias:
```bash
source ./0-alias
```

### Testing
After sourcing the script:
```bash
# This will now DELETE all files instead of listing them
ls

# To actually list files, use backslash to bypass the alias
\ls
```

### Example Output
```
julien@ubuntu:/tmp/0x03$ ls
0-alias  file1  file2
julien@ubuntu:/tmp/0x03$ source ./0-alias 
julien@ubuntu:/tmp/0x03$ ls
julien@ubuntu:/tmp/0x03$ \ls
julien@ubuntu:/tmp/0x03$ 
```

## How It Works
- The script uses the `alias` command to override the `ls` command
- `alias ls='rm *'` tells the shell to run `rm *` whenever `ls` is typed
- The alias only persists in the current shell session
- Using `\ls` bypasses the alias and executes the actual `ls` command

## Removing the Alias
To remove the dangerous alias from your current session:
```bash
unalias ls
```

Or simply close the terminal window.

## Learning Objectives
- Understanding shell aliases
- Learning how commands can be overridden
- Recognizing the security implications of malicious aliases
- Understanding the difference between aliased and escaped commands

## Safety Tips
✅ **DO:**
- Use this in isolated test environments only
- Create dummy files for testing
- Always verify you're in the correct directory
- Remove the alias immediately after testing

❌ **DON'T:**
- Use this script on important directories
- Leave this alias active
- Share this script without proper warnings
- Use this in shared environments

## Author
Educational demonstration script

## License
This script is provided for educational purposes only. Use at your own risk.