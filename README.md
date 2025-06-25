# 🚀 STM32F103C8T6 C++ Integration Guide

> A simple and efficient setup for using **C++** in **STM32CubeIDE** projects
> 📻 Based on this [YouTube tutorial](https://youtu.be/9syJpWDqj88)

---

## 📌 Objective

Enable and structure your STM32CubeIDE project to use **C++** (`.cpp`) files, offering object-oriented features and better organization — ideal for larger embedded projects.

---

## 📁 Project Structure

```
YourProject/
├── Core/
│   ├── Inc/
│   └── Src/
├── CPP/
│   ├── Inc/        <- For your C++ headers
│   └── Src/        <- For your C++ source files
└── STM32F103C8T6.ioc
```

---

## 🧠 Quick Setup (10 Easy Steps)

### ✅ Step 1: Create Project

Use **STM32CubeMX** or **STM32CubeIDE** to generate the `.ioc` and base project as usual.

### ✅ Step 2: Modify `main.c`

In the infinite loop of `main.c`, call your custom C++ entry point:

```c
while (1)
{
    CPPMain();  // Call C++ main loop
}
```

---

### ✅ Step 3: Declare C++ Entry in `main.h`

Add this in `main.h` inside the `/* USER CODE BEGIN EFP */` section:

```c
void CPPMain(void);
```

---

### ✅ Step 4–6: Create C++ Folder and Entry File

1. Create a new folder: `CPP`
2. Inside `CPP`, create:

   * `Inc/` → for headers
   * `Src/` → for sources
3. Add a file: `CPPMain.cpp` inside `CPP/Src/`

Example content:

```cpp
#include "main.h"

void CPPMain()
{
    while (1)
    {
        // Your C++ logic here
    }
}
```

---

### ✅ Step 7–10: Include Paths for Compilation

1. **Right-click** your project → **Properties**
2. Go to: `C/C++ General → Paths and Symbols → Includes`
3. Add the following:

   * Click `Add...`
   * ✅ Check **"Is a workspace path"**
   * Select: `YourProject/CPP/Inc`
   * Click OK → Apply and Close

---

## ✅ You're Done!

Now you can start using **C++** in your STM32 project 🎉

---

## 📷 Demo Screenshot

> *(Optional)*
> Include screenshots or project structure previews here.

---

## 🛠️ Tips

* Don’t forget to set the file extension to `.cpp`, `.hpp` to avoid linking issues.
* Use `extern "C"` when including C headers in C++ files:

```cpp
extern "C" {
    #include "main.h"
}
```

---

## 📚 Resources

* [STM32CubeIDE Documentation](https://www.st.com/en/development-tools/stm32cubeide.html)
* [ARM GCC Toolchain](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm)
