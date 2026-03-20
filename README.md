# Supporting OWL-Style Reasoning over UML-Style Models via Endogenous OWL Overlays

## Overview
This repository contains the implementation and experimental artifacts for the research work: "Supporting OWL-Style Reasoning over UML-Style Models via Endogenous OWL Overlays." The goal of this work is to demonstrate how OWL-style reasoning can be supported for UML-style models through the use of endogenous OWL overlays. The repository provides the program files and turtle files used in the experiment along with reasoning output screenshots.

## Implementation Workflow
The implementation follows a workflow involving rule-based overlay generation and ontology reasoning.

### Step 1 – Execution of program
* The program files containing original model facts and overlay derivation rules are executed in the Nemo Graph Rule Engine.
* Output produced: Generated overlay assertions.

### Step 2 – Generation of Turtle Files
* The original model facts and generated overlay assertions are exported in Turtle format (.ttl).
* These files are used as input for ontology reasoning.

### Step 3 – Execution on Reasoner
* The generated .ttl files are loaded into Protégé with the HermiT Reasoner.
* After executing the reasoner, inferred assertions and diagnostics are produced based on the overlay semantics.

### Step 4 – Visualization of Results
* The reasoning results are provided in this repository as screenshots.
