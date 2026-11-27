# Category-Theoretic Foundations of Conceptual Information Modeling: Rigorous Schema Representation, Isomorphism, and Asymptotic Refinement under Cognitive Finitude

## Abstract
In our preceding paper (Paper 0), I established an ontology grounded in relations (span structures) rather than isolated objects, formalizing how the world is partitioned into a Universe of multiple "Fields of Sense" connected by "Bridges" in order to avoid structural collapse caused by the inherent polysemy of everyday language. Furthermore, I demonstrated that observed "phenomena" constitute the "intension" of this Universe, and proved that it is in principle impossible to uniquely invert or reconstruct the global underlying structure solely from observed phenomena.

Accepting this epistemological limitation, the present paper (Paper 1) aims to provide affirmative mathematical answers to three fundamental questions: (1) For any given Field of Sense, does a valid schema governing its semantic structure necessarily exist? (2) If such a schema exists, is it unique—or mutually isomorphic across different representations? (3) Can human beings, possessing only finite memory and finite cognitive capacity, asymptotically approach the true underlying schema through iterative inquiry?

While modeling (abstraction) is commonly misunderstood as discarding details to render descriptions vague, this paper argues the exact opposite: eliminating ambiguity and establishing a concrete, rigorous structure is a necessary condition for a sound instance model (Field of Sense) to exist without contradiction. Specifically, I formalize the schema governing a single Field of Sense as a finitely complete and finitely cocomplete quotient 2-category equipped with identifiers (monomorphisms), strictly bounded data types, referential properties factored via commutative diagrams, bidirectional relationships bearing semantic phrases (2-morphisms) and four primitive multiplicities, exclusive coproduct decompositions (`Is-a`), multi-legged spans (associative classes), and axioms prohibiting self-loops (identity-link collapse). Within this rigorous framework, I prove: (i) the expressive completeness of this minimal formalism and the constructive existence of sound models, (ii) the categorical equivalence (isomorphism) of models that adequately capture the same Field of Sense, and (iii) an asymptotic convergence theorem—grounded in the Yoneda Lemma and the Density Theorem—showing how finite human cognition refines initial approximate models (containing `0..1` or `Nullable` ambiguities) into the true schema via subclassing and associative-class reification. Finally, I demonstrate that existing visual notations such as UML and ER diagrams function as rigorous, meaningful schema representations only when grounded in the category-theoretic semantics derived herein.

---

## 1. Introduction

### 1.1 Background and Problem Statement: From Limits of Observation to Ontology of Schemas
In Paper 0, starting from an ontology in which relations (span structures) rather than standalone objects ("things") serve as the primary substrate of reality, I formalized in category-theoretic terms how the world is partitioned into a Universe $\mathcal{U}$ comprising multiple "Fields of Sense" governed by schema categories and connected via "Bridges," thereby preventing semantic structures from collapsing into trivial identity morphisms under linguistic polysemy. Moreover, I proved that humanly observed "phenomena" manifest as the "intension" (projection via forgetful functors) of this Universe, and that it is fundamentally impossible to uniquely invert or reconstruct the global underlying structure (schema categories and states) solely from observed phenomena.

This proof of epistemological limitation immediately confronts this inquiry with three fundamental and practical questions:

1. **The Question of Existence:** If the underlying structure cannot be uniquely inverted from observation, can one assert that for any given Field of Sense, a valid schema consistently governing its semantic structure *necessarily exists*?
2. **The Question of Uniqueness and Isomorphism:** Assuming a valid schema exists, is it uniquely determined? Or, when multiple models are constructed using different representational forms, do they essentially reduce to being *isomorphic* (categorically equivalent)?
3. **The Question of Asymptotic Refinement:** Given that human beings possess only finite memory and finite cognitive capacity and cannot survey the entire structure at once, is it in principle possible to progressively approach the true underlying schema through iterative trial and error?

The objective of this paper (Paper 1) is to provide affirmative mathematical answers to all three questions. To achieve this, I deductively derive the rigorous formal specification required to describe the schema of a single Field of Sense—namely, the specification of a *Conceptual Information Model*—using category theory (quotient 2-categories and functorial semantics).

The third question, in particular, directly connects to the category-theoretic formalization of **abduction** (hypothesis formation) as the primary mode of inference in scientific inquiry and human modeling. Whereas *deduction* (deriving phenomena/intensions from a fixed schema) is uniquely determined, and *induction* (merely accumulating statistical regularities from observed data) cannot identify underlying structural principles, the essence of modeling by finite human minds lies in abductively hypothesizing a schema category $\mathcal{C}$ that most coherently explains observed phenomena, and iteratively refining it through an adjoint interplay of deductive verification and structural revision.

### 1.2 Paradigm Shift: Refuting "Modeling as Vague Abstraction"
In conventional software engineering and general modeling practice, there persists a widespread misconception that "modeling (abstraction) means discarding details to make descriptions rough and ambiguous." However, from the perspective of function spaces and functorial semantics, this conventional view is fundamentally flawed.

For a Field of Sense to be said to "reliably exist as a meaningful structure," there must exist non-trivial structure-preserving functors $\mathcal{F}$ (instance models) defined on the schema category $\mathcal{C}$ without internal contradiction ($\mathrm{Valid}(\mathcal{C}) \neq \emptyset$). If a schema is left ambiguous—for instance, if data-type value domains are ill-defined, injective individual identifiers are missing, or undifferentiated exceptions such as `0..1`, `Nullable`, and self-referential loops are permitted—then either constraints clash so that no sound model exists at all (structural breakdown), or infinitely many spurious models intrude, making it impossible to claim that the intended Field of Sense uniquely exists (explosion of indeterminacy).

Consequently, **modeling is not making things vague; rather, it must be the disciplined act of stripping away ambiguity to establish concrete, rigorous boundaries and constraints**. As demonstrated in this paper, the structural constructs of conceptual information modeling—data types, single and composite identifiers, referential properties via commutative diagrams, bidirectional relationships with semantic phrases and four multiplicities, exclusive coproduct decompositions (`Is-a`), and multi-legged spans (associative classes)—are not mere empirical rules of thumb or notational conventions. They are the **mathematically necessary and sufficient conditions required for the Universe and Fields of Sense introduced in Paper 0 to subsist without contradiction as forms of reality**.

### 1.3 Separation of Syntax and Semantics, and Structure of This Paper
This conclusion provides decisive guidance for practical modeling. Existing graphical notations such as UML (Unified Modeling Language) class diagrams and ER (Entity-Relationship) diagrams are, in themselves, merely *visual syntaxes* for drawing boxes and lines; the notation alone possesses no power to guarantee the validity of a model. Although UML is backed by the **MOF (Meta-Object Facility)** as a metamodeling infrastructure, MOF relies on a monistic, top-down hierarchy anchored by a single privileged meta-metamodel (M3). Consequently, MOF cannot satisfy the pluralistic, ontological requirement presupposed in Paper 0 and this work—namely, the rejection of a single overarching Universe in favor of autonomous Fields of Sense coexisting on a flat, equal footing. Conversely, when grounded not in a monistic meta-hierarchy but in the category-theoretic and ontological semantics derived herein, existing notations such as UML and ER diagrams function seamlessly as rigorous languages for expressing schemas of Fields of Sense.

The remainder of this paper is organized as follows:
* **Section 2** defines the basic components of conceptual information models, formalizes the schema category $\mathcal{C}$ of a single Field of Sense as a quotient 2-category ($\mathcal{C} \equiv CG/\mathcal{R}$), establishes the equivalence between instance functors and instance categories via the category of elements, and classifies the seven static data types ($\mathcal{D}_{\text{static}}$) while excluding array types.
* **Section 3** formalizes conceptual classes and identifiers (monomorphisms), bidirectional relationships with four primitive multiplicities, semantic phrases (2-morphisms) and propositional sentence generation, referential properties via commutative diagrams, and structural classifications (`Is-a` as exclusive coproducts and associative classes as span vertices).
* **Section 4** establishes the non-degeneracy axiom prohibiting diagonal embedding (identity self-loops) and the closure of internal topos logic defining the boundary of nonsense.
* **Section 5** proves four foundational theorems within this rigorous framework: (1) the Expressive Completeness Theorem (Theorem 5.1), (2) the Constructive Existence Theorem (Theorem 5.2), (3) the Isomorphism / Categorical Equivalence Theorem (Theorem 5.3), and (4) the Asymptotic Convergence Theorem under cognitive finitude (Theorem 5.4).
* **Section 6** discusses practical implications for visual notations (including the inherent irreversibility of round-trip engineering) and outlines the transition to dynamic modeling in Paper 2.

---

## 2. Schema Categories and Data Types of a Field of Sense

