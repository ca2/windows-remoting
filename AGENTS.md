# Repository instructions

## C/C++ line endings on Windows

- When editing `*.c++`, `*.cc`, `*.cpp`, `*.cppm`, `*.cxx`, `*.h`, `*.h++`, `*.hh`, `*.hpp`, `*.hxx`, `*.inl`, `*.ipp`, `*.ixx`, `*.tlh`, or `*.tli` files on Windows, preserve or write CRLF line endings.
- After applying a patch to any of those files on Windows, normalize only the touched C/C++ files back to CRLF before handing off the change.
- Do not bulk-convert unrelated files or change their line endings.

## Prefer ca2 facilities over STL

- Prefer existing ca2 types, containers, algorithms, ownership mechanisms, synchronization primitives, and other platform facilities over STL equivalents when a suitable ca2 alternative is available. For example, use the appropriate ca2 array type instead of `::std::vector`.
- Before introducing an STL dependency, inspect the relevant ca2 APIs and existing usage in the source tree. Choose the ca2 alternative when it preserves the required behavior, correctness, performance, and Windows/ReactOS compatibility.
- If no suitable ca2 equivalent exists, or a related ca2 facility cannot be used, explain the specific gap or limitation and suggest creating or extending a reusable ca2 equivalent where appropriate. Do not force an unsuitable replacement or introduce a new abstraction merely to avoid STL.
- When STL remains necessary, keep its use narrowly scoped and explain why the available ca2 facilities do not meet the requirement.

## Use descriptive source-code identifiers

- Avoid using `ca2`, `Ca2`, or `CA2` as a prefix, suffix, or other qualifier in source-code identifiers, including variables, functions, types, members, and macros. These qualifiers are redundant and can cause naming collisions.
- Name identifiers for their purpose, behavior, or domain. When a name needs disambiguation, use a more specific descriptive term or underscores rather than a `ca2`/`CA2` qualifier.
- Retain `ca2`/`CA2` where required in project or namespace names, file paths, comments, and externally defined API names; this guidance concerns source-code identifiers.
