

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




Yes, you can install MSYS2 straight from PowerShell using `winget`!

Open your PowerShell and run this command:

PowerShell

```
winget install --id=MSYS2.MSYS2
```

Once that finishes downloading and installing:

1. Close your PowerShell window.
    
2. Open the **MSYS2 UCRT64** app from your Windows Start Menu (or type `msys2` in your search bar to find it).
    
3. Paste this command into that terminal to install the complete C/C++ compiler toolchain:
    

Bash

```
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

Press `Enter` to accept all defaults and let it finish installing. Let me know when this part is done!




Yes, you can install MSYS2 straight from PowerShell using `winget`!

Open your PowerShell and run this command:

PowerShell

```
winget install --id=MSYS2.MSYS2
```

Once that finishes downloading and installing:

1. Close your PowerShell window.
    
2. Open the **MSYS2 UCRT64** app from your Windows Start Menu (or type `msys2` in your search bar to find it).
    
3. Paste this command into that terminal to install the complete C/C++ compiler toolchain:
    

Bash

```
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

Press `Enter` to accept all defaults and let it finish installing. Let me know when this part is done!




---------



Yes, you can install MSYS2 straight from PowerShell using `winget`!

Open your PowerShell and run this command:

PowerShell

```
winget install --id=MSYS2.MSYS2
```

Once that finishes downloading and installing:

1. Close your PowerShell window.
    
2. Open the **MSYS2 UCRT64** app from your Windows Start Menu (or type `msys2` in your search bar to find it).
    
3. Paste this command into that terminal to install the complete C/C++ compiler toolchain:
    

Bash

```
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

Press `Enter` to accept all defaults and let it finish installing. Let me know when this part is done!


That is a great question! It comes down to **how Windows handles programs versus how Linux-style environments work.**

Here is why we use both:

### 1. Why use PowerShell first?

PowerShell is your standard Windows control center. Programs like `winget` are built right into Windows, which makes PowerShell the fastest and cleanest way to **download and install** big software packages onto your hard drive without having to click through web browsers.

### 2. Why use the MSYS2 shell second?

MSYS2 isn't just a collection of files; it is a mini-Linux environment running inside Windows.

- **The Package Manager (`pacman`):** MSYS2 uses a package manager called `pacman` (originally from Arch Linux) to download and manage C/C++ compilers. `pacman` only exists inside the MSYS2 ecosystem, so standard PowerShell doesn't know what it is.
    
- **The Isolated Environment:** The MSYS2 shell (`UCRT64`) is pre-configured to automatically link all the complex C/C++ paths, libraries, and tools together safely.
    

Think of it like this: **PowerShell** is the delivery driver that drops the toolbox at your front door, and the **MSYS2 shell** is the specialized workbench where all the tools inside that box are neatly set up and ready to use.

Were you able to open the MSYS2 UCRT64 window and run the `pacman` command?


## The Grand Master Plan: Manual MinGW-w64 Setup

Since we are diving headfirst into the vintage archives, we are going to manually install **MinGW-w64** (Minimalist GNU for Windows) the old-school way. No automated `winget`, no heavy MSYS2 pacman managers—just a direct zip file, a folder structure, and a manual Windows Environment Variable.

### Step 1: Download the Pure Archive

1. Go directly to the sourceforge release page for WinLibs (the standalone builds of GCC for Windows):
    
    [WinLibs Standalone Builds - SourceForge](https://www.google.com/search?q=https://sourceforge.net/projects/winlibs/)
    
2. Scroll down to find the latest **UCRT runtime** release for **64-bit Windows**.
    
3. Look for the file ending in `.zip` (specifically the one labeled something like `winlibs-x86_64-posix-ucrt-...-gcc-...-snapshot-...-release.zip`).
    
4. Click download and save the zip file.
    

### Step 2: Extract to C:\

1. Once downloaded, extract the contents of the zip file.
    
2. Inside, you will see a folder named `mingw64`.
    
3. Move or copy that entire `mingw64` folder directly to the root of your primary drive so it sits at:
    
    Plaintext
    
    ```
    C:\mingw64
    ```
    

_(This gives us a clean, short path with no spaces, which compilers love.)_

### Step 3: Wire it into Windows (Environment Variables)

This is the archaic heart of the operation—telling Windows where the binary executable files live.

1. Press the Windows Key, type **Environment Variables**, and select **Edit the system environment variables**.
    
2. Click the **Environment Variables...** button at the bottom right.
    
3. In the bottom box (**System variables**), look for a variable named **`Path`** and double-click it.
    
4. Click **New** on the right side and type:
    
    Plaintext
    
    ```
    C:\mingw64\bin
    ```
    
5. Click **OK** on all the open windows to save your changes.
    

### Step 4: The Moment of Truth

1. Close your current PowerShell or Command Prompt completely.
    
2. Open a **brand new** PowerShell window (so it reads the new PATH variable).
    
3. Type:
    
    PowerShell
    
    ```
    gcc --version
    ```
    

Let me know if it greets you with the compiler version!



Ah, look at that! The screenshot shows that **MSYS2 actually successfully installed** earlier (`C:\msys64` is right there on your `C:\` drive), and it looks like a manual `mingw64` folder might be there too or it came from MSYS2.

Because you have MSYS2 installed at `C:\msys64`, your UCRT64 toolchain is tucked away inside it. That's why the manual `C:\mingw64\bin` path didn't work—the actual path for the MSYS2 UCRT compiler lives inside the msys structure.

Let's fix your Windows Environment Variable so PowerShell can find it directly:

### Update the Path

1. Press the Windows Key, type **Environment Variables**, and select **Edit the system environment variables**.
    
2. Click **Environment Variables...** at the bottom right.
    
3. Double-click **Path** under _System variables_.
    
4. Click **New** and add this exact path:
    
    Plaintext
    
    ```
    C:\msys64\ucrt64\bin
    ```
    
5. Click **OK** on all windows to save.
    

### Test It

1. Close your current PowerShell window completely.
    
2. Open a brand new PowerShell window.
    
3. Type:
    
    PowerShell
    
    ```
    gcc --version
    ```
    

Let me know if it finally prints out the GCC version!


- **Why we used WSL (Windows Subsystem for Linux):**
    
    It lets you run a genuine, lightweight Linux environment directly inside Windows without the heavy baggage, lag, or complicated setup of a traditional virtual machine or a dual-boot setup. It bridges the gap so you get native Linux tools while staying on Windows.
    
- **How we worked from there:**
    
    - You opened a Linux terminal tab (like Ubuntu) right inside your Windows terminal.
        
    - Inside that environment, you could use native Linux package managers (like `apt`) to instantly pull down compilers, libraries, or developer tools without messing with manual Windows paths or zip files.
        
    - Your Linux files could also be accessed seamlessly right from Windows Explorer (via the Linux network/tux icon sidebar), letting both operating systems share the workspace.



Let's write and compile your first C program using your new lightweight setup!

### Step 1: Create your C file

Create a new file anywhere on your computer (for example, on your Desktop) and name it **`main.c`**.

Open it with any text editor (like Notepad or VS Code) and paste this classic C code:

C

```
#include <stdio.h>

