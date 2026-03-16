# Supporting OWL-Style Reasoning over UML-Style Models via Endogenous OWL Overlays

## Overview
This repository contains the implementation and experimental artifacts for the research work: "Supporting OWL-Style Reasoning over UML-Style Models via Endogenous OWL Overlays." The goal of this work is to demonstrate how OWL-style reasoning can be supported for UML-style models through the use of endogenous OWL overlays. The repository provides the program files, generated overlay assertions, reasoning inputs, and result screenshots used in the experiments.

## Implementation Workflow
The implementation follows a multi-step reasoning workflow involving rule-based overlay generation and ontology reasoning.

### Step 1 – Original Model Facts
* Each program file contains facts extracted from the original UML-style model.
* These facts represent the base model elements that serve as input to the reasoning process.

### Step 2 – Overlay Derivation Rules
* Overlay derivation rules are defined to generate OWL-style overlay assertions.
* These rules are executed using the Nemo Graph Rule Engine.
* The rules transform the original model facts into overlay assertions that enable OWL-style reasoning.

### Step 3 – Execution in Nemo
* The program files containing original model facts and overlay derivation rules are executed in the Nemo Graph Rule Engine.
* Output produced: Generated overlay assertions.

### Step 4 – Generation of Turtle Files
* The original model facts and generated overlay assertions are exported in Turtle format (.TTL).
* These files are used as input for ontology reasoning.

### Step 5 – Reasoning in Protégé
* The generated .ttl files are loaded into Protégé with the HermiT Reasoner.
* After executing the reasoner, inferred assertions and diagnostics are produced based on the overlay semantics.

### Step 6 – Visualization of Results
* The reasoning results are shown as inferred assertions and diagnostics, which are provided in this repository as screenshots.
