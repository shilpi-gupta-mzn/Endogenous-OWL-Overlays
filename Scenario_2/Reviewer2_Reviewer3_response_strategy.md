# Reviewer 2 and Reviewer 3 Strategy Note

This note mirrors the structure of the Reviewer 1 strategy note. For each comment, it separates:

1. **What to say in the reviewer-response document**
2. **Whether the paper still needs to change**

The aim is not to agree with every reviewer framing, but to answer each point in a way that is calm, credible, and strategically useful for acceptance.

---

## General strategy for Reviewers 2 and 3

The strongest overall line is:

- the paper demonstrates **four representative reasoning services**, not the full extent of the architecture;
- the architecture itself is broader, and this is now discussed explicitly in the paper;
- the paper uses **LML as the concrete host notation** for a broad UML-style structural kernel, rather than claiming blanket support for all of UML;
- the current evaluation is a **scenario-based semantic validation** of the overlay/translation pipeline and prototype workflow, not a large-scale benchmark or usability study;
- the companion repository and companion scope note strengthen transparency, but the main paper itself now carries the essential scope and implementation story.

This general line can be reused across several comments below.

---

# Reviewer 2

## 18. "Better justify why the overlay approach is not meant to cover all of UML and only target a small set of OWL-style reasoning services ..."

### Recommended response-document line

We agree that the original text did not state the scope crisply enough. In the revised paper we now explain that the paper demonstrates four **representative OWL-style reasoning services** because these are the ones that most directly align with common UML/LML modelling idioms and provide actionable feedback to modellers. This should not be read as a claim that the architecture is limited to only those four services. Rather, the paper focuses on a manageable and coherent subset that can be explained and validated within the space of the article, while the broader construct coverage is discussed explicitly later in the paper and documented in the companion scope note.

We also clarify why the paper does not claim to cover all of UML. The approach is centred on a broad **UML-style structural kernel** (classes, relationships, participations, categorisations, markers, and multi-level typing), instantiated concretely in LML. This kernel is sufficient for the reasoning services demonstrated here and for a wider family of related OWL-style services, but the paper does not claim blanket support for all UML constructs.

### Does the paper need to change?

**Yes — definitely.**

#### Recommended paper changes

- In the **Introduction**, make the LML/UML-style relation explicit early: the paper uses LML as the concrete host notation for a broad UML-style structural kernel.
- In **Section 2.4**, keep the four services as the paper's focus, but say clearly that they are representative and that the broader architectural scope is discussed later.
- In **Section 7.2**, keep 3 short paragraphs that state:
  - what kinds of constructs/services the architecture directly supports,
  - how broader support is obtained (markers, normalization, local OWL carry-over),
  - where the clean RL/DL boundaries are.

This comment is one of the main reasons Section 7.2 must remain substantive.

---

## 19. "Better introduce the domain-independent overlay compilation kernel ..."

### Recommended response-document line

We agree. In the revised paper we now introduce the overlay compilation kernel more explicitly as the rule layer that aligns the basic LML structures with OWL/RDFS and compiles the intended semantics of common modelling idioms into OWL-aligned facts. We also make the modular structure clearer by distinguishing a stable kernel from the add-on modules exercised in Scenarios 2--4.

### Does the paper need to change?

**Yes — but this is a local fix, not a structural rewrite.**

#### Recommended paper changes

- In **Section 4.1 or 4.3**, add one sentence that defines the kernel plainly, e.g.:  
  *"The domain-independent overlay compilation kernel is the set of rules that maps the basic LML structures (typing, generalisation, participations, and markers) to OWL/RDFS-aligned facts and compiles the semantics of common modelling idioms into the derived overlay."*
- In **Section 4.4**, keep the current `R1`, `ΔR2`, `ΔR3`, `ΔR4` organisation, but tighten the first paragraph so it explicitly says that `R1` is the stable kernel and the deltas are add-on modules.

This is worth fixing because it helps Reviewer 2 read Section 4 as an architecture rather than as a list of examples.

---

# Reviewer 3

## 20. Positive overall evaluation; mentions Ecore/EMF, open/closed world, SHACL

### Recommended response-document line

