# microC Compiler

This repository implements a modular **compiler toolchain** for the microC language.  
It covers the complete pipeline: lexical analysis, parsing, intermediate code generation, and two-pass assembly.  

## 📂 Project Structure

```plaintext
Compiler-micorC/
├── lex/                           # Lexical analysis module
├── Lexical Analyzer for microC/   # Alternative iterative lexical analyzer
├── microC parser/                 # Parser (Bison + Flex)
├── Inter_mediate_code_generation/ # Intermediate code generator
├── code_generation/               # Translator and test programs
├── Two_pass/                      # Two-pass assembler
└── README.md                      # Project documentation
```


## 🚀 Modules

- **Lexical Analysis**  
  Uses Flex to tokenize input, build symbol tables, and generate output for later stages.

- **Parsing**  
  Implements grammar rules in Bison and validates syntax while producing parse trees.

- **Intermediate Code Generation**  
  Generates three-address code with semantic actions, enabling later optimization.

- **Code Generation**  
  Translates intermediate code into low-level form, tested with multiple `.mc` programs.

- **Two-Pass Assembler**  
  Performs symbol resolution and opcode mapping across two passes, producing the final output.

## ⚙️ Build & Run

Each module is **self-contained** with its own `Makefile`.  
Example usage for lexical analysis:

```bash
cd lex
make
./a.out < test.nc

