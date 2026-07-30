

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


That is normal! The installation finished successfully, but PowerShell doesn't know where `gcc` is located yet because the installation path hasn't been added to your system's Environment Variables (PATH).

Since you used `winget`, the files are installed on your system, but we just need to let PowerShell find them. Let's fix that right now:

### Step 1: Find where WinLibs installed `gcc.exe`

Usually, WinLibs installs itself inside a folder under `C:\Program Files\WinLibs` or inside your user profile. Let's find it quickly by running this command in PowerShell:

PowerShell

```
Get-ChildItem -Path "C:\Program Files" -Filter "gcc.exe" -Recurse -ErrorAction SilentlyContinue
```

_(If that doesn't return anything, check your user folder or your AppData)._

### Step 2: Add it to your PATH (or use the automatic way)

Alternatively, the easiest way to make PowerShell recognize it immediately without hunting for folders is to restart your entire computer or log out and log back into Windows. `winget` usually updates the PATH, but Windows needs a full session refresh to see it.

Try this right now:

1. Close **all** open PowerShell and terminal windows.
    
2. Open a **brand new** PowerShell window.
    
3. Type:
    
    PowerShell
    
    ```
    gcc --version
    ```
    

Did it recognize `gcc` after opening a fresh window?


Ah, `winget` installed the tool aliases successfully (which is why you saw all those `x86_64-w64-mingw32-gcc` commands added), but it dropped them into a directory that PowerShell doesn't look at by default yet.

Let's locate where WinLibs placed the executables on your system. Run this quick search command in PowerShell to find `x86_64-w64-mingw32-gcc.exe`:

PowerShell

```
Get-ChildItem -Path "C:\" -Filter "x86_64-w64-mingw32-gcc.exe" -Recurse -ErrorAction SilentlyContinue
```

Paste the path it gives you here, and we will hook it straight into your PowerShell environment!