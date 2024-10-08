# SB-TRANSPILER

**For the Portuguese version, read the [README-pt.md](README-pt.md).**

Source code translator from the Custom Assembly to IA-32 Assembly. Project developed in C++ with input and output operations in IA-32 Assembly.

## Authors

Gustavo Santana Lima - 211038235  
Yan Tavares - 202014323

## Usage

### Option 1 - Using the Makefile

To use the translator, simply run the command below:

```bash
make FILE=<file>
```

Where `<file>` is the file containing the source code **without the extension**.

**NOTE:** The file **must be** inside the `arquivos` directory.

## Example

To translate the `in_out_var.obj` file inside the `arquivos` directory, simply run the command below:

```bash
make FILE=in_out_var
```

The command will generate a file named `in_out_var.asm` in the `output` directory, assemble, and execute the generated code.

### Option 2 - Compiling and running manually

To compile the translator, simply run the command below:

```bash
g++ -o tradutor Tradutor.cpp
```

To run the translator, execute the following command:

```bash
./tradutor <file>.obj
```

Where `<file>` is the `.obj` file containing the source code.

To assemble, link, and execute the generated code, run the following commands:

```bash
nasm -f elf32 <file>.asm -o <file>.o
ld -m elf_i386 -o <file> <file>.o
./<file>
```

The executable file will print how many bytes were read and written to the terminal.

**NOTE:** The number of bytes read includes the newline character (`\n`).

## Project Structure

```
SB-TRANSLATOR
│ README.md
│ Makefile
│ Tradutor.cpp
│ Tradutor.hpp
│ io.asm
│
├── bin*
│ │ tradutor
│ │ file1
│
├── output*
│ │ file1.asm
│ │ file1.o
│
├── Arquivos
│ │ file1.obj
│ │ ...
│
```

Directories marked with `*` are automatically generated by the Makefile.

## Contact

If you would like to get in touch, send an email to any of the authors:

- [yantdo1@gmail.com](mailto:yantdo1@gmail.com)
- [guts.santana@gmail.com](mailto:guts.santana@gmail.com)