# Structure
## Repository Structure
```
.
├─ cli/     Compiler CLI, tools and help texts.
├─ docs/    Documentation files for users and contributors.
├─ lib/     Root for all standard library packages.
   ├─ bait/    Core compiler implementation.
   └─ ...
├─ tests/   Tests for general language features that do not belong to specific packages.
└─ ...
```

## Compiler Structure
The compiler consists of the following core packages:
- `ast`: Defines AST nodes, the scope system and the type system
- `builder`: Collect files, resolve imports and run all compilation stages
- `checker`:
  - Resolve all type information
  - Perfrom error and type checks
- Code Generation
  - `gen.c`: C backend (🚧)
  - `gen.js`: JavaScript backend
- `lexer`: Break source code into tokens
- `parser`: Create the AST and perform basic type resolving for constants and globals
- `preference`: Define preferences and argument parsing
- `token`: Defines tokens and their precedence

Other packages include:
- `message`: Data structures for compiler messages
- Utilities
  - `util.testing`: Common logic for in-out tests
  - `util.timers`: Helpers to measure performance of compiler stages
  - `util.tools`: Logic to launch tools in `cli/tools/`