### 2.1 Instance Models as the Starting Point of Cognition and the Necessity of Classification
Before entering the formal definition of a conceptual information model (schema), it is necessary to clarify how models originate in human cognition—namely, the structure of an **Instance Model**.

As argued in Paper 0, what human beings first encounter in engaging with the world are "phenomena" (the intension of the Universe). From a phenomenological standpoint (akin to Husserl's *epoché*), when we suspend preconceptions and attend directly to immediate phenomena, the primary elements that emerge are individual entities ("objects" or *instances*) that can be demonstratively pointed out and distinguished in thought, together with their accompanying *property values* (for example, a particular apple before us along with its "redness" and "weight"). Furthermore, as emphasized in the philosophy of language from Frege to Wittgenstein, the world is not a mere heap of isolated objects, but a network of states of affairs in which objects are interconnected by **semantic links** bearing bidirectional predicates (phrases).

However, as noted in Paper 0, human beings—constrained by finite memory and finite cognitive capacity—cannot comprehend the world by assigning ad-hoc individual labels to every newly encountered entity and link from scratch. Only by **classifying** individuals that share common property structures and relational patterns into unified types (templates) can a finite mind bring intelligible order to infinitely varied phenomena. This system of classification governing concrete networks of instances and semantic links (instance models) is precisely what constitutes a **Conceptual Information Model (Schema)**.


### 2.2 Basic Components and Terminological Conventions
The comprehensive conceptual model governing structure and behavior within a single Field of Sense comprises three sub-models: the **Conceptual Information Model** (describing static semantic structure), the State Model (describing temporal state transitions of individuals), and the Data Flow Action Model (describing input-output process transformations). This paper focuses on the category-theoretic formalization of the foundational static layer: the **Conceptual Information Model**.

Prior to formalization, I stipulate its three primary building blocks:

1. **Conceptual Class:**
   A concept or classification of entities ("objects") manifesting within a Field of Sense, characterized by a fixed tuple of properties and relationships with other classes. Each conceptual class bears a unique name within its domain, and every individual instance in an instance model is instantiated from exactly one conceptual class.
2. **Property:**
   An attribute characterizing a conceptual class, bearing a unique name within that class. The admissible values and operations of each property are strictly constrained by a domain-defined *Data Type*.
3. **Relationship:**
   A semantic relation defined between two conceptual classes (including recursive relations on a single class), serving as the template for *semantic links* connecting individual instances.
   * *Terminological Note (Relation vs. Relationship):* Mathematically and category-theoretically, the construct defined here is strictly a **Relation**. We adopt the term **Relationship** solely to maintain terminological alignment with standard conventions in relational database theory and software engineering; conceptually and formally, it denotes a rigorous mathematical relation realized via bidirectional morphisms and span structures.

### 2.3 Construction of the Schema Category as a Quotient 2-Category (Axiom C-Base)
A conceptual information model is not a mere collection of boxes and lines; mathematically, it is defined as a **finitely complete and finitely cocomplete quotient 2-category** obtained by imposing static consistency constraints (congruence relations) upon a free category generated from a directed graph schema.

**Definition 2.1 (Schema Category $\mathcal{C}$: Axiom C-Base)**
For a given Field of Sense, the object space (0-cells) $\mathrm{Ob}(\mathcal{C})$ of its schema category $\mathcal{C}$ is constructed as the disjoint union of three mutually disjoint sets:
$$\mathrm{Ob}(\mathcal{C}) = \mathcal{K} \sqcup \mathcal{D}_{\text{static}} \sqcup \mathcal{EE}$$
where:
1. $\mathcal{K}$ is a finite set of **Conceptual Classes** (each uniquely named within the domain),
2. $\mathcal{D}_{\text{static}}$ is the set of admissible **Static Data Types**, and
3. $\mathcal{EE}$ is the set of **External Entities** serving as boundary interfaces to autonomous external universes (such as time, character strings, physical laws, or international standards).

Let $CG$ denote the free 2-category generated by directed edges representing property morphisms and bidirectional relationship morphisms among $\mathcal{K}$, $\mathcal{D}_{\text{static}}$, and $\mathcal{EE}$, together with 2-morphisms representing the semantic phrases attached to relationship ends. The schema category $\mathcal{C}$ is uniquely defined as the quotient 2-category of $CG$ modulo the congruence relation $\mathcal{R}$ induced by the static consistency axioms (Axioms C-1 through C-5) specified below:
$$\mathcal{C} \equiv CG / \mathcal{R}$$

Through this quotient construction, distinct navigation paths or referential expressions that resolve to the same identifier or semantic target are unified into a single equivalence class of morphisms within $\mathcal{C}$. Thus, stating that a schema category $\mathcal{C}$ "exists as a consistent form of reality" means that $\mathcal{C}$ does not collapse into the initial object $0$ (the empty space) and admits non-trivial structure-preserving functors.

### 2.4 Equivalence of Instance Functors and Instance Categories
A concrete state of a Field of Sense instantiated from a schema category $\mathcal{C}$ (an *instance model*) is formalized in functorial semantics as a structure-preserving functor out of $\mathcal{C}$.

**Definition 2.2 (Instance Functors and the Valid State Space $\mathrm{Valid}(\mathcal{C})$)**
An **instance model** for a schema category $\mathcal{C}$ is a finite-limit and finite-colimit preserving 2-functor $\mathcal{F} : \mathcal{C} \to \mathbf{2\text{-}Set}$ (where $\mathbf{2\text{-}Set}$ denotes the 2-category of sets, functions, and natural logical constraints). For each conceptual class $A \in \mathcal{K}$, $\mathcal{F}(A)$ assigns the set of individuals existing at a given instant, and for each morphism $f : X \to Y$, $\mathcal{F}(f)$ assigns the corresponding property values or semantic links. The functor category of all instance functors satisfying every axiom of $\mathcal{C}$ is denoted $\mathrm{Valid}(\mathcal{C})$.

The perspective introduced in Paper 0—viewing an instance model as an *instance category* $\mathcal{I}$ whose objects are individual instances and whose morphisms are semantic links—and the present perspective of a *structure-preserving functor* $\mathcal{F}$ are in exact one-to-one correspondence via the **Category of Elements ($\int \mathcal{F}$)** and **Discrete Fibrations**.

**Proposition 2.1 (Equivalence of Instance Functors $\mathcal{F}$ and Instance Categories $\mathcal{I}$)**
For any instance functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$, let $\mathcal{I} \equiv \int \mathcal{F}$ be the category whose objects are pairs $(A, a)$ ($A \in \mathcal{K},\, a \in \mathcal{F}(A)$) and whose morphisms are semantic links $(A, a) \to (B, b)$ corresponding to $\mathcal{F}(r)(a) = b$ for schema morphisms $r : A \to B$. The canonical projection $\pi : \int \mathcal{F} \to \mathcal{C}$ forms a discrete fibration. Conversely, any discrete fibration $\pi : \mathcal{I} \to \mathcal{C}$ uniquely determines (up to natural isomorphism) a structure-preserving functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$ assigning to each $A$ its fiber $\pi^{-1}(A)$.

By this equivalence, the existence of an instance functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$ ($\mathrm{Valid}(\mathcal{C}) \neq \emptyset$) is mathematically identical to the existence of a consistent instance category $\mathcal{I}$ governed by the schema $\mathcal{C}$.

### 2.5 Rigorous Classification of Static Data Types ($\mathcal{D}_{\text{static}}$)
For a schema category $\mathcal{C}$ to be constructed without ambiguity, the value domains and admissible operations of class properties—the static data-type space $\mathcal{D}_{\text{static}}$—must be strictly closed. To eliminate structural ambiguity and out-of-bounds state spaces, variable- and fixed-length array types are excluded in principle. Only the disjoint union of the following **seven mutually disjoint type categories** is permitted:

$$\mathcal{D}_{\text{static}} = \mathcal{D}_{\text{Scalar}} \sqcup \mathcal{D}_{\text{UID}} \sqcup \mathcal{D}_{\text{REF}} \sqcup \mathcal{D}_{\text{Enum-Int}} \sqcup \mathcal{D}_{\text{Enum-Ext}} \sqcup \mathcal{D}_{\text{Ext}} \sqcup \mathcal{D}_{\text{Struct}}$$

1. **Scalar Complete Objects ($\mathcal{D}_{\text{Scalar}}$):**

   Numeric sorts closed under internal algebraic operations (integers $\mathbb{Z}$, reals $\mathbb{R}$, complex numbers $\mathbb{C}$), together with domain-specific range-restricted subobjects. Any operation exceeding domain bounds or dividing by zero collapses via pullback into the initial object $0$ (empty space).
2. **Persistent Unique Identifiers ($\mathcal{D}_{\text{UID}}$):**

   System-generated identifier spaces (`Unique-ID`) guaranteeing strict injectivity (monomorphism) across past, present, and future state transitions.
3. **Referential Types ($\mathcal{D}_{\text{REF}}$):**

   Types (`Reference`) pointing to the identifier ($\mathcal{D}_{\text{UID}}$, etc.) of a related conceptual class. Rather than an independent primitive sort, $\mathcal{D}_{\text{REF}}$ is dynamically derived via composition with relationship morphisms (formalized in Definition 3.4).
4. **Endogenous Complete-Lattice Enumerations ($\mathcal{D}_{\text{Enum-Int}}$):**

   Finite sets of two or more distinct symbolic constants arising from the internal logic of the Field of Sense itself, formalized as finite coproducts $\coprod_{i=1}^m \mathbf{1}$ (e.g., `{'Blue', 'Yellow', 'Red'}`).
5. **Exogenous Projected Enumerations ($\mathcal{D}_{\text{Enum-Ext}}$):**

   Finite choice sets imported via pullback from standardized external universes $\mathcal{EE}$ (e.g., ISO country codes, days of the week).
6. **External-Entity Projected Types ($\mathcal{D}_{\text{Ext}}$):**

   Minimal operational interfaces (value domains and admissible operators) projected from vast autonomous external universes such as time ($\mathcal{EE}_{\text{Time}}$) or character strings ($\mathcal{EE}_{\text{String}}$, treated as a free monoid $\Sigma^*$).
   * *Remark (Boundary Isolation for Constructibility):* Internalizing the full foundational construction of real numbers (e.g., Dedekind cuts) or relativistic spacetime metrics inside an ordinary application domain is unnecessary. By explicitly delegating their internal mechanics to an external Field of Sense ($\mathcal{EE}$) while specifying only the minimal interface form and operators required locally, finiteness and constructibility of $\mathcal{C}$ are preserved.
7. **Finite Product Composite Types ($\mathcal{D}_{\text{Struct}}$):**

   Finite nested Cartesian products ($\mathcal{M} \cong \prod_{i=1}^n \mathcal{D}_i$) composed of types from categories 1–6 (and other composite types) under uniquely named sub-fields.

---

## 3. Category-Theoretic Formalization of Conceptual Classes and Relationships

### 3.1 Conceptual Classes and Single/Composite Identifiers (Axiom C-1)
In the schema category $\mathcal{C}$, each conceptual class $A \in \mathcal{K}$ is equipped with a finite family of property morphisms
$$\{\mathrm{attr}_i : A \to T_i\}_{i \in \Lambda_A} \quad (T_i \in \mathcal{D}_{\text{static}})$$
where property names are unique within $A$. For entities ("objects") to be distinguishable as individuals within a Field of Sense, there must exist identifying tuples of properties that uniquely determine each instance.

**Definition 3.1 (Identifiers and Monomorphism Constraint: Axiom C-1)**

Each conceptual class $A \in \mathcal{K}$ possesses a non-empty family of candidate identifiers $\mathcal{U}_A \subseteq \mathcal{P}(\Lambda_A) \setminus \{\emptyset\}$. For every identifier $I = \{i_1, \dots, i_k\} \in \mathcal{U}_A$, the universal mediating morphism into the product of its property types,
$$\alpha_I = \langle \mathrm{attr}_{i_1}, \dots, \mathrm{attr}_{i_k} \rangle : A \longrightarrow \prod_{j=1}^k T_{i_j},$$
must be a **monomorphism** in $\mathcal{C}$.

Consequently, under any valid instance functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$, the image $\mathcal{F}(\alpha_I) : \mathcal{F}(A) \to \prod_{j=1}^k \mathcal{F}(T_{i_j})$ is an injective function in $\mathbf{Set}$. No two distinct instances of the same class can share identical values across all identifying properties, geometrically guaranteeing individuality for both single ($k=1$) and composite ($k \ge 2$) identifiers. Multiple candidate identifiers ($\lvert \mathcal{U}_A \rvert \ge 1$) are permitted.

### 3.2 Bidirectional Relationships and the Four Multiplicity Primitives

A binary relationship $R$ defined between conceptual classes $O, T \in \mathcal{K}$ (including recursive cases where $O = T$) carries a unique domain index and is obligatorily annotated at both ends with a **multiplicity** and a **semantic phrase**.

**Definition 3.2 (Bidirectional Relationships and Multiplicity Basis)**

A relationship $R$ between $O, T \in \mathcal{K}$ is formalized as an opposing pair of 1-morphisms $(r^{\rightarrow} : O \to T,\, r^{\leftarrow} : T \to O)$ (or equivalently as a span $O \xleftarrow{p_O} R \xrightarrow{p_T} T$). The multiplicities $m_O, m_T$ at both ends take values in the **four-element basis** proven necessary and sufficient to capture structural connection topologies:
$$m_O, m_T \in \{\, \mathbf{1},\; \mathbf{0..1},\; \mathbf{1..*},\; \mathbf{*} \,\}$$
* **$\mathbf{1}$ (Total Functional):** Fiber cardinality is strictly $1$ (total function).
* **$\mathbf{0..1}$ (Partial Functional):** Fiber cardinality is $0$ or $1$ (partial function).
* **$\mathbf{1..*}$ (Total Relational):** Fiber cardinality is $\ge 1$ (surjective/total relation).
* **$\mathbf{*}$ (General Relational):** Fiber cardinality is $\ge 0$, permitting up to countably infinite ($\infty$) links.

In every valid instance model $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$, the cardinality of the preimage fiber $\mathcal{F}(p_O)^{-1}(o)$ for any instance $o \in \mathcal{F}(O)$ is strictly bounded by $m_T$.

### 3.3 Semantic Phrases (2-Morphisms) and Propositional Derivation (Axiom C-0)
What elevates a relationship from an unlabeled graph edge to a semantic structure is the pair of semantic phrases attached to its ends, which maps instance links directly into propositional statements of fact.

**Definition 3.3 (Semantic Phrases and Non-Duplication Constraints)**

The semantic phrases $P_O, P_T$ attached to the $O$-end and $T$-end of a relationship $R$ are non-empty strings in the free monoid $\Sigma^*$, formalized in $\mathcal{C}$ as **2-morphisms (natural transformations)** $\mu_O, \mu_T$ accompanying the relationship morphisms. To ensure unambiguous semantics:
1. The two phrases attached to opposite ends of the same relationship $R$ must be distinct ($P_O \neq P_T$).
2. If multiple relationships $R_1, R_2$ exist between the same pair of classes $(O, T)$, their ordered phrase pairs must be distinct ($(P_{O,1}, P_{T,1}) \neq (P_{O,2}, P_{T,2})$).

**Proposition 3.1 (Derivation of Elementary Propositions and Topos Truth Evaluation: Axiom C-0)**

Each relationship specification in a conceptual information model automatically generates templates for elementary propositional sentences describing instance states:
1. **Binary Relationship:** For instances $o:O$ and $t:T$, bidirectional propositions
   $$\text{"}\underline{o:O}\;\; P_T \;\;\underline{t:T}\text{"} \quad \text{and} \quad \text{"}\underline{t:T}\;\; P_O \;\;\underline{o:O}\text{"}$$
   are derived.
2. **Specialization (`Is-a`):** For supertype $O$ and subtype $T$, the proposition $\text{"}\underline{t:T}\;\; \text{is-a} \;\;\underline{o:O}\text{"}$ is derived.
3. **Associative Class:** For an associative instance $a:A$, propositions $\text{"}\underline{a:A}\;\; P_O \;\;\underline{o:O}\text{"}$ and $\text{"}\underline{a:A}\;\; P_T \;\;\underline{t:T}\text{"}$ are derived.

Under $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$, the 2-morphism $\mathcal{F}(\mu)$ induces a characteristic evaluation into the subobject classifier $\Omega = \{\mathrm{True}, \mathrm{False}\}$, evaluating to $\mathrm{True}$ if and only if the corresponding semantic link exists in the instance model. Moreover, because morphism composition in $\mathcal{C}$ is associative, chaining propositions across multiple relationships (navigation) is uniquely well-defined.

### 3.4 Commutative Factorization of Referential Properties (Axioms C-1.5, C-4)
In an instance model, the existence of a semantic link between two instances is encoded by matching the value of a property on one instance with the identifier value of the target instance. Such attributes are termed **Referential Properties**.

**Definition 3.4 (Commutative Factorization of Referential Properties: Axioms C-1.5, C-4)**

When class $B$ references class $A$ via a relationship morphism $r : B \to A$, the referential property tuple $\beta_{B \to A} : B \to \prod_{j=1}^k T_{i_j}$ on $B$ is not an independent static type; rather, it is equationally constrained to factor as the **composition** of $r$ with one of $A$'s identifier monomorphisms $\alpha_I : A \to \prod_{j=1}^k T_{i_j}$:
$$\beta_{B \to A} = \alpha_I \circ r$$

```text
          r
    B ---------> A

    |            |
    |            | α_I (Identifier morphism: monic)
    | β_{B->A}   v
    +----------> ∏ T_i  (Referential property type matches identifier type)
```

Because this commutative diagram is built directly into the congruence relation $\mathcal{R}$ of the quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$, referential data types automatically match target identifier types, and dangling references (pointing to non-existent identifiers) are structurally impossible.

### 3.5 Structural Classifications: `Is-a` and Associative Classes (Axioms C-2, C-3)
To support rigorous semantic classification beyond simple binary links, two structural relationship constructs are defined.

**Definition 3.5 (`Is-a` as Exclusive Coproduct Decomposition: Axiom C-3)**

An `Is-a` relationship between a superclass $S \in \mathcal{K}$ and a finite family of subclasses $\{C_1, C_2, \dots, C_n\} \subset \mathcal{K}$ is defined via inclusion morphisms $\{\iota_i : C_i \to S\}_{i=1}^n$ such that $S$ is isomorphic to the **coproduct (disjoint union)** of its subclasses, and pairwise intersections vanish (exhaustive and mutually exclusive partitioning):
$$S \cong \coprod_{i=1}^n C_i, \qquad C_i \times_S C_j \cong 0 \quad (\forall i \neq j)$$
Furthermore, each subclass's referential property satisfies $\beta_{C_i \to S} = \alpha_{I_S} \circ \iota_i$.
* *Remark (Distinction from Object-Oriented Inheritance):* Unlike inheritance in object-oriented programming—which is a mechanism for code reuse and differential extension—`Is-a` here signifies an **ontological partition**: an individual instance of $S$ simultaneously and exclusively belongs to exactly one concrete subtype $C_i$. This coproduct decomposition is the decisive mechanism that eliminates `0..1` and `Nullable` ambiguities in Section 5.

**Definition 3.6 (Associative Classes as Multi-Legged Span Vertices: Axiom C-2)**

When individual semantic links arising from a relationship between $O, T \in \mathcal{K}$ possess intrinsic properties or participate in further relationships, an **Associative Class** $A \in \mathcal{K}$ is introduced such that each link corresponds bijectively to one instance of $A$. Category-theoretically, $A$ is the vertex of a **span** $O \xleftarrow{p_O} A \xrightarrow{p_T} T$ whose mediating morphism
$$\langle p_O, p_T \rangle : A \longrightarrow O \times T$$
is a **monomorphism**, equipped with referential properties $\beta_{A \to O} = \alpha_{I_O} \circ p_O$ and $\beta_{A \to T} = \alpha_{I_T} \circ p_T$. Relations are thereby reified as first-class objects within $\mathcal{C}$.

---

## 4. Non-Degeneracy Axioms and Internal Logic Closure

### 4.1 Prohibition of Diagonal Embedding (Identity Self-Loops)
In Paper 0, I showed that unrestricted link identification causes distinct semantic morphisms to degenerate into identity morphisms, trivializing the entire semantic network. To prevent such internal collapse at both the schema and instance levels, I impose a strict non-degeneracy axiom.

**Definition 4.1 (Prohibition of Diagonal Embedding and Identity Degeneration)**

For every conceptual class $A \in \mathcal{K}$ in $\mathcal{C}$, two constraints prevent structural trivialization:
1. **Prohibition of Direct Self-Loops (Diagonal Embedding):**
   For any recursive relationship $r : A \to A$, an instance $a \in \mathcal{F}(A)$ is strictly prohibited from linking directly to itself—that is, no realized semantic link may fall into the image of the diagonal morphism $\Delta_{\mathcal{F}(A)} : a \mapsto (a, a)$ in $\mathcal{F}(A) \times \mathcal{F}(A)$:
   $$\forall A \in \mathcal{K},\; \forall r : A \to A,\; \forall a \in \mathcal{F}(A),\quad \mathcal{F}(\mu_r)(a, a) = \mathrm{False}$$
2. **Prohibition of Global Identity Collapse:**
   For composite paths $p = r_n \circ \dots \circ r_1 : A \to A$ ($n \ge 2$) traversing distinct classes or semantic phrases, closed cycles at the instance level (e.g., a commutative triangle $A \to B \to C \to A$) are legitimately permitted. However, the congruence relation $\mathcal{R}$ of $\mathcal{C}$ prohibits equating a non-trivial composite path $p$ with the pure identity morphism $\mathrm{id}_A$ ($p = \mathrm{id}_A$), which would erase semantic differentiation.

Any state attempting to instantiate a direct self-link $(a, a)$ fails pullback composition and automatically collapses into the initial object $0$ (empty space) of the internal topos logic.
* *Remark (Distinction from Implicate Topology):* Static schema optimizations that equalize a boundary reference morphism with $\mathrm{id}_A$ via an equalizer to eliminate surplus degrees of freedom (e.g., representing the head/tail of a linear sequence) operate at the schema level and are strictly distinct from instantiating dynamic self-links $(a, a)$.

### 4.2 Closure of Internal Logic and the Boundary of Nonsense (Axiom C-5)
Building on Proposition 3.1, I rigorously demarcate the domain of meaningful statements within a Field of Sense.

**Definition 4.2 (Closure of Internal Logic: Axiom C-5)**

The space of meaningful propositions $\mathcal{L}(\mathcal{SYS})$ admissible within a Field of Sense $\mathcal{SYS}$ governed by $\mathcal{C}$ is defined inductively solely from the vocabulary of $\mathcal{C}$ ($\mathcal{K}$, $\mathcal{D}_{\text{static}}$, and semantic phrases $\mu$).

**Proposition 4.1 (Trichotomy of Propositional Status and Incompleteness Boundary)**

Every proposition $\varphi$ falls exclusively into one of three categories:
1. **Meaningful and True ($\mathrm{True}$):** $\varphi \in \mathcal{L}(\mathcal{SYS})$ and $\varphi$ matches the realized links and property values of the current instance functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$.
2. **Meaningful and False ($\mathrm{False}$):** $\varphi \in \mathcal{L}(\mathcal{SYS})$ but $\varphi$ does not match the current state $\mathcal{F}$.
3. **Nonsense (Collapse to Initial Object $0$):** $\varphi \notin \mathcal{L}(\mathcal{SYS})$. Any statement unconstructible from $\mathcal{C}$ or mixing vocabulary from an external Field of Sense is neither true nor false; it is rejected as *nonsense* and mapped immediately to the initial object $0$.

Thus, truth evaluation within $\mathcal{SYS}$ is 100% self-contained without appealing to an overarching meta-universe. Simultaneously, the existence of statements undecidable within a single schema $\mathcal{C}$ mirrors Gödel's incompleteness theorem and Lawvere's fixed-point theorem, necessitating **Bridges** across distinct Fields of Sense (connecting Paper 0 and Paper 3).

## 5. Theorems of Completeness, Existence, Isomorphism, and Asymptotic Refinement

Having formalized the schema of a single Field of Sense as a quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$, I now prove four core theorems answering the three fundamental questions posed in Section 1.

### 5.1 Expressive Completeness Theorem: Representability of Arbitrary Static Structures
First, I prove that the minimal primitives defined in Sections 2–4 suffice to express the static semantic structure of *any* Field of Sense without requiring additional structural constructs.

**Theorem 5.1 (Expressive Completeness of the Conceptual Information Model Formalism)**

The static semantic structure of any Field of Sense $\mathcal{SYS}$ axiomatizable within the geometric fragment of first-order logic (Geometric Logic) and locally presentable categories is adequately representable as an appropriate quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$ adhering to the axioms of Sections 2–4. No additional primitives (such as direct $n$-ary relationship symbols for $n \ge 3$ or array types) are required.

#### Proof

**Proof Strategy (Overview):**
To establish expressive completeness, we invoke the standard correspondence between geometric logic, locally presentable categories, and categorical sketches. Specifically, any static semantic structure formalizable in geometric logic can be represented as a finite-limit, finite-colimit sketch $\mathbb{S}$. We demonstrate in four steps that every structural primitive of $\mathbb{S}$ reduces without loss of information to the minimal primitives of our quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$.

1. **Reduction of Arbitrary $n$-ary Relations to Associative Class Spans:**
   Suppose the target domain contains an arbitrary $n$-ary relation $R \subseteq X_1 \times X_2 \times \dots \times X_n$ ($n \ge 2$). We introduce an independent associative conceptual class $A_R \in \mathcal{K}$ equipped with $n$ projection morphisms $p_k : A_R \to X_k$ (each having multiplicity `1` on the $A_R$ end) and require the universal mediating morphism
   $$\langle p_1, p_2, \dots, p_n \rangle : A_R \hookrightarrow \prod_{k=1}^n X_k$$
   to be monic (the natural $n$-legged span extension of Axiom C-2). Under any structure-preserving 2-functor $\mathcal{F}$, the elements of $\mathcal{F}(A_R)$ are canonically identified with a subobject of $\prod_{k=1}^n \mathcal{F}(X_k)$, and any higher-order attributes attached to the relation itself become standard properties of $A_R$. Thus, all $n$-ary relations reduce to binary relationships and associative classes.

2. **Reduction of Finite Products, Equalizers, and Pullbacks to Identifiers and Referential Commutativity:**
   A binary product $A \times B$ is represented by a surjective associative span $A \xleftarrow{p_A} P \xrightarrow{p_B} B$ with multiplicity `1` on both ends whose carrier exhausts the Cartesian product. Equalizers of parallel morphism pairs $f, g : A \rightrightarrows B$ and general pullbacks $A \times_C B$ are uniquely realized through the commutative diagram equations imposed by the congruence relation $\mathcal{R}$ (specifically, the referential property equations $\beta_{B \to A} = \alpha_I \circ r$ in Axioms C-1.5 and C-4) together with monic identifier morphisms $\alpha_I$ (Axiom C-1).

3. **Reduction of Finite Coproducts and Subobject Classification to `Is-a`, Enumerations, and the Four Multiplicities:**
   Any disjoint union decomposition (finite coproduct) in the domain is captured by the exclusive and exhaustive `Is-a` partition $S \cong \coprod_{i=1}^m C_i$ (Axiom C-3), while finite sets of constant alternatives are represented by intrinsic or extrinsic enumeration types ($\mathcal{D}_{\mathrm{Enum-Int}}, \mathcal{D}_{\mathrm{Enum-Ext}}$). Furthermore, any binary cardinality constraint is topologically spanned by the $2 \times 2 = 4$ combinations of totality (lower bound $0$ vs. $1$) and functionality/injectivity (upper bound $1$ vs. countable infinity $\infty$), corresponding precisely to the four multiplicity primitives (`1`, `0..1`, `1..*`, `*`).

4. **Categorical Equivalence of Model Categories (Sketch Theorem):**
   By the reductions above, the category of models $\mathrm{Mod}(\mathbb{S})$ of the geometric sketch $\mathbb{S}$ is canonically equivalent to the category of valid structure-preserving 2-functors $\mathrm{Valid}(\mathcal{C})$ over the quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$ (Barr–Wells Sketch Theorem and Gabriel–Ulmer Duality):
   $$\mathrm{Mod}(\mathbb{S}) \simeq \mathrm{Valid}(\mathcal{C}).$$
   Hence, no additional primitives are required to express any static semantic structure. $\blacksquare$

---

### 5.2 Existence Theorem: Constructive Reality of Rigorous Schema Categories
Next, I prove that imposing strict consistency constraints does not render a schema category vacuous; rather, any well-formed schema category $\mathcal{C}$ admits non-trivial sound instance models.

**Theorem 5.2 (Consistency and Constructive Existence of Rigorous Schema Categories)**

For any schema category $\mathcal{C} \equiv CG/\mathcal{R}$ satisfying all axioms of Sections 2–4 (data-type closure, identifier monicity, referential commutativity, `Is-a` coproduct exclusivity, associative span injectivity, multiplicity consistency, and diagonal non-degeneracy), there constructively exists a non-trivial structure-preserving functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$; that is,
$$\mathrm{Valid}(\mathcal{C}) \neq \emptyset.$$
Hence, $\mathcal{C}$ exists as a consistent, effective form of reality.

#### Proof

**Proof Strategy (Overview):**
We prove $\mathrm{Valid}(\mathcal{C}) \neq \emptyset$ by constructive induction. By the universal property of the quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$, constructing a valid 2-functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$ is equivalent to constructing a 2-functor $\widetilde{\mathcal{F}} : CG \to \mathbf{2\text{-}Set}$ on the free 2-category $CG$ that respects all defining relations of $\mathcal{R}$ and Axioms C-0–C-5. We proceed via four lemmas: (1) populating the `Is-a` hierarchy inductively from leaf classes, (2) embedding identifiers injectively into static data types, (3) constructing links via bijections and cyclic shift permutations to satisfy both multiplicity constraints and non-diagonality simultaneously, and (4) descending to $\mathcal{C} \equiv CG/\mathcal{R}$.

1. **Lemma 1 (Acyclicity of the `Is-a` Hierarchy and Inductive Class Population):**
   In any conceptual class set $\mathcal{K}$ satisfying Axiom C-3 (exclusive `Is-a` specialization) and the Non-Degeneracy Axiom (prohibition of identity collapse), the specialization graph formed by inclusion morphisms $\iota_i : C_i \to S$ is a finite directed acyclic graph (DAG). Indeed, any cycle $A_0 \to A_1 \to \dots \to A_m = A_0$ ($m \ge 1$) would either force $A_0$ to be isomorphic to a proper summand of itself or collapse a non-trivial composite path to $\mathrm{id}_{A_0}$, contradicting Axiom C-3 and non-degeneracy.
   By topological sorting, there exists a non-empty set of leaf classes $\mathcal{K}_{\mathrm{leaf}}$ that have no subclasses. We assign to each leaf class $L \in \mathcal{K}_{\mathrm{leaf}}$ a pairwise disjoint, non-empty finite set $\widetilde{\mathcal{F}}(L)$ of cardinality $N \ge 2$. Inductively, for any superclass $S$ whose subclasses $\{C_1, \dots, C_n\}$ have already been populated, we define
   $$\widetilde{\mathcal{F}}(S) \equiv \coprod_{i=1}^n \widetilde{\mathcal{F}}(C_i)$$
   and map each inclusion $\iota_i$ to the canonical injection $\mathrm{in}_i$. Consequently, for all $i \neq j$, the pullback $\widetilde{\mathcal{F}}(C_i) \times_{\widetilde{\mathcal{F}}(S)} \widetilde{\mathcal{F}}(C_j) = \emptyset$ (the initial object $0$), strictly satisfying Axiom C-3.

2. **Lemma 2 (Data Type Assignment and Injective Identifier Embeddings):**
   To each static data type $T \in \mathcal{D}_{\mathrm{static}}$, we assign its standard non-empty carrier set $\widetilde{\mathcal{F}}(T)$ according to Definition 2.5 (e.g., corresponding number sets for $\mathcal{D}_{\mathrm{Scalar}}$, the countably infinite set $\mathbb{N}$ for $\mathcal{D}_{\mathrm{UID}}$, specified finite complete lattices of size $\ge 2$ for $\mathcal{D}_{\mathrm{Enum}}$, and the free monoid $\Sigma^*$ for $\mathcal{D}_{\mathrm{Ext}}$). For every class $A \in \mathcal{K}$ and candidate identifier $I = \{i_1, \dots, i_k\} \in \mathcal{U}_A$, let $\mathcal{P}_I \equiv \prod_{j=1}^k \widetilde{\mathcal{F}}(T_{i_j})$. Choosing the base leaf cardinality $N \ge 2$ in Lemma 1 such that $N \le \min_{A, I} |\mathcal{P}_I|$ guarantees $|\widetilde{\mathcal{F}}(A)| \le |\mathcal{P}_I|$. Fixing an injection into the full attribute product $\prod_{i \in \Lambda_A} \widetilde{\mathcal{F}}(T_i)$ and projecting onto each component $I$ yields an injective map $\widetilde{\mathcal{F}}(\alpha_I)$ for every $I \in \mathcal{U}_A$, satisfying Axiom C-1.

3. **Lemma 3 (Construction of Semantic Links Satisfying Multiplicities and Non-Diagonality):**
   - **Case 1: Distinct Classes ($O \neq T$):** Balancing carrier cardinalities to a common integer $M \ge 2$ compatible with `Is-a` sum constraints, we construct a bijective link graph $E_R = \{(o_s, t_s) \mid 1 \le s \le M\} \subseteq \widetilde{\mathcal{F}}(O) \times \widetilde{\mathcal{F}}(T)$. Because every fiber of a bijection has cardinality strictly equal to $1$, $E_R$ simultaneously satisfies all four multiplicity primitives (`1`, `0..1`, `1..*`, `*`).
   - **Case 2: Recursive Relationships ($O = T$):** For a self-referential relationship $r : A \to A$, we must exclude diagonal pairs $(a, a)$ (Definition 4.1). Writing $\widetilde{\mathcal{F}}(A) = \{a_0, a_1, \dots, a_{M-1}\}$ with $M \ge 2$, we define $E_R$ as the graph of the cyclic shift permutation $\sigma(a_s) \equiv a_{(s+1) \bmod M}$:
     $$E_R = \{(a_s, a_{(s+1) \bmod M}) \mid 0 \le s < M\}.$$
     Since $M \ge 2$, we have $a_s \neq a_{(s+1) \bmod M}$ for all $s$, ensuring $(a, a) \notin E_R$ ($\widetilde{\mathcal{F}}(\mu_r)(a, a) = \mathrm{False}$). Moreover, since $\sigma$ is a bijection, all four multiplicity constraints are simultaneously satisfied.
   - **Associative Classes and Commutative Cycles:** For an associative class $R_{\mathrm{assoc}}$, we set $\widetilde{\mathcal{F}}(R_{\mathrm{assoc}}) \equiv E_R$ with component projections $\widetilde{\mathcal{F}}(p_O), \widetilde{\mathcal{F}}(p_T)$, making the mediating map $\langle \widetilde{\mathcal{F}}(p_O), \widetilde{\mathcal{F}}(p_T) \rangle : E_R \hookrightarrow \widetilde{\mathcal{F}}(O) \times \widetilde{\mathcal{F}}(T)$ a canonical inclusion (hence monic, Axiom C-2). When multiple relationships form commutative cycles, assigning bijections generated by powers of a common cyclic group $\mathbb{Z}/M\mathbb{Z}$ preserves all path-composition equalities.

4. **Lemma 4 (Referential Properties and Descent to the Quotient 2-Category):**
   We define the image of every referential property morphism $\beta_{B \to A}$ required by Axioms C-1.5 and C-4 via composition $\widetilde{\mathcal{F}}(\beta_{B \to A}) \equiv \widetilde{\mathcal{F}}(\alpha_I) \circ \widetilde{\mathcal{F}}(r)$, assign to each 2-morphism $\widetilde{\mathcal{F}}(\mu)$ the characteristic truth map on $E_R$ (Axiom C-0), and map external vocabulary to the initial object $0$ (Axiom C-5). Since $\widetilde{\mathcal{F}}$ preserves all relations generating $\mathcal{R}$, the universal property of the quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$ induces a unique structure-preserving 2-functor $\mathcal{F} : \mathcal{C} \to \mathbf{2\text{-}Set}$ satisfying $\widetilde{\mathcal{F}} = \mathcal{F} \circ \pi_{\mathcal{R}}$ with $\mathcal{F}(A) \neq \emptyset$ for all $A \in \mathcal{K}$. Thus, $\mathcal{F} \in \mathrm{Valid}(\mathcal{C})$ and $\mathrm{Valid}(\mathcal{C}) \neq \emptyset$. $\blacksquare$

This theorem refutes the fallacy that abstraction requires vagueness: it is precisely because ambiguity is eliminated that contradiction-free instance models can be constructed, guaranteeing the reality of the schema category $\mathcal{C}$.

---

### 5.3 Isomorphism Theorem: Uniqueness Across Representational Variations
We now prove that two schema categories adequately capturing the same Field of Sense are categorically equivalent regardless of syntactic or representational differences.

**Definition 5.1 (Adequacy and Representational Equivalence)**

Let $\Omega_{\mathcal{SYS}}$ denote the valid state space of a target Field of Sense $\mathcal{SYS}$. A schema category $\mathcal{C}$ is said to **adequately represent** $\mathcal{SYS}$ if there exists a natural bijection between $\mathrm{Valid}(\mathcal{C})$ and $\Omega_{\mathcal{SYS}}$ preserving the truth valuation of all meaningful propositions in $\mathcal{L}(\mathcal{SYS})$.

**Theorem 5.3 (Schema Isomorphism Theorem: Uniqueness up to Categorical Equivalence)**

Any two schema categories $\mathcal{C}_1$ and $\mathcal{C}_2$ that adequately represent the same Field of Sense $\mathcal{SYS}$ are **categorically equivalent** ($\mathcal{C}_1 \simeq \mathcal{C}_2$), and their valid model categories are naturally equivalent ($\mathrm{Valid}(\mathcal{C}_1) \simeq \mathrm{Valid}(\mathcal{C}_2)$).

#### Proof

**Proof Strategy (Overview):**
When two schema categories $\mathcal{C}_1$ and $\mathcal{C}_2$ are both adequate for the same field of sense $\mathcal{SYS}$ (Definition 5.3), their categories of valid instance models are canonically equivalent via the state space $\Omega_{\mathcal{SYS}}$. We apply Lawvere functorial semantics and Gabriel–Ulmer reconstruction using evaluation 2-functors to construct quasi-inverse 2-functors $F : \mathcal{C}_1 \to \mathcal{C}_2$ and $G : \mathcal{C}_2 \to \mathcal{C}_1$, proving $\mathcal{C}_1 \simeq \mathcal{C}_2$.

1. **Embedding Schemas via Evaluation 2-Functors:**
   By adequacy, there exists an equivalence of model categories
   $$\Phi : \mathrm{Valid}(\mathcal{C}_1) \xrightarrow{\;\sim\;} \mathrm{Valid}(\mathcal{C}_2), \qquad \Psi : \mathrm{Valid}(\mathcal{C}_2) \xrightarrow{\;\sim\;} \mathrm{Valid}(\mathcal{C}_1)$$
   preserving all internal logical truth evaluations, with $\Psi \circ \Phi \cong \mathrm{Id}_{\mathrm{Valid}(\mathcal{C}_1)}$ and $\Phi \circ \Psi \cong \mathrm{Id}_{\mathrm{Valid}(\mathcal{C}_2)}$. For each $i \in \{1, 2\}$, consider the contravariant Yoneda-type evaluation 2-functor
   $$\Upsilon_i : \mathcal{C}_i^{\mathrm{op}} \longrightarrow \mathbf{2\text{-}Cat}\!\left(\mathrm{Valid}(\mathcal{C}_i),\, \mathbf{2\text{-}Set}\right), \qquad X \longmapsto \mathrm{Ev}_X^{(i)},$$
   where $\mathrm{Ev}_X^{(i)}(\mathcal{F}) \equiv \mathcal{F}(X)$. Because each quotient 2-category $\mathcal{C}_i \equiv CG_i/\mathcal{R}_i$ is finitely complete and finitely cocomplete and admits a separating family of models (guaranteed by Theorem 5.2), $\Upsilon_i$ is fully faithful, and its essential image consists precisely of the continuous 2-functors preserving finite limits and filtered colimits (Lawvere–Gabriel–Ulmer Reconstruction Theorem).

2. **Construction of $F : \mathcal{C}_1 \to \mathcal{C}_2$ and Canonical Normalization:**
   For any object $X \in \mathrm{Ob}(\mathcal{C}_1)$, the composite 2-functor $\mathrm{Ev}_X^{(1)} \circ \Psi : \mathrm{Valid}(\mathcal{C}_2) \to \mathbf{2\text{-}Set}$ preserves finite limits and filtered colimits. By the essential surjectivity of $\Upsilon_2$ onto such continuous functors, there exists an object $F(X) \in \mathrm{Ob}(\mathcal{C}_2)$, unique up to canonical isomorphism, such that
   $$\mathrm{Ev}_{F(X)}^{(2)} \cong \mathrm{Ev}_X^{(1)} \circ \Psi.$$
   By the full faithfulness of $\Upsilon_2$, every 1-morphism $f : X \to Y$ and 2-morphism $\mu$ in $\mathcal{C}_1$ induces a unique corresponding 1-morphism $F(f) : F(X) \to F(Y)$ and 2-morphism $F(\mu)$ in $\mathcal{C}_2$.
   Representational differences between $\mathcal{C}_1$ and $\mathcal{C}_2$ are automatically normalized by the quotient congruence $\mathcal{R}_i$ and universal properties. For instance, if $\mathcal{C}_1$ models a relationship via a primitive morphism $r : B \to A$ while $\mathcal{C}_2$ models it via a pullback along a referential property $\beta_{B \to A}$ and identifier $\alpha_I$, the commutative identity $\beta_{B \to A} = \alpha_I \circ r$ (Axioms C-1.5 and C-4) induces naturally isomorphic fibers under $\mathrm{Ev}^{(i)}$, so $F$ maps them to isomorphic morphisms in $\mathcal{C}_2$. Similarly, associative spans (Axiom C-2) and `Is-a` coproducts (Axiom C-3) are preserved up to unique isomorphism by their universal properties.

3. **Establishment of the Categorical Equivalence $\mathcal{C}_1 \simeq \mathcal{C}_2$:**
   Symmetrically, applying the same construction to $\Phi$ yields a 2-functor $G : \mathcal{C}_2 \to \mathcal{C}_1$ satisfying $\mathrm{Ev}_{G(Y)}^{(1)} \cong \mathrm{Ev}_Y^{(2)} \circ \Phi$. For every $X \in \mathrm{Ob}(\mathcal{C}_1)$, we obtain natural isomorphisms
   $$\mathrm{Ev}_{G(F(X))}^{(1)} \cong \mathrm{Ev}_{F(X)}^{(2)} \circ \Phi \cong \mathrm{Ev}_X^{(1)} \circ \Psi \circ \Phi \cong \mathrm{Ev}_X^{(1)}.$$
   Since $\Upsilon_1$ is fully faithful, this induces a natural isomorphism $\eta : \mathrm{Id}_{\mathcal{C}_1} \xrightarrow{\sim} G \circ F$, and symmetrically $\varepsilon : F \circ G \xrightarrow{\sim} \mathrm{Id}_{\mathcal{C}_2}$. Thus, $\mathcal{C}_1 \simeq \mathcal{C}_2$ and $\mathrm{Valid}(\mathcal{C}_1) \simeq \mathrm{Valid}(\mathcal{C}_2)$. $\blacksquare$

An intuitive, canonical illustration of Theorem 5.3 is the comparison between a schema whose class names, property names, and phrases are written entirely in Japanese and one written entirely in English: although their surface string tokens differ completely, if both adequately capture the same network of monic identifiers, multiplicities, and commutative constraints, they are categorically equivalent. Conversely, if two modelers rigorously refine models of what they believe to be the same domain yet arrive at *non-equivalent* schema categories, the contrapositive of Theorem 5.3 proves that they are implicitly modeling **two distinct Fields of Sense** governed by different schemas (which must then be connected via a Bridge as formalized in Paper 0 and Paper 3).

---

### 5.4 Cognitive Finitude and the Asymptotic Convergence Theorem
Because human beings possess finite memory and finite cognitive capacity, a modeler cannot write down the complete true schema $\mathcal{C}^*$ in a single step upon encountering an unfamiliar Field of Sense. Nevertheless, by formalizing iterative **abduction** and **structural refinement**, I prove that finite human cognition can asymptotically converge to $\mathcal{C}^*$.

**Definition 5.2 (Initial Approximate Models and Two Refinement Operators)**

Let $\mathcal{C}^{(n)}$ denote the $n$-th approximate schema category abductively constructed by a modeler from finite observations. Due to cognitive finitude, an initial approximation $\mathcal{C}^{(0)}$ typically harbors two forms of undifferentiated ambiguity:
* **Ambiguity I (Conditional Attributes / Partial Links):** 

    Properties populated only for a subset of instances in a class $S$, or relationships bearing `0..1` (or implementation-level `Nullable`) multiplicities.
* **Ambiguity II (Unreified Many-to-Many Relations):** 

    Undifferentiated `*`-to-`*` relationships between classes $O$ and $T$ whose intrinsic relational attributes or temporal multiplicities have not yet been isolated.

Whenever deductive predictions from $\mathcal{C}^{(n)}$ diverge from newly observed phenomena (intensions), the modeler applies two refinement operators to obtain $\mathcal{C}^{(n+1)}$:
1. **Subclassing Operator $\mathcal{R}_{\text{sub}}$ (Coproduct Decomposition):** Discovering the latent semantic distinction behind a `0..1` link or conditional property in $S$, and partitioning $S$ into an exclusive coproduct $S \cong \coprod_{i=1}^k C_i$ (Axiom C-3). This transforms ambiguous `0..1` links into mandatory, total `1` links on specific subtypes $C_i$.
2. **Associative-Class Operator $\mathcal{R}_{\text{assoc}}$ (Span Reification):** Reifying an undifferentiated many-to-many relationship into a first-class associative class $A$ at the vertex of a span $O \xleftarrow{p_O} A \xrightarrow{p_T} T$ (Axiom C-2), endowed with its own identifier and strict `1` projections.

**Theorem 5.4 (Asymptotic Convergence under Cognitive Finitude)**

Let $\mathcal{C}^*$ be the true schema category of a Field of Sense $\mathcal{SYS}$, and let
$$\mathcal{C}^{(0)} \longrightarrow \mathcal{C}^{(1)} \longrightarrow \cdots \longrightarrow \mathcal{C}^{(n)} \longrightarrow \cdots$$
be a sequence of approximate schemas generated via abductive refinement operators ($\mathcal{R}_{\text{sub}},\, \mathcal{R}_{\text{assoc}}$) such that each step strictly increases fiber separation. Then:
1. **Monotonic Contraction of Spurious State Space:** The space of invalid states spuriously admitted by $\mathcal{C}^{(n)}$ contracts monotonically toward the true state space $\mathrm{Valid}(\mathcal{C}^*)$.
2. **Unique Convergence in the Limit (via the Density Theorem):** Because every instance functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C}^*)$ is canonically expressed as a colimit of representable functors $h^X = \mathcal{C}^*(X, -)$ over its category of elements (the **Density Theorem**),
   $$\mathcal{F} \cong \operatorname{colim}_{(X, a) \in \int \mathcal{F}} h^X,$$
   the inductive limit of the refinement sequence converges up to categorical equivalence to the true schema: $\varinjlim \mathcal{C}^{(n)} \simeq \mathcal{C}^*$.