We appreciate the reviewer’s positive assessment of the paper’s core architectural choice, namely keeping the model in one technology space by representing it as a graph and deriving an OWL view on top of it. We also agree that the relation to Ecore/EMF-style derived properties and UML/Ecore-to-OWL work should be discussed more explicitly. In the revised paper we have therefore added related-work discussion that acknowledges these connections and clarifies how endogenous overlays differ: the target is not merely platform-specific derived features, but a standards-based OWL overlay that supports both entailment-style closure and satisfiability-style diagnostics.

Regarding open versus closed world assumptions, we now make the point more clearly that the OWL reasoning step is open-world, but the authoritative source model remains available for later closed-world querying or validation by other mechanisms. We also mention SHACL as an example of a complementary validation technology rather than as part of the core contribution.

### Does the paper need to change?

**Yes — mildly.**

#### Recommended paper changes

- Keep the related-work additions on **Ecore/EMF** and **SHACL**.
- In the **open-world / closed-world** paragraph (Section 2.3), use the newer clearer wording: OWL reasoning is open-world, but the authoritative model remains available for later closed-world querying/validation.
- In the **Discussion**, mention SHACL only briefly as a complementary technology, not as something the paper now claims to integrate.

---

## 21. "Some kind of evaluation about the correctness of the translation would be important"

### Recommended response-document line

We agree that the validation target needed to be stated more explicitly. The paper’s evaluation is not intended as a large-scale benchmark, but as a semantic validation of the overlay-compilation and reasoning pipeline. In the revised manuscript we therefore make explicit that Section 6 validates whether the selected scenario models are compiled into the intended OWL-aligned facts and whether the expected reasoner consequences or diagnostics are obtained. This is the main sense in which correctness is evaluated in the present paper.

### Does the paper need to change?

**Yes.**

#### Recommended paper changes

- In **Section 6.1**, say explicitly that the evaluation target is the semantic correctness of the compilation pipeline and the resulting reasoning outputs.
- Keep a compact validation table (or equivalent prose) showing for each scenario:
  - source idiom,
  - representative exported overlay content,
  - expected consequence.

This is one of the most useful paper changes because it answers both Reviewers 1 and 3.

---

## 22. "Scalability and applicability ... should be discussed"

### Recommended response-document line

We agree that scalability and broader applicability are important, but we do not claim that the current paper provides a full empirical scalability study. We now make that explicit. The revised paper positions the current evaluation as scenario-based semantic validation and discusses scalability/applicability as a limitation and future-work issue, rather than leaving the reader to infer a broader empirical claim than intended.

### Does the paper need to change?

**Yes — briefly.**

#### Recommended paper changes

- Add 1 short paragraph in **Section 6** or **Section 7.4** stating that:
  - no large-scale benchmark is claimed,
  - the present work validates architectural and semantic feasibility,
  - larger model corpora and scalability measurement are future work.

No more than one paragraph is needed.

---

## 23. "Title and intro framed about UML/UML-like, but core centered on LML ... should already describe this focus more clearly"

### Recommended response-document line

We agree. The revised paper now states more explicitly that LML is the concrete host notation used in the paper, while the architectural claim is about a broad UML-style structural kernel rather than blanket support for all UML constructs. This is also why some UML features that are not needed for the demonstrated services are not part of the current metamodel fragment.

### Does the paper need to change?

**Yes — definitely.**

#### Recommended paper changes

- In the **Abstract**, avoid introducing LML by acronym, but make clear that the representation follows a multi-level modelling style.
- In the **Introduction**, explicitly say that LML is the concrete host notation used for the paper.
- In the **Background/Discussion**, state clearly that the paper does not claim support for all UML constructs and that LML is used because mainstream UML does not provide a robust general basis for multi-level modelling.

This point now intersects with Reviewer 1 comment 11, so the wording should be coordinated.

---

## 24. Ecore/EMF patterns and readonly derived properties; what can be manipulated after transfer back?

### Recommended response-document line

We agree that the paper should say more clearly how the approach differs from platform-specific derived features. In the revised manuscript we now discuss Ecore/EMF-style derived properties in related work and clarify that overlay-generated or reasoner-inferred consequences are analysis results by default. Fold-back is optional and selective rather than automatic. In particular, not every derived consequence must be treated as an editable first-class model element; whether and how derived results become explicit commitments in the source model is a tool and workflow decision.

### Does the paper need to change?

**Yes — slightly.**

#### Recommended paper changes

