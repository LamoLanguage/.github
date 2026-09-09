<div align="center">

# ⚡ Lamo Ecosystem

### A modern programming language that transpiles to C.
**As simple as an interpreted language. As fast as a compiled one.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge)](https://github.com/LamoLanguage/LamoLanguage/blob/main/LICENSE)
[![Made with C](https://img.shields.io/badge/core-C99-00599C?style=for-the-badge&logo=c&logoColor=white)](https://github.com/LamoLanguage/LamoLanguage)
[![Status](https://img.shields.io/badge/status-experimental-orange?style=for-the-badge)](https://github.com/LamoLanguage/LamoLanguage/blob/main/roadmap.md)

<br>

```
fn main() {
    print("Hello, World!")
}
```

</div>

---

<br>

## 🧭 What is Lamo?

Lamo compiles down to plain C — no virtual machine, no bytecode, no interpreter sitting in the hot path. Just readable source in, optimized native machine code out.

<table>
<tr>
<td width="50%" valign="top">

**⚡ Native performance**
Transpiles to C, then compiles with GCC/Clang — real executables, no VM overhead.

**🧠 Clean syntax**
Optional semicolons, Python-like truthiness, and a small, readable grammar.

**🧬 Generics**
Generic functions, structs, `impl<T>`, and trait-style constraints (`T: Ord`).

</td>
<td width="50%" valign="top">

**🏷️ Tagged-union enums**
`Option<T> { Some(T), None }` with pattern-matching bindings.

**📦 Batteries included**
Built-in package manager, formatter, test runner, and REPL.

**🌐 Real-world builtins**
Native HTTP server support and GUI backends (Win32 / X11).

</td>
</tr>
</table>

<br>

## 📦 Repositories

<div align="center">

| Repository | What it is |
| :--- | :--- |
| ⚡ [**LamoLanguage**](https://github.com/LamoLanguage/LamoLanguage) | The core compiler, standard library, package manager, formatter, REPL & tests |
| 🖼️ [**LamoImage**](https://github.com/LamoLanguage/LamoImage) | Reference implementation of the `.lamo` image container format |
| 🧩 [**LamoLanguageVscode**](https://github.com/LamoLanguage/LamoLanguageVscode) | VS Code extension for Lamo syntax & tooling support |
| 🤖 [**LamoLLM**](https://github.com/LamoLanguage/LamoLLM) | LLM-assisted tooling and workflows for the Lamo language |
| 🗄️ [**LamoPacketManager**](https://github.com/LamoLanguage/LamoPacketManager) `archived` | Original standalone package manager, since folded into the core compiler |

</div>

<br>

## ✨ A taste of the language

```lamo
struct Player {
    name: string,
    hp: int
}

impl Player {
    fn damage(amount: int) {
        self.hp -= amount
    }
}

let hero = Player { name: "Arthur", hp: 100 }
hero.damage(25)
print(hero.hp)   // 75
```

<details>
<summary><b>🧬 Generics, expanded</b></summary>

<br>

```lamo
fn pick<T>(a: T, b: T) -> T {
    if (1 < 2) { return a }
    return b
}

struct Stack<T> {
    items: array<T>,
    top: int
}

impl<T> Stack<T> {
    fn push(x: T) {
        self.items.push(x)
        self.top += 1
    }
}

let s: Stack<int> = Stack<int> { items: [], top: 0 }
s.push(10)
print(pick("left", "right"))   // "left"
```

</details>

<br>

## 🚀 Get started

```bash
git clone https://github.com/LamoLanguage/LamoLanguage
cd LamoLanguage
make            # build the compiler → produces the `lamo` binary
make test       # run the full regression suite
./lamo run examples/main.lamo
```

<div align="center">

| Command | Description |
| :--- | :--- |
| `lamo run <file.lamo>` | Compile and run a source file |
| `lamo build <file.lamo> -o <name>` | Compile to a binary without running it |
| `lamo check <file.lamo>` | Parse and semantic-check only — great for CI |
| `lamo fmt <file.lamo>` | Normalize source formatting in place |
| `lamo test` | Run the test suite |
| `lamo eval` / `lamo repl` | Fast-feedback interpreter, no C compile step |

</div>

Full docs live in [`docs/`](https://github.com/LamoLanguage/LamoLanguage/tree/main/docs), including the [language spec](https://github.com/LamoLanguage/LamoLanguage/blob/main/docs/SPEC.md), [type system](https://github.com/LamoLanguage/LamoLanguage/blob/main/docs/TYPE-SYSTEM.md), and [memory model](https://github.com/LamoLanguage/LamoLanguage/blob/main/docs/MEMORY-MODEL.md).

<br>

## 🗺️ Philosophy

> **As simple as an interpreted language, as fast as a compiled one.**

Lamo stays deliberately small. Every new construct ships with defined semantics, compiler validation, and tests — syntax never outruns meaning.

<br>

## 🤝 Contributing

Contributions are welcome across every repo in this org — compiler internals, standard library, editor tooling, or docs. Open an issue or PR to get started, and check [`docs/SPEC.md`](https://github.com/LamoLanguage/LamoLanguage/blob/main/docs/SPEC.md) before changing language behavior.

<br>

<div align="center">

Released under the **[MIT License](https://github.com/LamoLanguage/LamoLanguage/blob/main/LICENSE)**

</div>