3. **Practical Sufficiency at Finite Stages:** At any finite stage $\mathcal{C}^{(N)}$ prior to the infinite limit, the differentiated sub-domain is isomorphic to a structure-preserving projection (partial polynomial approximation) of $\mathcal{C}^*$, functioning as a completely sound and practical model for its bounded scope.

#### Proof

**Proof Strategy (Overview):**
Let $\mathcal{C}^{(0)} \xrightarrow{J_0} \mathcal{C}^{(1)} \xrightarrow{J_1} \cdots \xrightarrow{J_{n-1}} \mathcal{C}^{(n)} \to \cdots$ be the sequence of approximate schema categories generated by iterative abduction and refinement operations ($\mathcal{R}_{\mathrm{sub}}, \mathcal{R}_{\mathrm{assoc}}$), with structural embeddings $I_n : \mathcal{C}^{(n)} \to \mathcal{C}^*$ into the true schema category $\mathcal{C}^*$. We prove: (1) the induced restriction functors monotonically shrink the space of spurious states, (2) the filtered colimit converges to $\mathcal{C}^*$ by the Density Theorem, and (3) any finite truncation stage $N$ remains valid and adequate on its refined sub-domain.

1. **Monotonic Inclusion of Model Spaces and Elimination of Spurious States:**
   - **Under Subclass Partitioning ($\mathcal{R}_{\mathrm{sub}}$):** Suppose at stage $\mathcal{C}^{(n)}$, a class $S$ carries an optional relationship $r : S \to B$ of multiplicity `0..1` or conditional attributes, allowing spurious states in $\mathrm{Valid}(\mathcal{C}^{(n)})$ where links are attached to inapplicable instances or omitted from mandatory ones. Applying $\mathcal{R}_{\mathrm{sub}}$ decomposes $S \cong C_1 \amalg C_2$ into disjoint subclasses (Axiom C-3) and tightens $r$ to a mandatory `1`-multiplicity morphism $r' : C_1 \to B$. Precomposition along $J_n : \mathcal{C}^{(n)} \to \mathcal{C}^{(n+1)}$ induces a forgetful restriction functor
     $$J_n^* : \mathrm{Valid}(\mathcal{C}^{(n+1)}) \longrightarrow \mathrm{Valid}(\mathcal{C}^{(n)}), \qquad \mathcal{F} \longmapsto \mathcal{F} \circ J_n,$$
     which is injective on isomorphism classes of objects and faithful, pruning all invalid models in which $C_2$-instances participate in $r$.
   - **Under Associative Reification ($\mathcal{R}_{\mathrm{assoc}}$):** Reifying an undifferentiated many-to-many relation $O \leftrightarrow T$ into an associative class $A$ with monic mediating span $\langle p_O, p_T \rangle : A \hookrightarrow O \times T$ (Axiom C-2) eliminates spurious states containing duplicate link pairs or inconsistent link attributes.
   Consequently, we obtain a monotonically shrinking chain of valid model spaces:
   $$\mathrm{Valid}(\mathcal{C}^*) \subseteq \cdots \subseteq \mathrm{Valid}(\mathcal{C}^{(n+1)}) \subseteq \mathrm{Valid}(\mathcal{C}^{(n)}) \subseteq \cdots \subseteq \mathrm{Valid}(\mathcal{C}^{(0)}).$$