- In **Related Work**, keep the Ecore/EMF discussion.
- In **Section 4.6** or **the observations at the end of Section 5**, add one short sentence saying that fold-back is selective and modeller-controlled, and that the paper does not claim every derived result automatically becomes a mutable source-model element.

---

## 25. "You directly start with having the UML models as triples ... many UML models are stored as XMI/XML"

### Recommended response-document line

We agree that the paper should be explicit here. The approach does not assume that UML tools natively store models as RDF triples. Rather, the current model snapshot is exposed as a neutral triple-based base graph for reasoning purposes. This graph can be obtained from the underlying modelling environment, regardless of whether the tool stores its models internally in XMI, XML, or another format. The point of the paper is not that all UML tools already use triples, but that the reasoning workflow operates over a neutral graph representation once the snapshot has been exposed in that form.

### Does the paper need to change?

**Yes — this is worth making explicit.**

#### Recommended paper changes

- In **Section 4.1 or 4.2**, add a sentence such as:  
  *"The base graph is an internal neutral representation of the current model snapshot; it is not a claim about the storage format used by all UML tools."*

This directly answers the reviewer and costs almost no space.

---

## 26. "The evaluation section ... is not providing how you actually validated the pipeline / for which models"

### Recommended response-document line

We agree. In the revised manuscript we now state explicitly that the evaluation uses the running example together with the scenario-specific model fragments and extensions shown in Section 5. The purpose is to validate that the translation pipeline produces the intended OWL-aligned overlay content and the expected reasoning outcomes for each of the four targeted services. We do not claim that this constitutes a broad model-corpus study.

### Does the paper need to change?

**Yes.**

#### Recommended paper changes

- In **Section 6.1 or 6.2**, state explicitly that the validation uses:
  - the FHKB-derived running example,
  - plus the scenario-specific simplified/extended fragments shown in the storyboards.
- Make clear that this is a semantic validation of the pipeline, not a large model survey.

This comment is closely related to point 21 and can be handled together.

---

## 27. "Could you provide the tool support for the community?"

### Recommended response-document line

Yes. In response to this comment, we now provide a companion repository containing the prototype artefacts corresponding to the four scenarios, including the exported overlays and the reasoner outputs. The paper also now names the concrete tools used in the current prototype workflow.

### Does the paper need to change?

**Yes — but minimally.**

#### Recommended paper changes

- In **Section 6.1**, mention Nemo and HermiT explicitly (as already planned).
- Add one short sentence pointing to the companion repository, if you decide that the public link is appropriate for this review round.

---

## 28. "Is the linguistic metamodel presented in Figure 2 the metamodel of the LML language?"

### Recommended response-document line

Yes. We now make explicit that Figure 2 presents the relevant fragment of the linguistic metamodel that underlies the LML notation used in the paper. The figure is intentionally partial: it is the fragment needed for the current scenarios, not the full language definition.

### Does the paper need to change?

**Yes — trivially.**

#### Recommended paper changes

- Update the **Figure 2 caption** and/or the first sentence that introduces it so that it explicitly says:  
  *"Figure 2 shows the relevant fragment of the linguistic metamodel underlying the LML notation used in this paper."*

This is a very cheap fix and definitely worth making.

---

# Recommended overall position for Reviewers 2 and 3

Compared with Reviewer 1, these two reviewers can be satisfied more easily if the manuscript does the following consistently:

1. **State clearly that the paper uses LML as the concrete host notation** for a broad UML-style structural kernel.
2. **State clearly that the four scenarios are representative demonstrations**, not the whole architecture.
3. **Say explicitly what the evaluation validates** and what it does not claim.
4. **Clarify the prototype workflow and name the tools.**
5. **Keep the broader scope discussion in the paper**, but concise and disciplined.
6. **Use the companion repository and scope note as support**, not as substitutes for core argument.

---

# Practical priority list

## Must change in the paper
- 18 / 23: scope + LML/UML-style framing
- 21 / 26: evaluation target clarified
- 25: base graph is a neutral representation, not assumed native storage
- 27: name the tools and optionally point to repo
- 28: make Figure 2 explicit

## Should change in the paper
- 20 / 24: Ecore/EMF + fold-back clarification
- 22: one concise scalability/applicability paragraph

## Can mostly be handled in the response document
- the more ambitious parts of 18 and 20 that would otherwise bloat the paper

