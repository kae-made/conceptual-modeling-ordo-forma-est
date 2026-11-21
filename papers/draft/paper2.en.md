# Category-Theoretic Foundations of Dynamic Modeling: State Transitions, Data-Flow Action Models, Universal Execution Semantics, and Isomorphism with Physical Field Theories

## Abstract
In my preceding papers (Paper 0 and Paper 1) \cite{ota2026paper0,ota2026paper1}, I established an ontology grounded in relations (span structures) rather than isolated objects, formalized a Universe partitioned into multiple "Fields of Sense" connected by "Bridges," and proved that the static semantic structure of a single Field of Sense (the Conceptual Information Model) is rigorously represented as a finitely complete and finitely cocomplete quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$. Given that the conceptual information model provides the necessary and sufficient formal conditions for static existence, state changes occurring over that domain (state models and action models) must likewise be formulated upon the conceptual information model. However, merely specifying state transitions and actions leaves them inert; rigorous constraints governing how they causally transition (execute) without contradiction—namely, **Execution Semantics**—are indispensable.

The present paper (Paper 2) formalizes dynamic behavior (Dynamics) arising over a static schema category $\mathcal{C}$ in category-theoretic terms and proves four foundational propositions. First, **execution semantics can be defined universally and uniquely upon the abstract form of the conceptual information model itself ($\mathcal{C}_{\mathrm{FORM}}$), without inspecting the domain-specific business or physical semantics of any individual Field of Sense** (Universal Execution Semantics Theorem). Second, data-flow action models constructed as directed acyclic graphs (DAGs) from primitive process components, together with their **formal textual syntax (Action Language)** and external boundary interfaces (**Domain Functions**), form a **homotopically closed symmetric monoidal category ($\mathcal{DF}$)** equipped with sequential and parallel composition, and preserve all static schema invariants along any regular execution trajectory that avoids singularities (`Can't Happen` transitions or division by zero collapsing to the initial object $0$). Third, in exact symmetry with the static domain (Paper 1), this dynamic formalism satisfies **dynamic expressive completeness, categorical isomorphism across representational variations, and asymptotic convergence under cognitive finitude via abduction**, while also capturing **continuous dynamics without information loss** through projective limits and sheaf gluing of boundary-condition aspects. Fourth, **the integrated modeling architecture—comprising the Conceptual Information Model, State Model, Action Model, Domain Functions, and Universal Execution Semantics—is mathematically isomorphic to the formal structure of physical field theories** (configuration space, phase space with singularities, equations of motion, boundary conditions/external forces, and universal principles of time evolution and causality).

---

## 1. Introduction

### 1.1 Background and Problem Statement: From Static Structural Skeletons to State Transitions and Universal Execution Semantics
In my preceding papers, starting from an ontology in which relations (span structures) rather than standalone objects ("things") serve as the primary substrate of reality, I formalized how the world is partitioned into a Universe $\mathcal{U}$ comprising multiple "Fields of Sense" connected via "Bridges" (Paper 0) \cite{ota2026paper0}, and proved that the static semantic structure of a single Field of Sense (the Conceptual Information Model) exists constructively as a quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$ satisfying expressive completeness, existence, categorical isomorphism, and asymptotic convergence (Paper 1) \cite{ota2026paper1}.

Paper 1 established the "static form of existence (structural skeleton)" within a single Field of Sense. Since the conceptual information model provides the necessary and sufficient formal conditions for meaningful static existence, models describing state changes over that domain (state models and data-flow action models) must necessarily be formulated upon the conceptual information model (schema category $\mathcal{C}$). The causal chain in which new individual instances are created, existing instances transition across states, semantic links are reconfigured, and instances eventually terminate is formalized in functorial semantics as a structure-preserving transition from an instance functor $\mathcal{F}_n \in \mathrm{Valid}(\mathcal{C})$ at step $n$ to $\mathcal{F}_{n+1} \in \mathrm{Valid}(\mathcal{C})$ at step $n+1$.

**Remark 1.1 (Exclusion of Spacetime from Pure Conceptual Models and Terminological Convention):**
Within the pure mathematical formalism of conceptual information models, state models, and action models, there exists no *a priori* coordinate system of physical "time" or "space." What exists internally is solely structural linkage via relations (spans) and the causal partial order of state transitions induced by events ($\mathcal{F}_n \to \mathcal{F}_{n+1}$). Accordingly, Sections 2–4 formulate dynamic models without presupposing physical spacetime, using terms such as "transition step" or (purely for expository convenience) "chronological sequence / temporal evolution" to denote causal ordering. Physical time enters only externally as "timer events" supplied by the external entity $\mathcal{EE}_{\mathrm{Time}}$, and correspondence with physical spacetime and physical field theories is established explicitly in Sections 5.5 and 5.6.

However, merely specifying state transitions and actions renders a model meaningless. Unless constraints are given governing how static and dynamic models behave—that is, in what causal order and under what execution rules they evolve—the behavior of the model remains undetermined; without execution semantics, a specified model is merely a blueprint on paper. Crucially, **execution semantics need not inspect the concrete semantic content of any individual Field of Sense (whether commercial or physical); it can be defined universally upon the formal structure of the conceptual information model, state model, and action model itself ($\mathcal{C}_{\mathrm{FORM}}$)**.

Furthermore, any theory purporting to describe the real world must recognize that **models containing internal singularities—such as `Can't Happen` transitions, division by zero, or out-of-bounds domain operations that collapse to the initial object $0$ (empty space)—must be admitted as valid model specifications**. In real-world business and social domains, due to the cognitive finitude of modelers (specifiers), it is reasonable to recognize that countless operational models run in production while harboring latent structural defects (singularities) that have simply not yet been triggered, but will cause organizational or system breakdown the moment the fatal event sequence occurs. Likewise, in physical Fields of Sense, reaching the boundary of an equation's domain of definition (a singularity) manifests as a **phase transition**, where the current schema category collapses and the system transitions into a distinct Field of Sense governed by a new schema. By admitting singularities (morphisms into $0$) as legitimate structural components rather than artificially banning them, this framework faithfully captures the real world—including breakdowns and phase transitions—rather than an idealized toy universe.

### 1.2 Four Foundational Questions in Dynamic Modeling
Based on this problem setting, the present paper (Paper 2) provides affirmative mathematical answers to four foundational questions:

1. **Expressive Completeness, Isomorphism, Asymptotic Refinement, and Discrete Representation of Continuous Dynamics:** In symmetry with the static domain (Paper 1), can the formalism of **state models** (comprising active/final states and `Ignore`/`Can't Happen` singularities) coupled with **data-flow action models** built from primitive process components adequately represent every computable and realistic state evolution and concurrent process (Dynamic Expressive Completeness)? Moreover, do distinct representations reduce to categorical equivalence (Isomorphism), can finite human minds asymptotically converge to the true dynamic model via abduction, and can projective limits and sheaf gluing of boundary-condition aspects capture continuous dynamics without information loss?
2. **Isomorphism between Formal Textual Syntax and Diagrammatic Representation:** Can data-flow action models be expressed not only as visual string diagrams, but also via a rigorous context-free textual grammar (Action Language) that is categorically isomorphic to the diagrammatic representation (Syntax–Semantics Isomorphism)?
3. **Universal Execution Semantics and Homotopical Monoidal Closure:** When universal execution semantics is defined solely over the abstract form of the conceptual information model, state model, and action model ($\mathcal{C}_{\mathrm{FORM}}$) without inspecting domain-specific content, do state transitions, data-flow actions, and domain functions close consistently as a **homotopically closed symmetric monoidal category ($\mathcal{DF}$)** equipped with sequential ($\circ$) and parallel ($\otimes$) composition, while preserving all static schema invariants along any singularity-free regular execution trajectory?
4. **Structural Isomorphism with Physical Field Theories:** Is the entire modeling architecture—comprising the Conceptual Information Model (configuration space), State Model (phase space and singularities), Action Model (equations of motion), Domain Functions (boundary conditions and external forces), and Universal Execution Semantics (universal laws of time evolution and causality)—mathematically isomorphic to the formal structure of physical theories containing equations of motion?

### 1.3 Paradigm Shift and Structure of This Paper
In conventional object-oriented programming (OOP), systems are typically designed by encapsulating data and behavior (methods) inside individual objects and chaining synchronous method calls. However, under a relation-based ontology (Paper 0 and Paper 1), invariants such as multiplicities and referential integrity are defined not locally inside a single instance, but globally across the entire Field of Sense ($\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$). Consequently, organizing actions attached to target states as atomic transformations updating the entire Field of Sense ($\mathcal{F}_n \to \mathcal{F}_{n+1}$) is a mathematical necessity for preserving relational consistency (a category-theoretic elevation of the Shlaer–Mellor method and Executable UML \cite{shlaer1992,mellor2002}).

The remainder of this paper is organized as follows:
* **Section 2 (Category-Theoretic Formalization of State Models and Object Lifecycles)** formalizes typed events grounded in $\mathcal{C}$ (creation events, instance events, and timer events, together with supplemental data), state machines held by every instance, active and final states, `Ignore` (identity morphisms) and `Can't Happen` singularities, Moore normal form actions, and the isomorphism between event-driven execution semantics (with timer event binding and self-event priority) and local inertial frames (proper time and light-cone causality).
* **Section 3 (Data-Flow Action Models, Formal Textual Syntax, and the Symmetric Monoidal Category $\mathcal{DF}$)** derives the 16 orthogonal primitive process components uniquely from Paper 1, defines the formal textual syntax (New OAL / SSA grammar) and proves its isomorphism with acyclic string diagrams, establishes termination via acyclicity (DAG), and defines **Domain Functions** as external boundary interfaces connecting Bridges (Paper 0) and Transformations (Paper 3).
* **Section 4 (Universal Execution Semantics and Boundary-Condition Aspects)** defines Universal Execution Semantics over the form category $\mathcal{C}_{\mathrm{FORM}}$ via four axioms (including aspect pullbacks $\mathcal{M} \times_{\mathcal{C}_{\mathrm{FORM}}} \mathcal{V}$), proving dynamic invariant preservation along regular trajectories and characterizing breakdown and phase transitions at singularities.
* **Section 5 (Meta-Theorems of Dynamic Modeling, Discrete Representation of Continuous Dynamics, and Isomorphism with Physical Field Theories)** proves the four dynamic meta-theorems (completeness, homotopical monoidal existence, isomorphism, and asymptotic convergence), the discrete representation theorem for continuous dynamics via projective limits and sheaves, and the isomorphism theorem with physical field theories.