2. **Convergence in the Inductive Limit via the Density Theorem:**
   Because the target field of sense $\mathcal{SYS}$ is spanned by a countable set of conceptual classes and relationships (Axiom of Separability), when each refinement step strictly increases fiber separation, every object $X$ and morphism $f$ of $\mathcal{C}^*$ enters the image of $\mathcal{C}^{(N)}$ for some finite $N$, and the congruence $\mathcal{R}^*$ of $\mathcal{C}^*$ is exhausted by the union $\bigcup_{n=0}^{\infty} \mathcal{R}^{(n)}$. Hence, the filtered colimit in $\mathbf{2\text{-}Cat}$ satisfies
   $$\mathcal{C}_{\infty} \equiv \varinjlim_{n \to \infty} \mathcal{C}^{(n)} \simeq \mathcal{C}^*.$$
   Moreover, by the categorical Density Theorem (Co-Yoneda Lemma), every valid state 2-functor $\mathcal{F} \in \mathrm{Valid}(\mathcal{C}^*)$ is canonically a colimit of representable functors $h^X = \mathcal{C}^*(X, -)$ indexed by its category of elements:
   $$\mathcal{F} \cong \operatorname{colim}_{(X, a) \in \int \mathcal{F}} h^X.$$
   Thus, the model category of the limit schema converges uniquely to $\mathrm{Valid}(\mathcal{C}_{\infty}) \simeq \mathrm{Valid}(\mathcal{C}^*)$.

