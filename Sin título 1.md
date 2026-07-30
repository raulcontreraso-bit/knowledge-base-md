

Yes, you can do it right from PowerShell using Windows' native package manager (`winget`)! It is fast and keeps you entirely inside the terminal.

### Step 1: Install the C/C++ Compiler via PowerShell

1. Open **PowerShell** (you can right-click the Windows Start button and select PowerShell or Terminal).
    
2. Run this command to install WinLibs (a clean, native port of GCC/G++ for Windows):
    

PowerShell

```
winget install --id=BrechtSanders.WinLibs.POSIX.UCRT -e
```

3. Follow any on-screen prompts to accept the installation.
    

### Step 2: Refresh Your Environment Variables

Once the installation finishes, PowerShell needs to recognize the new path. Close your current PowerShell window, open a brand new PowerShell window, and verify it worked by typing:

PowerShell

```
gcc --version
g++ --version
```

If it prints out the version information, you're all set to compile and run C and C++ directly from PowerShell!