* **Section 6 (Practical Implications and Conclusion)** discusses practical implications for executable modeling (including AI code verification) and outlines the transition to structural transformations with Green's function isomorphism (Paper 3) and the universal ontology of conceptual modeling encompassing the holographic principle (Paper 4).

---

## 2. Category-Theoretic Formalization of State Models and Object Lifecycles

### 2.1 Typed Events Grounded in the Static Schema Category $\mathcal{C}$
In my preceding paper (Paper 1) \cite{ota2026paper1}, I proved that the static semantic structure (the form of existence) of a single Field of Sense is adequately and necessarily governed by a quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$ equipped with conceptual classes, seven strictly closed data types, monic identifiers, bidirectional relationships bearing four multiplicities and semantic phrases, exclusive coproduct decompositions (`Is-a`), and associative classes. Since semantic structure is governed by the conceptual information model, state changes ("Dynamics") occurring over that domain must likewise be formulated upon the conceptual information model.

Inputs that trigger state changes are defined as **Events** belonging to conceptual classes.

**Definition 2.1 (Typed Event Spaces and Supplemental Data)**
For each conceptual class $A \in \mathcal{K}$ in the schema category $\mathcal{C}$, a finite set of event labels $\mathcal{E}_A$ triggering state transitions on instances of $A$ is defined. Each event $e \in \mathcal{E}_A$ is partitioned exclusively into two disjoint subsets according to the existential status of its target entity:
$$\mathcal{E}_A = \mathcal{E}_A^{\mathrm{create}} \sqcup \mathcal{E}_A^{\mathrm{inst}}$$
1. **Creation Events ($e \in \mathcal{E}_A^{\mathrm{create}}$):** Events that instantiate a new entity not yet present in the Field of Sense. Because no target individual exists prior to execution, creation events carry no target identifier, carrying solely the supplemental data required to enter an initial state and initialize property values.
2. **Instance Events ($e \in \mathcal{E}_A^{\mathrm{inst}}$):** Events directed at a specific existing individual $a \in \mathcal{F}_n(A)$ already present in the Field of Sense. They carry an identifier value $\mathcal{F}_n(\alpha_I)(a)$ (Paper 1, Axiom C-1) to uniquely resolve the target individual, together with event-specific supplemental data.