3. **Practical Adequacy at Finite Stages:**
   If the refinement process halts at a finite stage $N$, let $\mathcal{C}_{\mathrm{sub}}^{(N)} \subseteq \mathcal{C}^{(N)}$ be the full sub-2-category of classes and relationships whose partitions and spans have already been stabilized. The restricted embedding $I_N|_{\mathcal{C}_{\mathrm{sub}}^{(N)}}$ is fully faithful and preserves finite limits and coproducts. Therefore, for any true state $\mathcal{F}^* \in \mathrm{Valid}(\mathcal{C}^*)$, its restriction $\mathcal{F}^*|_{\mathcal{C}_{\mathrm{sub}}^{(N)}}$ belongs to $\mathrm{Valid}(\mathcal{C}_{\mathrm{sub}}^{(N)})$, guaranteeing sound and practically sufficient modeling within the delineated scope. $\blacksquare$

In real-world modeling practice, the quintessential trajectory of Theorem 5.4 is the gradual elimination of `0..1` and `0..*` (`Nullable` or optional) multiplicities: beginning from a coarse model $\mathcal{C}^{(0)}$ riddled with conditional exceptions, the modeler repeatedly applies subclassing ($\mathcal{R}_{\text{sub}}$) to replace `0..1` with mandatory `1` and associative reification ($\mathcal{R}_{\text{assoc}}$) to structure `0..*` entanglements, steadily converging toward $\mathcal{C}^*$.

