# PE Mod (beta)

PE Mod is a C tool designed to modify PE (Portable Executable) files by adding new sections, naming them, and embedding shellcode within those sections. The tool also modifies the Entry Point address to redirect execution to the embedded shellcode, allowing it to be executed from the newly added section.

## Usage

To use PE Mod, run the following command:

```
pemod.exe <pefile> <sectionName> <shellcodeFile>
```

- **<pefile>**: The path to the PE file you wish to modify.
- **<sectionName>**: The name you want to assign to the newly added section.
- **<shellcodeFile>**: The path to the shellcode file to be embedded in the new section.

## How it Works

1. **PE File Modification**: PE Mod inserts a new section into the specified PE file.
2. **Shellcode Insertion**: The provided shellcode is embedded into the newly created section.
3. **Entry Point Modification**: The tool then modifies the PE file’s Entry Point so that, upon execution, it jumps to the shellcode located in the new section.

## Example

To add a new section called `mySection` containing shellcode from `shellcode.bin` to `example.exe`, you would use the following command:

```
pemod.exe example.exe mySection shellcode.bin
```

## Requirements

- A C compiler (e.g., GCC, MSVC) for building the tool.
- The shellcode file must be in raw binary format.

## Disclaimer

This tool is intended for educational and research purposes only. It should not be used for unauthorized activities or attacks. The authors are not responsible for any misuse of the tool.
