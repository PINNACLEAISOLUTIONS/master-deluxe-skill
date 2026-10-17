# Software Engineering & Architecture Reference

## 1. Clean Code Standards
- **Single Responsibility (SRP)**: Every class, function, or module must perform exactly one conceptual job.
- **Keep It Simple (KISS)**: The simplest code that solves the problem is superior to clever abstractions.
- **You Aren't Gonna Need It (YAGNI)**: Implement only what is required right now; avoid speculative features.
- **Guard Clauses**: Use early returns for invalid conditions and edge cases to keep functions flat (maximum 2 levels of nesting).
- **Naming Intent**: Names must reveal intent without comments (e.g. `isEmailVerified`, `fetchActiveSubscribers()`, `MAX_RETRIES`).
- **Function Size**: Prefer functions between 5 and 20 lines. Keep arguments to 3 or fewer.

## 2. Test-Driven Development (TDD)
- **Red Phase**: Write a failing test that clearly expresses expected behavior and edge cases before writing code.
- **Green Phase**: Implement the minimal code necessary to make the test pass.
- **Refactor Phase**: Clean up duplicate logic, improve naming, and enforce architectural boundaries without changing external behavior.

## 3. Git & Pull Request Protocol
- **Semantic Commits**: Format commits with conventional types: `feat:`, `fix:`, `refactor:`, `docs:`, `perf:`, `chore:`.
- **Atomic Commits**: Keep commits focused on a single change.
- **Detailed Descriptions**: Document *why* the change was made, not just *what* lines were edited.