---

## 6. Practical Implications and Conclusion

### 6.1 Re-evaluating Visual Notations (UML and ER Diagrams): Syntax vs. Semantics
The category-theoretic formalization established in this paper clarifies the true status of modeling notations in software engineering and information system design. In everyday practice, graphical syntaxes such as UML class diagrams, ER diagrams, or textual formats (YAML/JSON) are frequently mistaken for the "model" itself. In our framework, however, **the model is the intrinsic semantic structure (the schema category $\mathcal{C}$), whereas UML and ER diagrams are merely visual syntaxes used to communicate that structure**.

* **Syntax Alone Guarantees Nothing:** Drawing boxes and lines does not by itself determine whether classes possess monic identifiers, whether `Is-a` denotes an exclusive coproduct ($S \cong \coprod C_i$) rather than implementation inheritance, or whether `0..1` ambiguities remain unresolved. Without rigorous semantics, visual diagrams risk degenerating into arbitrary sketches.
* **Vindication of Standard Notations under Rigorous Semantics:** Conversely, when a modeler writes with the category-theoretic semantics of Sections 2–5 explicitly in mind, standard notations such as UML and ER diagrams function seamlessly as faithful representations of $\mathcal{C}$. Moreover, by Theorem 5.3, any two representations—whether diagrammatic or textual, in Japanese or in English—that satisfy these rigor conditions converge to the exact same model up to categorical equivalence.

