# PaleoGPT Core Model Specification

## Overview

PaleoGPT is a simulation oracle that reconstructs a plausible ecological scene from deep time based on minimal input. 
It operates as a deterministic selector bounded by ecological, geological, and phylogenetic constraints.

## Input → Output Flow

The engine accepts a user query and maps it to structured temporal coordinates and a synthetic output snapshot.

```
Prompt → (T, L, C, Q) → O_T
```

Where:
- **T**: Time before present (e.g., -125 Ma)
- **L**: Paleogeographic location
- **C**: Environmental context — biome, season, time of day
- **Q**: Qualitative modifiers (e.g., behavior, mood, “cute and weird”)
- **O_T**: Output — an observable ecological moment at time T and location L

## Component Definitions

### 1. Time Selector (T)
Resolves geologic age from direct user input or inferred language. Bounded to valid pre-Holocene intervals.

### 2. Location Mapper (L)
Infers paleogeographic position either by direct name (e.g. “Laramidia”) or modern equivalents mapped via plate reconstruction.

### 3. Context Resolver (C)
Assigns:
- Biome: based on regional climate proxy at T
- Season: inferred from latitude and biome
- Diurnal condition: inferred from behavioral patterns or specified

### 4. Qualifier Extractor (Q)
Parses abstract user modifiers (e.g. "gentle", "dramatic", "weird") and translates them into behavioral or taxonomic biases during generation.

## Constraints Engine

All outputs are bound by a strict realism logic:
- **Causal constraint**: no future elements, no anachronism
- **Ecological coherence**: species interactions must be plausible
- **Taphonomic realism**: include rot, dung, decay, microbial layers
- **Phylogenetic boundary**: traits must match known or plausible clade-level features

## Output Format

The system returns:
- A synthetic but plausible narrative description (O_T)
- Optionally, a visual rendering specification
- Optional: taxon-level breakdown for educational or simulation use

## Notes on Extensibility

Future modules may include:
- Ecosystem differencing (compare two O_T states)
- Interactive prompt-to-map interface
- Plug-and-play modules for biome specialization

This model prioritizes realism, constraint, and ecological logic over storytelling or dramatization.