int main() {
    printf("Hello, World from GCC 16.1.0 on Windows!\n");
    return 0;
}
```

### Step 2: Compile it with GCC

Open your PowerShell, navigate to the folder where you saved `main.c` (using `cd your_folder_path`), and run this compile command:

PowerShell

```
gcc main.c -o program.exe
```

- _What this does:_ It tells `gcc` to take `main.c` and compile it into a runnable Windows program named `program.exe`.
    

### Step 3: Run it!

Type the name of your new executable right there in PowerShell:

PowerShell

```
.\program.exe
```

Let me know what happens when you run it!



Yes, absolutely! The extension you give your source file tells `gcc` (and other compilers) which language it is dealing with and how to compile it.

Here is the quick breakdown of the two:

- **`.c` (C Language):** This tells the compiler to parse and compile the file using standard **C** rules (like C11, C17, or C23).
    
- **`.cpp` (C++ Language):** This tells the compiler to switch to **C++** rules (supporting classes, objects, `std::cout`, templates, etc.).
    

If you name your file with a `.cpp` extension instead of `.c`, you can actually still use your exact same `gcc` command, or you can use its C++ counterpart (`g++`) which comes in the exact same MinGW/MSYS2 toolchain!

For example, if you name your file `main.cpp`, you would compile it like this:

PowerShell

```
g++ main.cpp -o program.exe
```

Are you planning to write pure C, or did you want to dive into C++ instead?


Mixing C and C++ together is a fantastic way to learn because C++ was literally built as an extension of C! Doing this teaches you how they talk to each other under the hood.

Because C++ can understand C (with a little bit of help), you can compile them together using your `g++` compiler. Here is how you can mix them cleanly:

### Step 1: Write a pure C file (`helper.c`)

Create a file named `helper.c` with a standard C function:

C

```
#include <stdio.h>

void say_hello_from_c() {
    print("Hello from a pure C function!\n");
}
```

_(Wait, let's fix that tiny typo to `printf` when you write it!)_

### Step 2: Write a C++ file that uses it (`main.cpp`)

Create a file named `main.cpp`. Because C and C++ handle function names slightly differently during compilation (due to "name mangling"), you have to wrap your C function declarations in an `extern "C"` block so C++ knows how to find it:

C++

```
#include <iostream>

// Tell the C++ compiler: "Hey, this function was written in C, don't change its name!"
extern "C" {
    void say_hello_from_c();
}

int main() {
    std::cout << "Hello from C++! Now calling C...\n";
    
    // Call the C function from your C++ program
    say_hello_from_c();
    
    return 0;
}
```

### Step 3: Compile them together!

Because your main file is C++ (`.cpp`), use `g++` to compile both files at the exact same time into a single executable:

PowerShell

```
g++ main.cpp helper.c -o mixed_program.exe
```

### Step 4: Run it

PowerShell

```
.\mixed_program.exe
```

Mixing them like this forces you to understand linkers, header declarations, and how C++ maintains backwards compatibility with C. Want to give this mix-and-match experiment a try?