Furthermore, separating syntax from semantics naturally reveals why the traditional ideal of bidirectional "round-trip engineering" ($\text{Requirements Model} \to \text{Design Model} \to \text{Implementation Code} \to \text{Requirements Model}$) cannot hold in principle: problem-domain requirements and execution platforms inhabit distinct Fields of Sense governed by different schema categories, and transformations mediated by non-functional boundary conditions are inherently unidirectional and irreversible (a structural asymmetry formalized in Paper 3). Practical modeling mastery therefore lies not in automated reverse-engineering from code, but in disciplined abductive refinement toward $\mathcal{C}^*$.

### 6.2 Conclusion and Outlook for Paper 2
Building upon the relation-based ontology and Universe of Fields of Sense introduced in Paper 0, this paper (Paper 1) has formalized the static semantic structure of a single Field of Sense (the Conceptual Information Model) as a quotient 2-category $\mathcal{C} \equiv CG/\mathcal{R}$. We demonstrated that seemingly strict modeling rules—closed data types, monic identifiers, bidirectional relationships with four multiplicities and semantic phrases, commutative referential properties, exclusive coproduct `Is-a` partitions, associative span classes, and diagonal non-degeneracy—constitute the exact necessary and sufficient conditions to affirm all three foundational questions:

1. **Affirmation of Existence (Theorems 5.1 and 5.2):** The static structure of any Field of Sense is expressively representable within this minimal formalism (Theorem 5.1), and every well-formed schema category $\mathcal{C}$ constructively admits non-trivial, contradiction-free instance models ($\mathrm{Valid}(\mathcal{C}) \neq \emptyset$, Theorem 5.2).
2. **Affirmation of Uniqueness / Isomorphism (Theorem 5.3):** Any two schema categories adequately describing the same Field of Sense are categorically equivalent ($\mathcal{C}_1 \simeq \mathcal{C}_2$) across variations in notation, representation, or natural language.
3. **Affirmation of Asymptotic Refinement (Theorem 5.4):** Even with finite cognitive capacity, human modelers can iteratively refine initial approximations via abduction, subclassing, and associative-class reification, converging asymptotically to the true schema $\mathcal{C}^*$ by virtue of the Yoneda Lemma and the Density Theorem.

