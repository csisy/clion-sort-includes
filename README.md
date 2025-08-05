Tried to save all changes into the project-specific settings, but here are the most notable options:

- **Editor | Code Style | C/C++ | General**
    - *C/C++ formatting engine*: `ClangFormat`
- **Editor | Code Style | C/C++ | Syntax Style**
    - *Sort include directives*: `checked`
    - *Type of slashes to use in include directives*: `Use forward slashes`
    - *Use angle brackets instead of quotes*: `When possible`
- **Languages & Frameworks | C/C++ | Order of #includes**
    - Only `Preserve existing #include groups during a sort` is checked
    - Added `^<MyLib.*>` just above the `^<.*` (thus, below the `Header for the current file`)
- Optionally **Tools | Actions on Save**
    - *Reformat code*: `checked`

A minimal `clang-format` file is present with the same include sorting options.

**The issue**

- Open `B.cpp`
- CLion warns that the includes are out of order (`A.h` should be before `B.h`)
- Sort the includes via the context action
- `MyLib/A.h` is sorted before `MyLib/B.h`
- If reformat code on save is enabled, the clang-format immediately sorts it back to the correct `MyLib/B.h`then
  `MyLib/A.h` order
