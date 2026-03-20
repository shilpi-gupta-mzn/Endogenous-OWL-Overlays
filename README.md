# Supporting OWL-Style Reasoning over UML-Style Models via Endogenous OWL Overlays

## Overview
This repository contains the implementation and experimental artifacts for the research work titled "Supporting OWL-Style Reasoning over UML-Style Models via Endogenous OWL Overlays."

The objective of this work is to demonstrate how OWL-style reasoning can be effectively applied to UML-style models through the use of endogenous OWL overlays. The repository includes program files, generated Turtle files, and screenshots illustrating the reasoning results obtained during the experiments.

## Implementation Workflow
The implementation follows a structured workflow consisting of rule-based overlay generation and ontology reasoning.

### Step 1 – Program Execution
* The program files, which include the original model facts and overlay derivation rules, are executed using the Nemo Graph Rule Engine.
* Output: Generated overlay assertions.
  
### Step 2 – Turtle File Generation
* The original model facts and the generated overlay assertions are exported in Turtle (.ttl) format.
* These files serve as input for the ontology reasoning process

### Step 3 – Reasoning Process
* The generated Turtle files are loaded into Protégé and processed using the HermiT Reasoner.
* The reasoner produces inferred assertions and diagnostic results based on the defined overlay semantics.

### Step 4 – Result Visualization
* The reasoning outcomes are documented and provided in this repository in the form of screenshots.