With the static spatial skeleton of a single Field of Sense firmly established, **Paper 2** will extend this framework to **temporal evolution and dynamic state transitions**. By integrating instance state models, data-flow action models, and execution semantics (boundary conditions and invariants), Paper 2 will prove that the dynamic behavior of a Field of Sense closes as a **Symmetric Monoidal Category**, capable of faithfully representing continuous real-world dynamics through discrete state transitions.

---

## References

1. **Ota, H. (2026).** *Relation-Based Ontology and a Category-Theoretic Formalization of Fields of Sense: Structural Collapse via Linguistic Polysemy and Phenomena as the Intension of a Universe* (Version 1.0.1). Zenodo. DOI: [10.5281/zenodo.24267213](https://doi.org)
2. **Mac Lane, S. (1998).** *Categories for the Working Mathematician* (2nd ed.). Springer.
3. **Lawvere, F. W. (1963).** *Functorial Semantics of Algebraic Theories*. Proceedings of the National Academy of Sciences of the United States of America, 50(5), 869–872.
4. **Gabriel, P., & Ulmer, F. (1971).** *Lokal präsentierbare Kategorien*. Lecture Notes in Mathematics, Vol. 221, Springer.
5. **Spivak, D. I. (2012).** *Functorial Data Migration*. Information and Computation, 217, 31–51.
6. **Barr, M., & Wells, C. (1990).** *Category Theory for Computing Science*. Prentice Hall.
7. **Mac Lane, S., & Moerdijk, I. (1992).** *Sheaves in Geometry and Logic: A First Introduction to Topos Theory*. Springer.
8. **Peirce, C. S. (1903/1998).** *Pragmatism as the Logic of Abduction*. In *The Essential Peirce: Selected Philosophical Writings*, Vol. 2 (1893–1913), Indiana University Press.
9. **Gabriel, M. (2015).** *Fields of Sense: A New Realist Ontology*. Edinburgh University Press.
10. **Wittgenstein, L. (1921/1922).** *Tractatus Logico-Philosophicus*. Kegan Paul, Trench, Trubner & Co.
11. **Shlaer, S., & Mellor, S. J. (1988).** *Object-Oriented Systems Analysis: Modeling the World in Data*. Yourdon Press.
12. **Shlaer, S., & Mellor, S. J. (1992).** *Object Lifecycles: Modeling the World in States*. Yourdon Press.
13. **Mellor, S. J., & Balcer, M. J. (2002).** *Executable UML: A Foundation for Model-Driven Architecture*. Addison-Wesley.
14. **Chen, P. P. (1976).** *The Entity-Relationship Model—Toward a Unified View of Data*. ACM Transactions on Database Systems, 1(1), 9–36.
15. **Codd, E. F. (1970).** *A Relational Model of Data for Large Shared Data Banks*. Communications of the ACM, 13(6), 377–387.
16. **Object Management Group (OMG). (2019).** *OMG Meta Object Facility (MOF) Core Specification* (Version 2.5.1). OMG Document Number: formal/2019-10-01.
