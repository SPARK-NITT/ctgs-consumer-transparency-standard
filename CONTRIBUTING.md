# Contributing to Spark-CTGS

Thank you for your interest in improving the Consumer Transparency Governance
Standard (CTGS). This repository hosts the canonical text, implementation
notes, and supporting materials for CTGS v1.0.

Because CTGS is a governance standard, changes must be careful, well-documented,
and traceable.

---

## 1. Types of contributions

You can contribute by:

- Proposing clarifications or corrections to the CTGS text
- Suggesting additional examples or scenarios
- Adding or refining schemas (e.g., CTGS harm-pattern records)
- Improving documentation and explanatory materials
- Adding non-intrusive tooling (tests, helpers, scripts)

For questions or early ideas, please open an Issue rather than a Pull Request.

---

## 2. Working with versions

CTGS v1.0 is an immutable release once hashed and notarized.

- Changes that alter the meaning of the standard **must** be part of a
  versioned update (for example, v1.1 or v2.0).
- Non-normative additions (e.g., extra examples, additional docs, schemas)
  may be accepted without changing the CTGS v1.0 core, as long as they are
  clearly marked as non-normative.

The file `HASHES.md` and the associated notarization record (`NOTARIZATION.md`)
describe the integrity chain for the current canonical release.

---

## 3. Pull request guidelines

Before opening a pull request:

1. Open an Issue describing what you want to change and why.
2. Reference specific files and sections (for example:
   `Standard_v1.0.md`, section "Rights").
3. Indicate whether your change is:
   - Normative (changes the standard itself)
   - Non-normative (examples, commentary, or tooling)

When opening a PR:

- Keep changes focused and minimal.
- Include a short summary in the PR description.
- Link to the Issue you are addressing.
- Do not update `HASHES.md` or `NOTARIZATION.md` unless the maintainers
  agree that a new integrity cycle is being created.

---

## 4. Style and tone

CTGS documents should:

- Use clear, neutral language suitable for legal, regulatory,
  and engineering audiences.
- Avoid marketing and speculative claims.
- Align with the existing terminology used in CTGS v1.0.

Code and scripts should:

- Prefer clarity over cleverness.
- Include basic tests where appropriate.
- Avoid unnecessary dependencies.

---

## 5. License and attribution

By contributing to this repository, you agree that:

- Text and documentation contributions are licensed under **CC BY 4.0**.
- Code contributions are licensed under the **MIT License**.

See `LICENSE` and `LICENSE-CC-BY-4.0.md` for details.

---

## 6. Getting help

If you are unsure whether your idea fits, open an Issue with a short proposal:

- What you want to add or change
- Why it matters for consumer transparency
- Whether it is normative or non-normative

Maintainers will help you determine the right path forward.
