# TLOS

This repository contains the official documentation for detailing the official LevelZ Standard.

## Definitions

This documentation references several concepts that both link into one another, and are relevant to proper usage of the LevelZ File Format. This will cover a short list of definitions that are **outside** of the scope of the LevelZ File Format itself.

- "Bindings"
  - "Bindings" refer to the interpretation of a `.lvlz` file or file content by any software program. They can be implemented in any language or program developers choose.
  - The LevelZ File Format, and by proxy Calculus Games, maintains official bindings in various programming languages. These bindings are held to a specific standard outlined in this document.
  - However, unofficial bindings in same, similar, or different programming languages or programs are allowed to deviate from official bindings standards, unless explicitly stated that said behavior violates the overall standard.

## Contributing

All LevelZ propositions must be correctly authored by the propositioner, reviewed by a proper authority, and submitted in the correct position. They must be well-docmented, with the submission being in grammatical English.

We prioritize **readability**, **flexibility**, and **efficiency** in the LevelZ Official Standard. Good propositions should reflect these three core values. Markdown must meet the standards found in the [.mdlrc](/.mdlrc) file when ran through `markdownlint`.

Files should contain authors first and last name (or online alias if wished to be remain anonymous), a synopsis detailing the standard, at least one example of correct usage, and at least two examples of incorrect usage with reasonings and severity level. "Severity Level" is defined as `soft warning`, `warning`, or `error`.

- A `soft warning` represents a standard that is lightly encouraged by the LevelZ File Format primarily for aesthetic or non-functionality related reasons, but is not widely enforced.
- A `warning` represents a standard that is encouraged by the LevelZ File Format primarily for functionality related reasons, but is not necessary for full functionality and less widely enforced.
- A `error` represents a rule that is critical to the correct parsing of a `.lvlz` file by official bindings.

## About

LevelZ is an official property of the Calculus Games organization, open-sourced to the public. Therefore, all iterations for its development must be approved by the Calculus Games organization, or an entity that has been granted permission (such as an outside administrator of the LevelZ File Format organization).

Permission is granted to all persons to be used both in public and private, at anytime, for personal and commercial use, free of charge, to be modified and distributed in any format, as long as any published modifiations are not associated with the Calculus Games or LevelZ brand, unless granted permission thereof.

Calculus Games reserves the right to create, revise, iterate, or delete propositions, features, and improvements to the officially recognized LevelZ File Format language for any reason, excluding reasons that are unlawful or are against company interests.
