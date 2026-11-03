# CSS architecture: controlled change

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

A small documented component library.

## Lesson and lab

Treat shared styles as an interface. A token rename or changed component selector can break many screens even when the stylesheet compiles.

Create a change proposal for replacing a spacing scale: identify affected components, introduce new tokens, migrate consumers, and remove old tokens after searching for references. Use cascade layers only after documenting their ordering; unlayered normal declarations can override layered normal declarations unexpectedly.

Compare CSS Modules, utility classes, and runtime styling using actual project needs: isolation, theme variation, output size, and debugging. Measure before adding abstractions. Provide a migration plan and a rollback diff.

Review visual regressions on representative screens with fixed fonts, viewport, and data. Inspect intentional differences rather than automatically accepting snapshots. Keep semantic and keyboard checks alongside visual checks. Extension: document which component changes are backward compatible and which require consumer migration.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