**Supplemental Data and Input Connection to Action Models:**
For every event $e \in \mathcal{E}_A$, the argument tuple $\mathbf{d} \in \prod_{j=1}^m \mathcal{F}(T_j)$ carried by the event is defined as **Supplemental Data** strictly typed by the exact same static data-type space $\mathcal{D}_{\mathrm{static}}$ as the conceptual information model (Paper 1, Section 2.5) (a pure signal event carrying no data corresponds to the empty product $m=0$, i.e., the monoidal unit $I$). The moment event $e$ determines a target state $s' \in \Sigma_A$, this supplemental data $\mathbf{d}$ is fed directly as the **initial input data-flow wires (boundary input resources)** into the data-flow action model $\mathcal{A}_{s'}$ (Section 3) attached to state $s'$ (when multiple distinct events transition into the same target state $s'$, the input signature accepted by $\mathcal{A}_{s'}$ is uniquely constrained to the common data-type tuple shared across all incoming events).

Furthermore, the passage of time itself is not an external absolute clock forcibly driving entities in lockstep; rather, it is supplied by the external entity $\mathcal{EE}_{\mathrm{Time}}$ as **Timer Events ($e_{\mathrm{time}} \in \mathcal{E}_A^{\mathrm{inst}}$)** bound to individual instances on completely equal footing with domain or physical events.

---

### 2.2 State Machines Held by Every Instance and Lifecycles (Persistence and Termination)
In Paper 1 (Proposition 2.1: Category of Elements $\int \mathcal{F}$), a conceptual class $A \in \mathcal{K}$ was formalized as the existential template for individual instances $a \in \mathcal{F}(A)$. From this type–instance correspondence, whenever a state model governing state-transition rules is defined for conceptual class $A$, it follows as a direct logical consequence that **every individual instance instantiated from $A$ possesses its own independent state machine**.

**Definition 2.2 (Conceptual Class State Models and Exclusive Coproduct State Spaces)**
Each conceptual class $A \in \mathcal{K}$ is equipped with a deterministic state model serving as the behavioral template for its instances:
$$M_A = \left(\Sigma_A,\, \mathcal{E}_A,\, \delta_A,\, \{\mathcal{A}_s\}_{s \in \Sigma_A}\right)$$
The finite state set $\Sigma_A$ is partitioned as a disjoint union of two mutually exclusive subsets according to the existential outcome of the instance after transition:
$$\Sigma_A = \Sigma_A^{\mathrm{active}} \sqcup \Sigma_A^{\mathrm{final}}$$
1. **Active / Persistent States ($s \in \Sigma_A^{\mathrm{active}}$):** States in which the instance $a$ continues to exist in $\mathcal{F}_{n+1}(A)$ after transition and action completion, remaining receptive to subsequent events.
2. **Final / Deletion States ($s \in \Sigma_A^{\mathrm{final}}$):** Terminal states upon whose entry and accompanying action completion the instance $a$ is removed from the Field of Sense ($\mathcal{F}_{n+1}(A) = \mathcal{F}_n(A) \setminus \{a\}$).

*(Note: Static conceptual classes that undergo no state transitions throughout their lifecycle are uniformly treated as trivial state models possessing a single active state $\Sigma_A = \Sigma_A^{\mathrm{active}} = \{\star\}$.)*

**Proposition 2.1 (Universal Instance State Machines and Causal Coproduct Exclusivity)**
Every instance $a \in \mathcal{F}_n(A)$ manifesting in a Field of Sense from conceptual class $A \in \mathcal{K}$ maintains its own independent instance state machine templated by $M_A$. Dual to `Is-a` relationships in Paper 1—which enforce spatial coproduct exclusivity ($S \cong \coprod C_i$)—at any local causal stage, instance $a$ cannot split across multiple states, occupying strictly one current state $\sigma(a) \in \Sigma_A^{\mathrm{active}}$. Moreover, an entity instantiated via a creation event $e \in \mathcal{E}_A^{\mathrm{create}}$ enters an initial state $s_0 \in \Sigma_A$; if $s_0 \in \Sigma_A^{\mathrm{final}}$, it terminates immediately upon completing its creation action (modeling transient event instances).

---

### 2.3 Algebraic Structure of State Transition Tables (STT): `Ignore` and Singularities (`Can't Happen`)
The behavior upon event arrival in every state is exhaustively specified by the state transition function (State Transition Table, STT).

**Definition 2.3 (State Transition Function and Category-Theoretic Definition of `Ignore` and `Can't Happen`)**
The state transition function $\delta_A$ of conceptual class $A \in \mathcal{K}$ consists of creation transitions $\delta_A^{\mathrm{create}} : \mathcal{E}_A^{\mathrm{create}} \to \Sigma_A \sqcup \{\mathrm{Can't\ Happen}\}$ and instance transitions:
$$\delta_A : \Sigma_A^{\mathrm{active}} \times \mathcal{E}_A^{\mathrm{inst}} \longrightarrow \Sigma_A \sqcup \{\mathrm{Ignore},\; \mathrm{Can't\ Happen}\}$$
In addition to standard state transitions $s \to s' \in \Sigma_A$, two special outcomes are rigorously defined in algebraic and topos-theoretic terms:
1. **`Ignore` (Event Ignored = Identity Morphism $\mathrm{id}$):** When event $e$ arrives at instance $a$ in state $s$, no state change or action execution occurs, leaving the entire Field of Sense unchanged. Category-theoretically, this maps to the **identity morphism ($\mathrm{id}_{\mathcal{F}}$)** on the state space.
2. **`Can't Happen` (Impossible Transition = Collapse to Initial Object $0$ / Singularity):** Expresses a structural prohibition stating that event $e$ cannot logically arrive at instance $a$ while in state $s$. Category-theoretically—in exact analogy with "nonsense" and division by zero or out-of-bounds operations in Paper 1—this is defined as a **collapse morphism into the initial object $0$ (empty space / contradiction)** of the internal topos logic.

**Remark 2.1 (Legitimate Inclusion of Singularities and Breakdown Boundaries in Real-World Models)**
Crucially for any theory describing the real world, **models containing internal singularities such as `Can't Happen` transitions or division by zero (morphisms into the initial object $0$) must be admitted as valid model specifications**. In real-world business and social domains, due to the cognitive finitude of modelers, countless operational models run in production while harboring latent structural defects (singularities) that simply have not yet been triggered, but will cause organizational or system breakdown the moment the fatal event occurs. Likewise, in physical Fields of Sense, reaching the domain limit of a state equation (a singularity) manifests as the critical boundary of a **phase transition**, where the current schema category collapses and the system transitions into a distinct Field of Sense governed by a new schema. Admitting singularities (morphisms into $0$) as legitimate components enables this framework to capture the real world—including breakdowns and phase transitions—rather than an idealized closed toy system.

---

### 2.4 Global State Updates via Moore Normal Form Actions and Isomorphism with Local Inertial Frames
Once the arrival of event $e$ determines the target state $s' \in \Sigma_A$ for instance $a$, the data-flow action model $\mathcal{A}_{s'}$ (formalized in Section 3) attached to state $s'$ is invoked.

**Definition 2.4 (Global Field-of-Sense Updates via Moore Normal Form Actions)**
The action $\mathcal{A}_{s'}$ accompanying a state transition $s \xrightarrow{e(\mathbf{d})} s'$ receives the event's supplemental data $\mathbf{d} \in \prod_{j=1}^m \mathcal{F}_n(T_j)$ as its initial input data-flow wires and acts not merely as a local mutation of instance $a$'s internal variables, but as an **atomic morphism updating the entire instance functor $\mathcal{F}_n \in \mathrm{Valid}(\mathcal{C})$ of the Field of Sense to the next state $\mathcal{F}_{n+1} \in \mathrm{Valid}(\mathcal{C})$**:
$$\llbracket \mathcal{A}_{s'} \rrbracket : \mathrm{Valid}(\mathcal{C}) \times \prod_{j=1}^m \mathcal{F}_n(T_j) \longrightarrow \mathrm{Valid}(\mathcal{C})$$
(For events carrying no supplemental data, $\prod_{j=1}^m \mathcal{F}_n(T_j) \cong \mathbf{1}$, reducing to $\llbracket \mathcal{A}_{s'} \rrbracket : \mathrm{Valid}(\mathcal{C}) \to \mathrm{Valid}(\mathcal{C})$.) Completion of $\mathcal{A}_{s'}$ establishes the global state $\mathcal{F}_{n+1}$ and simultaneously commits instance $a$'s new state as $s'$ (removing $a$ from $\mathcal{F}_{n+1}(A)$ if $s' \in \Sigma_A^{\mathrm{final}}$).

* **Remark 2.2 (Contrast with OOP Encapsulation and Isomorphism between Moore and Mealy Forms):** To practitioners accustomed to object-oriented programming (OOP), having an action update the entire Field of Sense rather than remaining encapsulated inside a single instance may initially appear unusual. Under a relation-based ontology (Paper 0 and Paper 1), however, invariants such as multiplicities and referential integrity are always defined globally across the entire Field of Sense, making atomic global updates a structural necessity. Moreover, even if an alternative dynamic formalism is chosen—such as Mealy machines attaching actions to transition arrows—partitioning the state space via coproducts yields a **categorical equivalence (isomorphism) with the Moore normal form** adopted here, where actions are bound to target states (Section 5, Theorem 5.3).

Furthermore, the causal structure governing event transmission across concurrently operating instance state machines is geometrically isomorphic to **Local Inertial Frames** in relativistic physics.

**Proposition 2.2 (Isomorphism with Local Inertial Frames and Relativistic Causal Structure)**
The ensemble of concurrent instance state machines within a Field of Sense is isomorphic to local inertial frames in relativistic physics in three respects:
1. **State Transitions as Proper Time:** Rather than a single global absolute clock, the chain of steps in which events—including timer events ($e_{\mathrm{time}}$)—arrive at and are processed by an individual instance $a$ defines that entity's own local time axis (proper time $\tau_a$).
2. **Preservation of Local Causality (Self-Event Priority):** Among events generated during the execution of action $\mathcal{A}_{s'}$, events addressed to the executing instance itself (Self-Events) are always processed prior to external events addressed to other instances (Self-Event Priority Axiom), preserving local causality along each entity's worldline.
3. **Spacelike Separation and Commutativity:** State transitions of independent instances that exchange no events are spacelike-separated; regardless of their relative execution order, the symmetry isomorphism (parallel composition $\otimes$) of the symmetric monoidal category guarantees an identical global outcome.

---

## 3. Data-Flow Action Models, Formal Textual Syntax, and the Symmetric Monoidal Category $\mathcal{DF}$

### 3.1 Four Scopes of Action Models and the Templated Nature of Primitive Processes
Section 2 established that actions accompanying state transitions update the global instance functor $\mathcal{F}_n \in \mathrm{Valid}(\mathcal{C})$ of a Field of Sense to $\mathcal{F}_{n+1}$. Within this framework, a data-flow action model (a composition of primitive process components and data-flow wires) is formalized not as an imperative sequence of commands ("Doing"), but as side-effect-free **equational logic ("Being")** governed by linear-logic resource flow \cite{girard1987}.

Based on spatial scope and encapsulation rules, action models may be specified in strictly **four domains**:
1. **Entry Action:** Bound to a target state in a state model; transforms the global state of the Field of Sense ($\mathcal{F}_n \to \mathcal{F}_{n+1}$) via instance creation/deletion, property updates, and link reconfiguration.
2. **Mathematical Property:** Bound to a derived attribute of a conceptual class; evaluates automatically upon reference to return a value computed from relationship topology or cardinality without side effects ($\mathcal{F}_n(A) \to \mathcal{F}_n(T)$). Within this derivation flow, **inputs are strictly restricted to the current global state of the Field of Sense ($\mathcal{F}_n$ queries/traversals) and outputs from external entity functions** (state-mutating operations and event generation are syntactically and semantically prohibited), and **the output necessarily closes via equational binding to that specific attribute on `SELF` (Component ⑮(b) below)**.
3. **Class Function:** A domain-internal pure computation helper bound to a conceptual class sort (direct invocation from external domains is prohibited). Within this flow, **inputs are strictly restricted to explicitly passed input parameter wires ($\bigotimes_{i=1}^p T_{\mathrm{in}, i}$), the invariant schema structure of the Conceptual Information Model (such as type bounds and enumeration lattices), and outputs from external entity functions**. Reading or mutating the current instance state ($\mathcal{F}_n$) and generating events are strictly prohibited, and the output necessarily closes via a typed `return` wire (Component ⑮(a) below).
4. **Domain Function:** Bound to the formal interface boundary of a Field of Sense; serves as the public port interacting with Bridges connecting distinct Fields of Sense (Paper 0 and Paper 3) or external simulators (recursive internal calls from within the same domain are prohibited).

Crucially, every primitive process component (bubble) placed within a data flow is not generic program code; rather, it is a **unique function symbol (morphism) that automatically emerges within that Field of Sense the moment its Conceptual Information Model and State Model schemas are fixed**. Every component fires if and only if 100% of its required input resources are present on its incoming wires as a linear-logic tensor product ($\otimes$).

| Action Model Scope | Input Data-Flow Sources | Reading Instance State $\mathcal{F}_n$ | Mutating State $\mathcal{F}_n$ / Event Generation | Output Closure |
| :--- | :--- | :--- | :--- | :--- |
| **1. Entry Action** | Event Supplemental Data + State $\mathcal{F}_n$ + $\mathcal{EE}$ | **Allowed** (Read / Select) | **Allowed** (Global update $\mathcal{F}_n \to \mathcal{F}_{n+1}$) | Committed global state $\mathcal{F}_{n+1}$ (no return value) |
| **2. Mathematical Property** | Current global state $\mathcal{F}_n$ + $\mathcal{EE}$ (no arguments) | **Allowed** (Read / Select) | **Prohibited** (Zero side effects) | Equational assignment to `SELF`'s attribute |
| **3. Class Function** | Input parameters (data types) + **CIM schema structure (form)** + $\mathcal{EE}$ | **Prohibited** (No instance state) | **Prohibited** (Pure computation only) | Typed function `return` wire |
| **4. Domain Function** | Boundary input parameters (static types) + State $\mathcal{F}_n$ + $\mathcal{EE}$ | **Allowed** (Read / Select) | **Allowed** (Global updates / event generation) | Boundary output wires (projection of state intension) |

---

### 3.2 Exhaustive Catalog of Primitive Process Components (①–⑯) and New OAL Syntax
Grounded in the primitives of the Conceptual Information Model (Paper 1) and State Models (Section 2), the building blocks of data-flow action models are uniquely and exhaustively determined as **16 orthogonal geometric operators (morphisms)**, expressed textually via **New OAL** (an equational formalization referencing BridgePoint xtUML's Object Action Language \cite{mellor2002,xtumlorg}):

#### ① Create Object Instance
* **I/O & Syntax:** Takes a conceptual class keyletter $A \in \mathcal{K}$ and optional initial property values ($v_i \in \mathcal{F}(T_i)$), outputting a newly instantiated reference $\mathrm{Ref}(A)$ (`CREATE INSTANCE uniqueRef OF ClassKL [PropA: valueA, ...];`).
* **Category-Theoretic Form:** A pushout from the initial object $0$ producing a provisional functor $\mathcal{F}'(A) = \mathcal{F}(A) \sqcup \{a_{\mathrm{new}}\}$, simultaneously fixing $\mathcal{F}'(\mathrm{attr}_i)(a_{\mathrm{new}}) = v_i$ (or topos default values) and enforcing injectivity of the persistent identifier $\mathcal{F}'(\alpha_I) : \mathcal{F}'(A) \hookrightarrow \prod_{i \in I} \mathcal{F}'(T_i)$ (monomorphism).

#### ② Delete Object Instance
* **I/O & Syntax:** Takes a single instance reference $\mathrm{Ref}(A)$ and terminates into the terminal object $1$ (`DELETE INSTANCE uniqueRef;`).
* **Category-Theoretic Form:** A local copushout $\mathcal{F}'(A) = \mathcal{F}(A) \setminus \{a\}$ pushing all incident link morphisms of $a$ into empty space ($\mathcal{F}'(r)(a) = \emptyset$). Transient dangling links resulting immediately after deletion are permitted mid-action and checked globally upon state commitment.

#### ③ Read Property
* **I/O & Syntax:** Takes $\mathrm{Ref}(A)$ and an attribute morphism $\mathrm{attr} : A \to T$ ($T \in \mathcal{D}_{\mathrm{static}}$), outputting a single element of $\mathcal{F}(T)$ (`valueContainer = uniqueRef.PropA;`).
* **Category-Theoretic Form:** A state-preserving projection $\mathrm{read} : \mathcal{F}(A) \to \mathcal{F}(T)$ ($a \mapsto \mathcal{F}(\mathrm{attr})(a)$) whose sort compatibility is guaranteed functorially.

#### ④ Update Property / Assign
* **I/O & Syntax:** Takes $\mathrm{Ref}(A)$, $\mathrm{attr} : A \to T$, and $v_{\mathrm{new}} \in \mathcal{F}(T)$, terminating into $1$ (`ASSIGN uniqueRef.PropA = valueExpression;`). Direct assignment to referential properties ($\mathcal{D}_{\mathrm{REF}}$) is syntactically prohibited.
* **Category-Theoretic Form:** Via the state-update monad $\mathcal{T}_P$ \cite{moggi1991}, updates $\mathcal{F}'(\mathrm{attr})(a) = v_{\mathrm{new}}$. If $v_{\mathrm{new}}$ violates subobject boundaries $m : T_{\mathrm{sub}} \hookrightarrow T$ (range or enumeration bounds), a type guard immediately collapses the morphism into the initial object $0$.

#### ⑤ Relate
* **I/O & Syntax:** Takes two instance references $\mathrm{Ref}(A),\, \mathrm{Ref}(B)$ (plus $\mathrm{Ref}(R)$ for associative classes) and a relationship specification, terminating into $1$ (`relate a to b across R1.'phrase';` / `using assocInst;`).
* **Category-Theoretic Form:** Enforces topological constraints: (1) **Binary:** $\mathcal{F}'(r^{\rightarrow})(a) = b \iff \mathcal{F}'(r^{\leftarrow})(b) = a$; (2) **`Is-a`:** coproduct inclusion $\mathcal{F}'(\iota_i)(c) = s$; (3) **Associative:** span monicity $\mathcal{F}'(\langle p_A, p_B \rangle) : \mathcal{F}'(R) \hookrightarrow \mathcal{F}'(A) \times \mathcal{F}'(B)$. Sort mismatches or monicity violations collapse immediately into $0$; multiplicity constraints are verified upon state commitment.

#### ⑥ Unrelate
* **I/O & Syntax:** Takes $\mathrm{Ref}(A),\, \mathrm{Ref}(B)$ (and optionally $\mathrm{Ref}(R)$) and terminates into $1$ (`unrelate a from b across R1.'phrase';`).
* **Category-Theoretic Form:** Removes the link from the morphism graph ($b \notin \mathcal{F}'(r^{\rightarrow})(a) \iff a \notin \mathcal{F}'(r^{\leftarrow})(b)$), remaining strictly orthogonal to deleting the associative instance itself.

#### ⑦ Select From Instances Of
* **I/O & Syntax:** Takes class $A \in \mathcal{K}$ and a `WHERE` predicate, outputting $\mathrm{Ref}(A)$ (`ANY`) or an unordered set $\mathrm{Set}(A)$ (`MANY`) (`select any dest from ClassKL where condition;` / `select many destSet ...`).
* **Category-Theoretic Form:** Pullback along the characteristic predicate $\chi : \mathcal{F}(A) \to \Omega$ yielding $A_{\mathrm{sub}} = \{a \in \mathcal{F}(A) \mid \chi(a) = \mathrm{True}\}$. For `ANY`, if $A_{\mathrm{sub}} = \emptyset$, textual syntax holds `NULL`, whereas in data-flow geometry the output wire vanishes into $1$, cutting off downstream dependent computations.

#### ⑧ Select Related By
* **I/O & Syntax:** Takes a starting reference $\mathrm{Ref}(S)$ and a multi-hop phrased relationship path equipped with per-hop local `WHERE` filters (using keyword `TARGET`) and fixed-point modifiers (`flux` / `root` / `leaf`), outputting $\mathrm{Ref}(A)$ (`ONE` / `ANY`) or $\mathrm{Set}(A)$ (`MANY`).
* **Category-Theoretic Form:** A composite global pullback morphism
  $$\mathrm{navigate}_{\mathrm{multi}} = \mathcal{F}(r_n \ \text{restricted by} \ \chi_n) \circ \dots \circ \mathcal{F}(r_1 \ \text{restricted by} \ \chi_1)$$
  augmented by transitive-closure fixed-point/colimit operators: **`flux`** (maximal terminal element in forward traversal), **`root`** (minimal initial element in reverse traversal), and **`leaf`** (all terminal leaf nodes lacking outgoing child arrows as $\mathrm{Set}(A)$). For `ONE`, absence of a target violates multiplicity `1` and collapses immediately into $0$.

#### ⑨ Variable Assignment (Data-Flow Wire Creation)
* **I/O & Syntax:** Takes an evaluated resource of any admissible type ($\mathcal{D}_{\mathrm{static}}$, $\mathrm{Ref}(A)$, or $\mathrm{Set}(A)$) and binds it to a named solid data-flow wire (`assign varName = expr;`).
* **Category-Theoretic Form:** Rather than destructive memory mutation, binds a unique static single-assignment (SSA) identifier to a live data-flow wire. Any sort mismatch between left-hand and right-hand sides immediately collapses the morphism into $0$.

#### ⑩ Arithmetic Operation
* **I/O & Syntax:** Binary (`+`, `-`, `*`, `/`, `%`) or unary (`cardinality`, unary `-`) operators taking tensered input wires ($\otimes$) and outputting a single result wire.
* **Category-Theoretic Form:** (1) Mixed integer ($\mathbb{Z}$) and real ($\mathbb{R}$) operands promote via inclusion adjunction to $\mathbb{R}$. (2) **Division by zero** collapses immediately into $0$ via pullback failure, proving the action specification itself invalid. (3) Modulo (`%`) is restricted to $\mathbb{Z}$ and governed by Euclidean division $a = b \times q + r$ ($0 \le r \lt \lvert b \rvert$). (4) String concatenation (`+`) and affine time algebra ($\mathrm{DateTime} - \mathrm{DateTime} \to \mathrm{TimeSpan}$, $\mathrm{DateTime} \pm \mathrm{TimeSpan} \to \mathrm{DateTime}$, $\mathrm{TimeSpan} \pm \mathrm{TimeSpan} \to \mathrm{TimeSpan}$) map to external entity functions; invalid combinations (e.g., $\mathrm{DateTime} + \mathrm{DateTime}$) collapse immediately into $0$.

#### ⑪ Logical Evaluation
* **I/O & Syntax:** Same-sort comparisons (`==`, `!=`, `<`, `<=`, `>`, `>=`) or boolean algebra (`and`, `or`, `not`) outputting an element of the subobject classifier $\Omega = \{\mathrm{True}, \mathrm{False}\}$.
* **Category-Theoretic Form:** String lexicographical order and datetime chronological order map to external entity functions; boolean connectives evaluate via meet ($\wedge$), join ($\vee$), and complement ($\neg$) in $\Omega$. Cross-sort comparisons collapse immediately into $0$ on par with division by zero.

#### ⑫ Internal Logical Selection (`If / Else If / Else`)
* **I/O & Syntax:** Takes a boolean guard ($\Omega$) and incoming data wires $X$, routing through branch morphisms ($f, g, h$) into a merged target space $Y$.
* **Category-Theoretic Form:** Rather than imperative control jumps, partitions $X$ into an exclusive coproduct $X \to X_{\mathrm{cond0}} \amalg X_{\mathrm{cond1}} \amalg X_{\mathrm{else}}$ followed by the universal copairing morphism $[f, g, h] : X_{\mathrm{cond0}} \amalg X_{\mathrm{cond1}} \amalg X_{\mathrm{else}} \to Y$. Under linear-logic resource flow, unselected branches receive zero resource energy ($0$) and attenuate silently without firing side effects.

#### ⑬ Set-Wide Concurrent Evaluation (`For Each Loop`)
* **I/O & Syntax:** Takes an instance set $\mathrm{Set}(A)$ and an inner action morphism $f$, evaluating across all elements (`for each elem in setVar ... end for;`).
* **Category-Theoretic Form:** Rather than sequential index iteration, expands the current finite set $A_{\mathrm{set}} = \{a_1, \dots, a_n\}$ via dynamic colimit $X_{\mathrm{total}} \cong \coprod_{i=1}^n \mathrm{Ref}(a_i)$, spawning $n$ independent, simultaneously executing copies $\coprod_{i=1}^n f_i$. If $A_{\mathrm{set}} = \emptyset$ ($n=0$), total resource energy is $0$ and the block closes silently.

#### ⑭ Event Generation
* **I/O & Syntax:** Takes an event label, supplemental data tensor $\bigotimes T_{\mathrm{args}}$, and target ($\mathrm{Ref}(B)$, `SELF`, class keyletter `creator`, plus `TimeSpan` or `DateTime` for delayed events) (`generate ... to ... [delay ... | at ...];`).
* **Category-Theoretic Form:** Projects an event pulse onto the target instance's local causal poset queue $\mathcal{E}_b = \langle E_b, \le_b \rangle$. Targeting `creator` triggers Component ① (`CREATE`) on class $B$; delayed events (`delay` / `at`) materialize onto $\mathcal{E}_b$ via pullback upon reaching the boundary condition on $\mathcal{EE}_{\mathrm{Time}}$.

#### ⑮ Output Flow Termination and Equational Binding (`Return / Property Assignment`)
* **Category-Theoretic Form:** (a) Terminates class functions and domain functions by delivering the converged value to the declared output signature (`return expr;`), and (b) equationally binds a Mathematical Property upon reference via `SELF.[PropertyName] = expr;`.

#### ⑯ External Entity Function Execution
* **I/O & Syntax:** Maps a tensor product of declared static input types $\bigotimes_{i=1}^n T_{\mathrm{in}, i}$ to at most one static output type $T_{\mathrm{out}}$ or $1$ (`EE_KL::funcName(...);`).
* **Category-Theoretic Form:** An **opaque (black-box) symmetric monoidal morphism** $f_{\mathcal{EE}} : \bigotimes_{i=1}^n T_{\mathrm{in}, i} \to T_{\mathrm{out}}$ into an autonomous external universe. It cannot inspect or directly mutate the local instance functor $\mathcal{F}_n$ (state invariance), influencing the local domain solely through its output data-flow wire.

### 3.3 Standard External Entities (`STR`, `TIM`) and the Principle of Transient Evaluation and Two-Stage Consistency
Because strings and timestamps are ubiquitous across virtually all Fields of Sense, two standard external entities are built into the base action language:
1. **String External Entity (`STR`: $\mathcal{EE}_{\mathrm{String}}$):** Provides equality (`equal`, `not_equal`), lexicographical ordering (`compare`), concatenation (`concat`), substring extraction (`substring`), pattern search (`index_of`), replacement (`replace`), and length measurement (`length`) over the free monoid $\Sigma^*$.
2. **Datetime External Entity (`TIM`: $\mathcal{EE}_{\mathrm{Time}}$):** Provides affine time algebra (`duration`, `add_span`, `subtract_span`, `combine_span`) between time points (`DATETIME`) and duration vectors (`TIMESPAN`), chronological ordering (`compare`), and calendar synthesis/extraction (`create_datetime`, `get_year` through `get_microsecond`), where out-of-bounds calendar values collapse immediately into $0$ on par with division by zero.

**Axiom 3.1 (Orthogonal Independence, Evaluation of Transient States, and Two-Stage Consistency Verification)**
The 16 primitive process components defined above are mutually orthogonal, independent geometric operators containing no internal pre-validation logic. Execution of an entry action (or domain function) progresses as a **chain of provisional/transient instance functors ($\mathcal{F}_n \to \mathcal{F}' \to \mathcal{F}'' \to \cdots \to \mathcal{F}_{n+1}$)** governed globally by three topological rules:

1. **Reference to the Current Transient State Functor $\mathcal{F}'$:** Primitive process components that consume the state of the Field of Sense as input data flow (e.g., ③ `ReadAttr`, ⑦ `Select From Instances`, ⑧ `Select Related By`) evaluate not against a frozen initial snapshot $\mathcal{F}_n$, but against **the exact transient instance functor $\mathcal{F}'$ produced by preceding operations at the moment the component fires**. Consequently, mid-execution within an active transition's entry action, static constraints of the Conceptual Information Model (CIM) may be temporarily violated (such as transient dangling links or unsatisfied multiplicities immediately after `DELETE` or `UNRELATE`), and those transient values are directly observed and utilized.
2. **Immediate Type-Guard Collapse (Local Singularities):** Division by zero, out-of-bounds values on range-restricted types, cross-sort comparisons, missing targets on multiplicity-`1` traversals (`select one`), and duplicate span-monomorphism bindings on associative classes immediately render composition impossible, collapsing into the initial object $0$.
3. **Global Consistency at State Commitment:** Temporary CIM constraint violations in transient states $\mathcal{F}'$ are legitimately permitted mid-action; a transition commits validly if and only if the final functor upon action completion satisfies $\mathcal{F}_{n+1} \in \mathrm{Valid}(\mathcal{C})$ (as well as global requirement norms addressed in Paper 3).

**Remark 3.2 (Representability of Transient Inconsistencies, Resource Contention, and Deadlocks)**
Conventional software engineering methodologies attempt to hide intermediate inconsistencies and resource-contention deadlocks behind idealized transaction abstractions and encapsulation. In the real world—whether in human business processes or physical interactions—transient states in which structural constraints are temporarily broken, as well as resource contention leading to deadlocks, are commonplace. By explicitly admitting sequential evaluation over transient functors $\mathcal{F}'$ and collapse singularities ($0$), this formalism enables modelers to specify and analyze transient inconsistencies, resource contention, and deadlocks without concealment. Furthermore, because potential deadlocks and singularity paths are explicitly representable within the model, modelers can systematically identify those conditions and specify **sound, deadlock-free models within the exact same formalism** via state partitioning and arbitration aspects.

---

### 3.4 Homotopical Closure of the Symmetric Monoidal Category $\mathcal{DF}$ and Domain Functions
**Theorem 3.1 (Syntax–Semantics Isomorphism and Homotopical Symmetric Monoidal Closure)**
There exists a natural categorical equivalence (syntax–semantics isomorphism) between valid New OAL textual programs (quotiented by $\alpha$-equivalence and commutation of independent statements) and acyclic string diagrams (DAGs) formed by sequential composition ($\circ$) and linear-logic tensor products ($\otimes$) of the 16 primitive process components \cite{joyal1991,coecke2017}. By the Joyal–Street coherence theorem, any continuous deformation (isotopy/homotopy) preserving causal data dependencies belongs to the same equivalence class, and every action execution terminates in finitely many steps to commit a unique resulting state $\mathcal{F}_{n+1}$.

**Definition 3.1 (Domain Functions as Boundary Composite Morphisms and Bridge Interfaces)**
The fourth scope of action models, a **Domain Function**, belongs to no specific state transition; rather, it is a boundary composite morphism constructed solely from the 16 primitive components under the DAG rules of $\mathcal{DF}$ whose external signature is closed entirely over static data types ($\mathcal{D}_{\mathrm{static}}$):
$$F_{\mathrm{dom}} : \bigotimes_{i=1}^p T_{\mathrm{in}, i} \longrightarrow \bigotimes_{j=1}^q T_{\mathrm{out}, j} \qquad (T_{\mathrm{in}, i},\, T_{\mathrm{out}, j} \in \mathcal{D}_{\mathrm{static}})$$
(Invocation-only ports with no input wires correspond to $p=0$, i.e., morphisms from the monoidal unit $I \to \bigotimes_{j=1}^q T_{\mathrm{out}, j}$, whereas state-updating ports returning no value correspond to $q=0$, i.e., morphisms $\bigotimes_{i=1}^p T_{\mathrm{in}, i} \to I$.) Fundamentally, a domain function is a pure bundle of input and output data-flow wires in a symmetric monoidal category, referred to conventionally as "input parameters" and "return values" when written in textual New OAL syntax. To preserve the autonomy and logical closure of each Field of Sense, coexisting Fields of Sense cannot directly manipulate one another's internal conceptual classes; instead, **public events** and **domain functions** serve as the sole formal connection ports for Bridges (Paper 0) and cross-domain Transformations (Paper 3).

**Remark 3.1 (Formal Characterization of Domain Function Outputs as the "Intension" of State)**
As established in Paper 0, the Universe contains no privileged "external space" overarching all Fields of Sense; multiple Fields of Sense coexist on an equal, flat footing. Accordingly, the output data flow ($\bigotimes_{j=1}^q T_{\mathrm{out}, j}$) of a domain function $F_{\mathrm{dom}}$ represents not the view of a transcendent external observer, but **the formal image obtained by projecting the current state $\mathcal{F}_n \in \mathrm{Valid}(\mathcal{C})$ into static data-type space while forgetting internal conceptual classes and relational links—that is, the "Intension" of state formalized in Paper 0**. Because coexisting Fields of Sense cannot inspect one another's internal schemas, only these formal intensional projections (via domain functions and public events) act as bridge interfaces, and in accordance with Paper 0's epistemological limitation theorem, the full internal instance state cannot in general be uniquely inverted from these projected outputs alone.

---

## 4. Universal Execution Semantics and Boundary-Condition Aspects

### 4.1 Execution Semantics via Reference to Form ($\mathcal{C}_{\mathrm{FORM}}$) Independent of Domain Content
Paper 1 established the formal specification for static semantic structure (the Conceptual Information Model), and Sections 2 and 3 of the present paper established the formal specification for dynamic state evolution (State Models and Data-Flow Action Models). Yet no matter how rigorously static and dynamic models are specified, they remain inert unless accompanied by constraints governing how they behave—that is, under what causal order, priority rules, and boundary conditions they execute.

A foundational principle derived in this framework is that **Execution Semantics can be defined universally and uniquely upon the abstract structural form itself (Meta-Form) of the conceptual information model, state model, and action model, without inspecting the concrete domain semantics of any individual Field of Sense** (whether accounting, logistics, embedded control, or physical phenomena).

**Definition 4.1 (Form Category $\mathcal{C}_{\mathrm{FORM}}$ and the Four Axioms of Universal Execution Semantics)**
Let **the Form Category $\mathcal{C}_{\mathrm{FORM}}$** denote the canonical structural meta-form shared by every domain model $\mathcal{M} = (\mathcal{C}, \{M_A\}_{A \in \mathcal{K}}, \mathcal{DF})$—comprising conceptual classes, monic identifiers, four multiplicities, state transition tables, acyclic DAG actions, and proper-time event queues. **Universal Execution Semantics** independent of domain content is uniquely defined as a natural state-transition functor $\mathcal{E}_{\mathrm{exec}}$ over $\mathcal{C}_{\mathrm{FORM}}$ governed by four axioms:

1. **Axiom E-1 (Run-to-Completion Atomicity):** When a single event $e$ is dequeued from an instance $a \in \mathcal{F}_n(A)$'s proper-time queue to trigger transition $s \xrightarrow{e} s'$, the entire DAG evaluation of the entry action $\mathcal{A}_{s'}$ attached to target state $s'$ (together with any invoked mathematical properties or class functions) executes as an **indivisible atomic step** free from external interruption. Intermediate transient functors $\mathcal{F}'$ (such as dangling states immediately after `delete` or `unrelate`) are never externally committed; only the final functor $\mathcal{F}_{n+1}$ upon action completion is established as the valid next state.
2. **Axiom E-2 (Self-Event Priority: Preservation of Local Proper Time):** Among multiple events generated (`generate`) during the execution of entry action $\mathcal{A}_{s'}$, events addressed by instance $a$ **to itself (`to SELF`)** are always processed prior to external events addressed to other instances (`to uniqueRef` / `to creator`), ensuring that local causality along each individual entity's worldline is strictly preserved.
3. **Axiom E-3 (FIFO Ordering and Parallel Commutativity of Asynchronous Events):** External events transmitted between distinct instances strictly preserve emission order (FIFO partial order $\le_b$) along any path from a given sender instance to a given receiver instance. Conversely, event processing across independent instances exchanging no causal signals is spacelike-separated and invariant under any parallel or interleaved execution schedule via the symmetry isomorphism ($\otimes$) of $\mathcal{DF}$.
4. **Axiom E-4 (Pullback Coupling of Boundary-Condition Aspects):** Timer events supplied by external entity $\mathcal{EE}_{\mathrm{Time}}$ (timer expirations, periodic triggers) as well as non-functional execution constraints (synchronization, mutual exclusion locks, transaction boundaries, numerical precision) are applied orthogonally across the entire model form—without polluting first-class domain classes—via the **pullback (fiber product)** with an aspect category $\mathcal{V}$ over $\mathcal{C}_{\mathrm{FORM}}$:
   $$\mathcal{M}_{\mathrm{exec}} \equiv \mathcal{M} \times_{\mathcal{C}_{\mathrm{FORM}}} \mathcal{V}$$

**Theorem 4.1 (Universal Execution Semantics Theorem)**
For any domain model $\mathcal{M}$ conforming to the axioms of Paper 1 (quotient 2-category $\mathcal{C}$) and Sections 2–3 of the present paper, the execution semantics $\mathcal{E}_{\mathrm{exec}}$ defined by the four axioms of Definition 4.1 induces a **unique, deterministic state-transition system (up to parallel commutation equivalence) $\mathrm{Valid}(\mathcal{C}) \Rightarrow \mathrm{Valid}(\mathcal{C}) \sqcup \{0\}$ solely from the abstract model form**, without referencing domain-specific business rules or physical laws.

**Proof Sketch:**
Static structures are fully typed via monic identifiers and seven closed data types, while dynamic structures reduce to finite state transition tables (STTs) and acyclic string diagrams (DAGs). Axiom E-1 fixes the input–output boundary of each transition step; Theorem 3.2 (DAG acyclicity) guarantees finite-step termination; Axioms E-2 and E-3 uniquely determine the causal partial order of event queues; and the fiber product $\mathcal{M} \times_{\mathcal{C}_{\mathrm{FORM}}} \mathcal{V}$ in Axiom E-4 functorially composes external boundary conditions. Hence, a universal execution semantics is uniquely determined independent of domain content. $\blacksquare$

---

### 4.2 Dynamic Preservation of Invariants and Collapse / Phase Transitions at Singularities
When a model evolves under Universal Execution Semantics $\mathcal{E}_{\mathrm{exec}}$, its execution trajectories partition strictly into "regular trajectories" that preserve all consistency constraints of $\mathcal{C}$ and "singular trajectories" that reach a collapse boundary ($0$).

**Definition 4.2 (Regular Trajectories and Singular Trajectories)**
For an event-driven execution sequence $\mathcal{F}_0 \xrightarrow{e_1} \mathcal{F}_1 \xrightarrow{e_2} \cdots \xrightarrow{e_n} \mathcal{F}_n$ starting from $\mathcal{F}_0 \in \mathrm{Valid}(\mathcal{C})$:
* **Regular Trajectory:** An execution path along which no `Can't Happen` transition, no immediate type-guard collapse (division by zero, subobject boundary violation, span monicity breach), and no global consistency violation at state commitment ever occurs.
* **Singular Trajectory:** An execution path that encounters any of the above prohibited conditions at some step $k$, collapsing the state functor into the initial object $0$ (empty space) of the internal topos logic.

**Theorem 4.2 (Dynamic Preservation of Invariants)**
Along any regular execution trajectory, if the pre-transition state $\mathcal{F}_n$ satisfies all axioms and constraints of the static schema category $\mathcal{C}$ ($\mathcal{F}_n \in \mathrm{Valid}(\mathcal{C})$), then the post-transition state $\mathcal{F}_{n+1}$ committed after any event arrival and subsequent completion of entry action $\mathcal{A}_{s'}$ **necessarily preserves 100% of the static invariants of $\mathcal{C}$** (identifier injectivity, four multiplicities, referential commutativity, `Is-a` coproduct exclusivity, associative span monicity, and prohibition of diagonal self-loops):
$$\mathcal{F}_n \in \mathrm{Valid}(\mathcal{C}) \quad \Longrightarrow \quad \mathcal{F}_{n+1} \in \mathrm{Valid}(\mathcal{C})$$

**Proof Sketch:**
Each entry action $\mathcal{A}_{s'}$ is a finite DAG composition of the 16 primitive components of Section 3. Components ① (`CREATE`) and ④ (`ASSIGN`) enforce identifier monicity (Axiom C-1) and subobject range bounds via immediate type guards, while Component ⑤ (`RELATE`) enforces associative span monicity (Axiom C-2) and coproduct inclusion (Axiom C-3). Any temporary multiplicity deficits or dangling links arising mid-action after ② (`DELETE`) or ⑥ (`UNRELATE`) are evaluated globally upon action completion against the pullback conditions of $\mathcal{C} \equiv CG/\mathcal{R}$ under Axiom E-1 and Axiom 3.1. Because a regular trajectory by definition avoids collapse into $0$ at state commitment, $\mathcal{F}_{n+1}$ automatically satisfies all structure-preserving conditions of $\mathrm{Valid}(\mathcal{C})$. $\blacksquare$

**Corollary 4.1 (Unified Account of Business Breakdowns and Physical Phase Transitions at Singularities)**
Conversely, when an execution trajectory reaches a singularity (initial object $0$), this represents not a crash of an execution engine, but the **mathematical manifestation that the system has reached the critical boundary of the "constitution" (conditions of possibility) defined by $\mathcal{C}$ and its state model, beyond which that Field of Sense can no longer subsist without contradiction**:
* **Commercial and Organizational Domains:** When an operational business or software model harboring latent specification oversights (unhandled `Can't Happen` transitions, unguarded division by zero, or missing mandatory links) encounters the critical event sequence, its operational order loses consistency and suffers organizational or system breakdown.
* **Natural and Physical Domains:** In physical Fields of Sense, when state variables reach a singularity of their governing equations (critical temperature, critical pressure, or an event horizon), the description under schema category $\mathcal{C}_1$ collapses to $0$, and the system undergoes a **phase transition** into a distinct Field of Sense governed by a new schema category $\mathcal{C}_2$ (such as boiling from liquid to gas or transitioning to superconductivity).

---

## 5. Meta-Theorems of Dynamic Modeling, Discrete Representation of Continuous Dynamics, and Isomorphism with Physical Field Theories

Sections 2–4 formalized causal state transitions and dynamic behavior over a static schema category $\mathcal{C}$ in terms of typed events (including supplemental data), universal instance state machines, active/final states and singularities (`Can't Happen`), acyclic string diagrams (the symmetric monoidal category $\mathcal{DF}$) built from 16 primitive process components alongside formal New OAL textual syntax, boundary composite morphisms (**Domain Functions**), and Universal Execution Semantics defined over $\mathcal{C}_{\mathrm{FORM}}$.

In this section, I prove the four dynamic meta-theorems in exact symmetry with the static theorems of Paper 1 (**Dynamic Expressive Completeness, Constructive Existence and Homotopical Monoidal Closure, Dynamic Isomorphism, and Dynamic Asymptotic Convergence**), followed by the **Discrete Representation Theorem for Continuous Dynamics** and the **Isomorphism Theorem with Physical Field Theories**.

---

### 5.1 Dynamic Expressive Completeness Theorem
**Theorem 5.1 (Expressive Completeness of the Dynamic Modeling Formalism)**
Any computable (Turing-complete) and causal state-transition system defined over the valid state space $\mathrm{Valid}(\mathcal{C})$ of a static schema category $\mathcal{C}$ is adequately representable using solely the minimal primitives of this framework—namely: (1) finite state machines (STTs) bound to conceptual classes, (2) creation, instance, and timer events typed by $\mathcal{D}_{\mathrm{static}}$ (with supplemental data), (3) acyclic string diagrams (in $\mathcal{DF}$) composed of the 16 primitive process components, and (4) Universal Execution Semantics.

**Proof Sketch:**
By the Church–Turing thesis and equivalence with Minsky register machines, arbitrary algorithmic and discrete-event dynamics are spanned by: (a) finite state memory and branching, (b) unbounded dynamic allocation and release of structured relational state, and (c) conditional iteration. Within this formalism, (a) is realized by the exclusive coproduct state space $\Sigma_A$ and logical selection (⑫), (b) is realized by instance creation (①), deletion (②), link binding (⑤), and unbinding (⑥), and (c) arbitrary iteration or recursion is realized via asynchronous self-events (⑭ `generate ... to SELF`) driving state-machine transition cycles while keeping every individual action DAG strictly acyclic. Thus, no additional control primitives are required. $\blacksquare$

---

### 5.2 Dynamic Consistency and Homotopical Monoidal Closure Theorem
**Theorem 5.2 (Constructive Existence and Homotopical Monoidal Closure of Dynamic Models)**
For any dynamic model $\mathcal{M} = (\mathcal{C}, \{M_A\}, \mathcal{DF}, \mathcal{E}_{\mathrm{exec}})$ satisfying the axioms of Sections 2–4, there constructively exists a non-empty regular execution trajectory ($\mathcal{F}_0 \to \mathcal{F}_1 \to \cdots$ avoiding the initial object $0$) preserving all static schema invariants at every regular step ($\mathcal{F}_n \in \mathrm{Valid}(\mathcal{C}) \implies \mathcal{F}_{n+1} \in \mathrm{Valid}(\mathcal{C})$). Moreover, the space of dynamic behaviors closes as a **homotopically closed symmetric monoidal category** under string-diagram isotopy and parallel commutation.

**Proof Sketch:**
By Paper 1 (Theorem 5.2), a non-trivial valid initial state $\mathcal{F}_0 \in \mathrm{Valid}(\mathcal{C})$ exists constructively. Assigning each instance to an active state in $\Sigma_A^{\mathrm{active}}$ and mapping incoming events to `Ignore` (identity) or invariant-preserving `WriteAttr`/`Relate` DAGs yields a well-formed regular trajectory $\mathcal{F}_0 \to \mathcal{F}_0 \to \cdots$. By Theorem 3.2 and Axiom E-3, reordering independent parallel events across spacelike-separated instances forms commuting diamond diagrams (homotopy equivalences) converging to an identical state $\mathcal{F}_{n+1}$. $\blacksquare$

---

### 5.3 Dynamic Isomorphism Theorem
**Definition 5.1 (Dynamic Adequacy and Observational Equivalence)**
Let $\mathcal{T}_{\mathcal{SYS}}$ denote the space of valid state-transition trajectories of a target Field of Sense $\mathcal{SYS}$. A dynamic model $\mathcal{M}$ **adequately represents** $\mathcal{SYS}$ if the space of regular trajectories (and singularity boundaries) generated under Universal Execution Semantics $\mathcal{E}_{\mathrm{exec}}$ stands in natural bijection with $\mathcal{T}_{\mathcal{SYS}}$, preserving the truth valuation of all meaningful propositions at every transition step.

**Theorem 5.3 (Dynamic Isomorphism Theorem: Uniqueness up to Monoidal Equivalence)**
Any two dynamic models $\mathcal{M}_1$ and $\mathcal{M}_2$ that adequately represent the same Field of Sense $\mathcal{SYS}$ are **categorically equivalent as symmetric monoidal state-transition systems ($\mathcal{M}_1 \simeq \mathcal{M}_2$)**, regardless of representational variations (e.g., Mealy transition actions vs. Moore normal form, state granularity, visual string diagrams vs. New OAL text syntax, or natural-language labels).

**Proof Sketch:**
By Paper 1 (Theorem 5.3), $\mathcal{C}_1 \simeq \mathcal{C}_2$ and $\mathrm{Valid}(\mathcal{C}_1) \simeq \mathrm{Valid}(\mathcal{C}_2)$. Any Mealy-style model attaching actions to transition arrows converts isomorphically into Moore normal form via coproduct splitting of states indexed by incoming event–target pairs, while diagrammatic and textual equivalence holds by Theorem 3.1. By universality of minimal realization for observationally equivalent transition systems, $\mathcal{M}_1$ and $\mathcal{M}_2$ are monoidally equivalent. $\blacksquare$

---

### 5.4 Dynamic Asymptotic Convergence Theorem
**Theorem 5.4 (Asymptotic Convergence of Dynamics under Cognitive Finitude)**
Let $\mathcal{M}^*$ be the true dynamic model of a Field of Sense $\mathcal{SYS}$, and let $\mathcal{M}^{(0)} \to \mathcal{M}^{(1)} \to \cdots \to \mathcal{M}^{(n)} \to \cdots$ be a sequence of approximate dynamic models generated by a finite modeler via abductive refinement—specifically: (1) exclusive state partitioning (refining undifferentiated states in $\Sigma_A$ upon observing unexpected `Can't Happen` singularities, operational breakdowns, or deadlocks), and (2) decomposing monolithic conditional actions into pure functions, state-mutation DAGs, and arbitration aspects. Then spurious transitions and excess singularity regions contract monotonically, and in the inductive limit the sequence converges up to symmetric monoidal equivalence to the true model ($\varinjlim \mathcal{M}^{(n)} \simeq \mathcal{M}^*$).

**Proof Sketch:**
Exclusive state partitioning is the causal dual of static subclassing $\mathcal{R}_{\mathrm{sub}}$ (Paper 1, Theorem 5.4), monotonically pruning spurious transition trajectories. Since every action morphism decomposes into a finite DAG of primitive generators, the Yoneda Lemma and Density Theorem guarantee that colimits of representable approximations uniquely recover the true transition functor and monoidal category $\mathcal{DF}^*$ in the limit. $\blacksquare$

**Remark 5.1 (Faithful Simulation as Scientific Validation of Abductive Models)**
As argued in Paper 1 (Section 1.1), modeling by finite human minds proceeds through an interplay between **abduction** (hypothesizing underlying structural rules from observed intensions) and **deductive verification**. Because the integrated formalism of Conceptual Information Models, State Models, Data-Flow Action Models, and Universal Execution Semantics faithfully reproduces the behavioral dynamics of a Field of Sense—including transient inconsistencies, resource contention, and deadlocks—executing **meaningful simulations** under $\mathcal{E}_{\mathrm{exec}}$ serves as a rigorous, falsifiable scientific instrument to validate whether an abductively hypothesized model accurately captures the laws of the target domain.

---

### 5.5 Discrete Representation of Continuous Dynamics
In the physical world and many operational domains, continuous dynamics—such as object motion, temperature/pressure variations, or continuous asset valuations evolving smoothly along continuous time $t \in \mathbb{R}_{\ge 0}$ via differential equations or continuous flows—are routinely observed. By contrast, the present formalism of event-driven finite state machines and data flows is a discrete transition system. This raises the question of whether discrete state-transition models are merely coarse approximations or compromises when representing continuous reality. By applying projective limits ($\varprojlim$) and sheaf gluing conditions to the pullback of boundary-condition aspects introduced in Section 4 (Axiom E-4), I prove that discrete representations capture continuous dynamics without information loss (up to isomorphism).

**Theorem 5.5 (Discrete Representation Theorem: Sheaf and Projective Limit Isomorphism)**
Let $\Phi : T \times X \to X$ be a continuous-time dynamical system over $T = [0, \infty)$ on a topological space or manifold, and let $\{\mathcal{M}_{\varepsilon} \equiv \mathcal{M} \times_{\mathcal{C}_{\mathrm{FORM}}} \mathcal{V}_{\varepsilon}\}_{\varepsilon > 0}$ be a filtered projective system of discrete state-transition models parameterized by boundary-condition aspects $\mathcal{V}_{\varepsilon}$ specifying temporal step size $\Delta t = \varepsilon$ (via `TIM` timer events) and numerical precision. Then:
1. **Sheaf Gluing Condition:** Families of local discrete trajectories defined over open covers $\{U_i\}$ of $T$ glue uniquely into global trajectories whenever they agree on overlaps, forming a temporal sheaf $\mathcal{F}_{\mathrm{Sheaf}}$.
2. **Isomorphic Convergence in the Projective Limit:** In the projective limit as $\varepsilon \to 0$,
   $$\mathcal{M}_{\mathrm{cont}} \equiv \varprojlim_{\varepsilon \to 0} \left(\mathcal{M} \times_{\mathcal{C}_{\mathrm{FORM}}} \mathcal{V}_{\varepsilon}\right),$$
   the induced state-evolution system is categorically equivalent (topologically and structurally isomorphic) to the continuous dynamical system $\Phi$. Thus, continuous behavior requires no separate formalism and is rigorously encompassed as the limit structure of discrete event-driven state transitions and data flows.

**Proof Sketch:**
Pulling back timer intervals $\Delta t = \varepsilon$ from $\mathcal{EE}_{\mathrm{Time}}$ via $\mathcal{V}_{\varepsilon}$ induces discrete evolution operators $\mathcal{F}_{k\varepsilon} \to \mathcal{F}_{(k+1)\varepsilon}$ (analogous to Euler/Runge–Kutta discretizations). Coarse-graining projections $\pi_{\varepsilon', \varepsilon} : \mathcal{M}_{\varepsilon'} \to \mathcal{M}_{\varepsilon}$ ($\varepsilon' < \varepsilon$) form a projective system whose sheaf-glued projective limit completes discrete lattice trajectories into continuous solution trajectories, in exact structural analogy with constructing $\mathbb{R}$ as the projective limit/completion of dyadic rational grids. $\blacksquare$

---

### 5.6 Isomorphism with Physical Field Theories
Finally, as the culmination of this paper, I prove that the complete conceptual modeling architecture established in Paper 1 and the present paper (Paper 2) is mathematically isomorphic to the formal structure of foundational physical theories (such as classical mechanics, electromagnetism, relativity, and quantum field theory, consisting of equations of motion and universal laws of time evolution).

**Definition 5.2 (Category-Theoretic Specification of Physical Field Theories $\mathcal{P}_{\mathrm{Phys}}$)**
The canonical mathematical specification $\mathcal{P}_{\mathrm{Phys}}$ of a physical field theory or dynamical system comprises five structural components:
1. **Configuration / Field Space ($\mathcal{Q}$):** Degrees of freedom, physical quantity domains, and spatial coupling structures governing entities (particles or fields).
2. **Phase Space & Singularities ($\mathcal{P}$):** Exclusive state classifications and critical singularity boundaries where governing equations break down or undergo phase transitions.
3. **Equations of Motion / Local Operators ($\mathcal{L}_{\mathrm{eq}}$):** Differential or algebraic operators (derived from a Hamiltonian or Lagrangian density) governing local state evolution.
4. **External Forces / Boundary Conditions / S-Matrix ($\mathcal{B}_{\mathrm{ext}}$):** Non-opaque boundary ports mediating energy or signal exchange with external environments or coupled fields.
5. **Universal Time-Evolution & Causality ($\mathcal{U}_{\mathrm{dyn}}$):** Universal dynamical principles applied to the formal structure itself independent of specific matter content (principle of least action, light-cone locality, and conservation laws).

**Theorem 5.6 (Isomorphism Theorem with Physical Field Theories)**
The complete conceptual modeling architecture for a single Field of Sense,
$$\mathfrak{M}_{\mathrm{CM}} \equiv \left(\mathcal{C},\; \{M_A\}_{A \in \mathcal{K}},\; \mathcal{DF},\; \{F_{\mathrm{dom}}, \mathcal{E}^{\mathrm{public}}\},\; \mathcal{E}_{\mathrm{exec}}\right),$$
is categorically equivalent (structurally isomorphic) to a physical theory specification $\mathcal{P}_{\mathrm{Phys}} = (\mathcal{Q}, \mathcal{P}, \mathcal{L}_{\mathrm{eq}}, \mathcal{B}_{\mathrm{ext}}, \mathcal{U}_{\mathrm{dyn}})$ under a natural structure-preserving correspondence:

| Conceptual Modeling Architecture $\mathfrak{M}_{\mathrm{CM}}$ (Papers 1 & 2) | Physical Field Theory $\mathcal{P}_{\mathrm{Phys}}$ | Mathematical & Ontological Isomorphism |
| :--- | :--- | :--- |
| **1. Conceptual Information Model** (Schema Category $\mathcal{C}$) | **Configuration / Field Space** ($\mathcal{Q}$) | Static geometry of admissible entities (classes), quantities (7 data types), and relations (spans) |
| **2. State Model** (STT & `Can't Happen`) | **Phase Space & Singularities** ($\mathcal{P}$) | Exclusive coproduct state partitions ($\Sigma_A$) and critical phase-transition/breakdown boundaries ($0$) |
| **3. Action Model** (DAGs & New OAL) | **Equations of Motion / Operators** ($\mathcal{L}_{\mathrm{eq}}$) | Deterministic local state-update operators $\mathcal{F}_n \to \mathcal{F}_{n+1}$ (isomorphic to differential equations in the continuous limit) |
| **4. Domain Functions & Public Events** | **External Forces / Boundary Conditions / S-Matrix** ($\mathcal{B}_{\mathrm{ext}}$) | Opaque boundary ports mediating interaction via static data types ($\mathcal{D}_{\mathrm{static}}$) |
| **5. Universal Execution Semantics** ($\mathcal{E}_{\mathrm{exec}}$ on $\mathcal{C}_{\mathrm{FORM}}$) | **Universal Time-Evolution & Causality** ($\mathcal{U}_{\mathrm{dyn}}$) | Domain-independent dynamical laws applied to form itself (proper time, local inertial frames, invariant conservation) |

**Proof Sketch:**
By Theorem 5.5, discrete transitions $\mathcal{F}_n \to \mathcal{F}_{n+1}$ converge isomorphically to continuous evolution trajectories as $\varepsilon \to 0$. Under this correspondence: (1) instance sets, attributes, and relationship spans of $\mathcal{C}$ map bijectively to configuration spaces and tensor fields $\mathcal{Q}$; (2) state partitions $\Sigma_A$ and collapse boundaries ($0$) correspond to phase spaces and critical manifolds $\mathcal{P}$; (3) entry-action DAGs $\mathcal{A}_{s'}$ correspond to local evolution operators $\mathcal{L}_{\mathrm{eq}}$; (4) domain functions $F_{\mathrm{dom}}$ and public events correspond to external boundary couplings $\mathcal{B}_{\mathrm{ext}}$; and (5) just as physical principles such as least action and relativistic causality apply universally to the formal structure of field equations regardless of specific interactions, Universal Execution Semantics $\mathcal{E}_{\mathrm{exec}}$ applies universally to $\mathcal{C}_{\mathrm{FORM}}$ independent of domain content (Theorem 4.1). Hence $\mathfrak{M}_{\mathrm{CM}} \simeq \mathcal{P}_{\mathrm{Phys}}$. $\blacksquare$

**Corollary 5.1 (Unified Ontology of Information Systems and Physical Phenomena)**
Theorem 5.6 demonstrates that business and control models specified by human modelers and physical theories describing natural phenomena are not fundamentally disparate kinds of knowledge, but **the exact same mathematical structure evolving via universal execution semantics over forms inscribed on a Field of Sense**. This result bridges directly to cross-domain transformations and Green's function isomorphism (Paper 3) and the universal ontology of conceptual modeling encompassing the holographic principle (Paper 4).

---

---

## 6. Practical Implications and Conclusion

### 6.1 Mathematical Completion of Executable Modeling and Implications for Systems Engineering
The synthesis of static and dynamic modeling theories establishes decisive design principles for software engineering and systems architecture:

1. **Elevation to "Directly Executable Mathematical Models":** By equipping Conceptual Information Models and State Transition Tables with acyclic string diagrams of primitive process components and Universal Execution Semantics $\mathcal{E}_{\mathrm{exec}}$, models become complete, unambiguous, directly executable mathematical systems.
2. **Liberation from "Control Spaghetti":** Separating macro-level causal control into asynchronous event-driven instance state machines and confining intra-transition computations to acyclic DAG string diagrams structurally eliminates infinite action loops and state inconsistencies.
3. **Geometric Visualization of Bugs and Breakdowns:** Explicitly locating `Can't Happen` transitions, division by zero, and boundary violations as collapse points into the initial object $0$ (singularities) enables static topological verification at the model specification stage, including the **rigorous verification of code generated by generative AI**.

---

### 6.2 Conclusion and Outlook toward Paper 3 and Paper 4
Grounded in the static schema category from Paper 1, this paper formalizes causal state transitions and dynamic behavior within a single Field of Sense, proving four foundational results:

1. **Universal Execution Semantics and Homotopical Monoidal Closure:** Execution semantics are defined universally upon the conceptual model, forming a homotopically closed symmetric monoidal category $\mathcal{DF}$ that preserves static invariants.
2. **Four Dynamic Meta-Theorems:** The formalism achieves dynamic expressive completeness, dynamic isomorphism across representations, and dynamic asymptotic convergence.
3. **Discrete Representation of Continuous Dynamics:** Projective limits and sheaf gluing conditions capture smooth continuous physical and operational dynamics via discrete event-driven transitions without information loss.
4. **Structural Isomorphism with Physical Field Theories:** The integrated modeling architecture is mathematically isomorphic to the formal structure of foundational physical theories.

Looking ahead, **Paper 3** will expand this to multi-field interactions and structural transformations (modeled via Green's function propagators), while **Paper 4** will synthesize the series to demonstrate that conceptual modeling provides a universal ontological and mathematical formalism for the world itself, encompassing the Holographic Principle as an isomorphic special case (*Ordo Forma Est*).

---

## References

1. **Ota, H. (2026).** *Relation-Based Ontology and a Category-Theoretic Formalization of Fields of Sense: Structural Collapse via Linguistic Polysemy and Phenomena as the Intension of a Universe* (Version 1.0.1). Zenodo. https://doi.org
2. **Ota, H. (2026).** *Category-Theoretic Foundations of Conceptual Information Modeling: Rigorous Schema Representation, Isomorphism, and Asymptotic Refinement under Cognitive Finitude* (Version 1.0.0). Zenodo. https://doi.org
3. **Mac Lane, S. (1998).** *Categories for the Working Mathematician* (2nd ed.). Springer.
4. **Joyal, A., & Street, R. (1991).** *The Geometry of Tensor Calculus, I*. Advances in Mathematics, 88(1), 55–112.
5. **Coecke, B., & Kissinger, A. (2017).** *Picturing Quantum Processes: A First Course in Quantum Theory and Diagrammatic Reasoning*. Cambridge University Press.
6. **Lawvere, F. W. (1963).** *Functorial Semantics of Algebraic Theories*. Proceedings of the National Academy of Sciences of the United States of America, 50(5), 869–872.
7. **Mac Lane, S., & Moerdijk, I. (1992).** *Sheaves in Geometry and Logic: A First Introduction to Topos Theory*. Springer.
8. **Girard, J.-Y. (1987).** *Linear Logic*. Theoretical Computer Science, 50(1), 1–101.
9. **Moggi, E. (1991).** *Notions of Computation and Monads*. Information and Computation, 93(1), 55–92.
10. **Shlaer, S., & Mellor, S. J. (1992).** *Object Lifecycles: Modeling the World in States*. Yourdon Press.
11. **Mellor, S. J., & Balcer, M. J. (2002).** *Executable UML: A Foundation for Model-Driven Architecture*. Addison-Wesley.
12. **Milner, R. (1989).** *Communication and Concurrency*. Prentice Hall.
13. **Peirce, C. S. (1903/1998).** *Pragmatism as the Logic of Abduction*. In *The Essential Peirce: Selected Philosophical Writings*, Vol. 2 (1893–1913), Indiana University Press.
14. **Gabriel, M. (2015).** *Fields of Sense: A New Realist Ontology*. Edinburgh University Press.
15. **xtUML Project / One Fact Inc.** *BridgePoint xtUML Object Action Language (OAL) Reference*. Open Source xtUML Project. Available at: https://xtuml.org
16. **Starr, L. (2001).** *Executable UML: How to Build Class Models*. Prentice Hall.
