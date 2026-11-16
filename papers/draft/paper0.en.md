# Relation-Based Ontology and a Category-Theoretic Formalization of Fields of Sense:

Structural Collapse via Linguistic Polysemy and Phenomena as the Intension of a Universe

## Abstract

Traditional philosophy of language and general modeling methodologies have predominantly adopted an object-based perspective, treating objects ("things") as foundational and relations as secondary attributes attached between them. However, within this object-based framework, it is fundamentally impossible to explain how the inherent "polysemy" of everyday language causes semantic networks to become intricately entangled, leading to the trivialization and collapse of structure. In this paper, starting from a category of existents (objects) and semantic links, I demonstrate that its dual perspective—a span structure in which relations (links) themselves serve as the primary subjects of reality—constitutes the essence of meaningful existence. Furthermore, I formalize the mechanism by which the polysemy of a word-labeling functor causes distinct semantic links to degenerate into morphisms isomorphic to identity morphisms, resulting in the collapse of meaning. To avoid this collapse, human cognition partitions the world using predefined conceptual yardsticks (schema categories), constructing a "Universe" composed of instance categories (fields of sense) governed by schemas and "bridges" that specify correspondences between these fields. Finally, I demonstrate that what we ordinarily call "phenomena" or "observation" manifests as the "intension" of this Universe, and prove that it is in principle impossible to uniquely invert or reconstruct the global structure of the original Universe solely from observed intensions.

## 1. Introduction

Whenever we perceive the world, think, and describe it through language or theory, a structural gap persistently exists between "the world as it really is" and "observed phenomena." Just as Kant argued in the Critique of Pure Reason that human cognition can access only "phenomena" appearing through our cognitive frameworks rather than "things-in-themselves" (Ding an sich), there is a fundamental asymmetry between the global structure of reality and the phenomena we grasp. Meanwhile, traditional analytic philosophy and ontology—represented by Frege's context principle and early Wittgenstein's picture theory—have relied on an object-based paradigm, assuming that the world is a totality of objects and that meaning arises from the configuration and relations among them.

However, this paradigm faces a profound difficulty. Because the words (labels) we use to describe phenomena are inherently polysemous, connecting objects with words on a single, uniform network causes links from different contexts to become hopelessly entangled. Eventually, relations that ought to be distinct become indistinguishable (trivial), resulting in the collapse of meaning. This is the structural and mathematical consequence of what Markus Gabriel pointed out in his New Realism: that there is no single, all-encompassing "World," and that reality appears instead across infinitely many distinct "Fields of Sense".

The objective of this paper is to formalize, via category theory, the common foundation of "general modeling methodologies" through which humans articulate and grasp the world—ranging from everyday linguistic understanding to theoretical descriptions of phenomena in physics and the natural sciences. As a self-contained study, this paper demonstrates the following three propositions:

1. Distinction and the Dual Shift to a Relation-Based Foundation: In cognition, "distinction" corresponds to establishing an intrinsic identity morphism (self-identity) for an entity, and pointable existents are classified into "objects," "feature values," and "semantic links". Among these, the essence of meaningful reality lies in the "semantic link" (relation) itself; to preserve difference without collapsing into self-identity, a dual span structure is required in which the link serves as the object projecting onto left and right roles.
2. Construction of a Universe via Epoché and Schema Partitioning: To prevent the collapse of meaning caused by linguistic polysemy, humans temporarily suspend (Epoché) the single yardstick unconsciously applied to reality and partition the world using multiple schema categories (conceptual yardsticks). This formalizes a totality—termed the "Universe"—consisting of respective instance categories (fields of sense) and the bridges connecting them.
3. The "Intensional" Nature of Phenomena and Non-Invertibility: Phenomena, or what we call observation, are bundles of cognition carved out as the "intension" of this Universe. Consequently, it is in principle impossible to uniquely invert or reconstruct the global structure of the original Universe solely from observed phenomenological data.

## 2. Category-Theoretic Formalization of "Distinction" and Existence


### 2.1 "Distinction," Identity Morphisms, and the Three Pointable Entities

To "distinguish" (individuate) something within phenomena is to draw a boundary separating it from others and to recognize its intrinsic self-identity (aligning with Quine's maxim, "No entity without identity"). Within the framework of category theory, such a "distinguished, pointable existent" is rigorously formalized as an object possessing an identity morphism $\mathrm{id}$ pointing to itself (just as the "arrows-only definition" of a category identifies objects with their identity morphisms, the establishment of an intrinsic identity morphism serves as the ground of existence).

Pointable existents within phenomena (objects equipped with identity morphisms) are strictly classified into three types according to their structural roles:

- Definition 2.1 (Threefold Classification of Pointable Existents):
    1. Objects (Entities $A, B, \dots$): Targets that appear as independent individuals within phenomena, serving as nodes for features and relations, each possessing an intrinsic identity morphism $\mathrm{id}_{A}$.
    2. Feature Values (Attribute Values $V_1, V_2, \dots$): Properties or states attached to an object (e.g., "red," "high temperature"). While a feature value V is also a pointable existent with an identity morphism $\mathrm{id}_{V}$, its structure is limited to being connected to an object A via a unidirectional, subordinate morphism α: A → V; it lacks the capacity to draw other objects to its left and right to extend relational networks.
    3. Semantic Links (Relations R): The meaningful connections themselves established between objects.

Initially, from our naive perspective, we may consider a category $\mathcal{C}_{\text{inst}}$ whose objects are individual entities A, B and whose morphisms are semantic links spanning between them. Unlike feature values that terminate in unidirectional arrows, semantic links always manifest as bidirectional pairs consisting of a forward morphism $f: A \to B$ and a backward morphism $g: B \to A$. This is because whenever an object A bears meaning with respect to B, a reverse context referencing A from B must be adjointly stipulated for the relational contour to close.

### 2.2 The Dual Shift of Perspective: Link-Centered Span Structures

However, the perspective of $\mathcal{C}_{\text{inst}}$—which treats objects as protagonists and links merely as arrows (subordinates) between them—overlooks the essential condition under which meaning arises. Crucially distinct from feature values that close via unidirectional arrows, the true core of reality weaving semantic networks is the "semantic link (relation) R itself".

When I reconceptualize a link R as a first-class existent (an object), a dual structure emerges in which the roles of objects and morphisms in $\mathcal{C}_{\text{inst}}$ are inverted.

- Definition 2.2 (Link-Centered Representation and Span Structure): When a semantic link R itself is treated as an object, being an existent, it possesses an identity morphism $\mathrm{id}_R: R \to R$ pointing to itself. Simultaneously, projections $p_1: R \to A$ and $p_2: R \to B$  extend from R to the objects A and B situated at both ends of the relation. Mathematically, this is a span $A \xleftarrow{p_1} R \xrightarrow{p_2} B$ with R at its apex, carrying objects to its left and right. Simultaneously, from the perspective of logical propositions, these two projections assume left and right roles (phrases), forming the structural foundation for a single propositional statement (predicate structure) asserting that "A and B stand in relation R".

What is observed in $\mathcal{C}_{\text{inst}}$ as "a bidirectional link between objects A and B" is merely a projection of this essential span structure viewed from the perspective of its endpoint objects.

- Proposition 2.3 (Non-Triviality Condition for Meaning): A semantic link R is meaningful if and only if R does not degenerate into a trivial point isomorphic to its own identity morphism $\mathrm{id}_{R}$, but instead preserves distinct roles (difference) through its left and right projections p₁ and p₂.

If a link loses its pair of non-trivial left and right projections and becomes indistinguishable from a single closed point, R reduces merely to $\mathrm{id}_{R}$, thereby losing its meaning as a relation.

## 3. Collapse of Meaning via Linguistic Polysemy

In ordinary linguistic activity and thought, we do not assign a unique symbol to every individual existent on each occasion; rather, we designate objects and relations using pre-existing "words (labels)". This process can be described as a projection (a labeling functor) from a category of existents to a category of linguistic labels $\mathcal{W}$.

- Definition 3.1 (Labeling Functor and Polysemy): Consider a functor $L: \mathcal{E} \to \mathcal{W}$ from a category $\mathcal{E}$ forming a network of existents to a category $\mathcal{W}$ whose objects are word labels. A word $w \in \mathcal{W}$ is said to possess polysemy when its inverse image (fiber) $L^{-1}(w)$ under L contains multiple distinct existents belonging to different contexts and different span structures.

For instance, the single label "bridge" is applied both to a physical structure (a relation connecting a river and its banks) and to a metaphorical mediation (a relation connecting people). Attempting to describe the world on a single network through such a polysemous labeling functor L results in a complex, cobweb-like entanglement.

- Theorem 3.2 (Degeneration into Identity Morphisms and Collapse of Meaning via Polysemy): When existents from different contexts are folded (quotiented) into the same label w by a polysemous labeling functor L, the endpoints of a semantic link R that originally connected distinct targets become identified, forming a self-loop. Furthermore, as contextual differences are lost, the morphism degenerates into a morphism isomorphic to the identity morphism $\mathrm{id}_{w}$ of label w, violating the non-triviality condition of Proposition 2.3 and causing the collapse of meaning.

Thus, in a single network model that uncritically permits linguistic polysemy, all semantic links eventually collapse into trivial identity morphisms, rendering an accurate description of phenomena impossible.

## 4. Construction of the Universe via Fields of Sense and Bridges, and Phenomenological Epoché


### 4.1 Schema Categories, Fields of Sense, and Phenomenological Epoché as Forms of Existence

As demonstrated in Chapter 3, attempting to confine relations (semantic links) belonging to different contexts within a single, homogeneous space causes links to interfere and degenerate until they become indistinguishable from identity morphisms, collapsing the structure itself. Therefore, for the world to exist while preserving non-trivial differences, reality itself must inherently possess a structure partitioned by context, regardless of the presence or absence of an observer.

What governs this partitioned form of existence are "schema categories," which serve as structural types, and "instance categories (fields of sense)," in which concrete existents are arranged according to those schemas. Applying this to human cognition, the reason our everyday thought avoids the collapse of meaning is that we do not attach words haphazardly to phenomena; rather, we articulate the world by applying "predefined conceptual yardsticks (schemas)".

- Definition 4.1 (Schema Categories and Fields of Sense): A category defined by concept classes (types of objects), attribute types (types of feature values), and relation types (types of relations) within a specific context or system of laws is defined as a schema category $\mathcal{S}_{i}$. The local state of reality in which concrete objects, feature values, and semantic links are arranged according to the structure of schema $\mathcal{S}_{i}$ is formalized as a functor $I_i: \mathcal{S}_i \to \mathbf{Set}$ (or equivalently, its category-theoretic representation as an instance category $\mathcal{I}_{i}$).

Crucially, a schema $\mathcal{S}_{i}$ and an instance $\mathcal{I}_{i}$ stand in a dual relationship (the duality of functorial semantics) between "syntax" (type specification centering on relations) and "semantics" (concrete fields centering on objects). Each local instance category $\mathcal{I}_{i}$ carved out per schema $\mathcal{S}_{i}$ is the category-theoretic formalization of what Markus Gabriel terms a "Field of Sense".

However, in everyday naive cognition (what Husserlian phenomenology calls the "natural attitude"), humans unconsciously apply a specific conventional yardstick (a single schema) to phenomena, acting as though it were the sole reality. Consequently, different fields of sense overlap, causing fiber collisions and the collapse of meaning. Here, an operation corresponding to Epoché (suspension of judgment) in phenomenology functions on the side of the observer. Epoché signifies temporarily suspending (bracketing) the application of the unconsciously imposed single yardstick and withholding the attitude of accepting targets as bundles of single labels. Through this suspension, we are liberated from forcing phenomena into a single framework and become able to attune our perspective to the multiple partitioned structures inherently possessed by reality (the configuration of distinct schema categories $\{\mathcal{S}_i\}$ and fields of sense $\{\mathcal{I}_i\}$). Within each field of sense $\mathcal{I}_{i}$, contextual interference is eliminated, and every semantic link preserves a sound non-triviality distinct from identity morphisms.

Traditional phenomenology positioned Epoché as a reduction to a single ultimate foundation—namely, "transcendental subjectivity (pure consciousness)"—which was the inevitable consequence of attempting to integrate diverse phenomena into a single center. Yet, because integrating distinct contexts into a single space induces structural breakdown, such approaches are perpetually forced to posit metaphysical apparatuses beyond experience. In contrast, this paper redefines Epoché not as a reduction to a single foundation, but as an operation that temporarily halts an unconsciously fixed single yardstick and liberates our perspective toward the structure of multiple, coexisting fields of sense $\{\mathcal{I}_i\}$ and schema categories $\{\mathcal{S}_i\}$ inherent in reality.

### 4.2 Bridges Connecting Fields of Sense and the Universe

Viewed in this light, polysemy arising in language and modeling is not merely a notational defect or noise on the human side. Rather, it is an unavoidable consequence stemming from the very form of existence: that reality itself is partitioned into multiple fields of sense, while entities belonging to different fields coexist with correspondences between them. Accordingly, an objective structure is required to re-relate these partitioned fields of sense.

- Definition 4.2 (Bridges and the Universe): A correspondence between instances in two fields of sense $\mathcal{I}_{i}$ and $\mathcal{I}_{j}$, grounded in distinct schemas $\mathcal{S}_{i}$ and $\mathcal{S}_{j}$, is defined as a span $\mathcal{I}_i \leftarrow \mathcal{B}_{ij} \rightarrow \mathcal{I}_j$ with a mediating structure $\mathcal{B}_{ij}$ at its apex, and is termed a Bridge.

Of paramount importance here is that the targets correlated by a bridge $\mathcal{B}_{ij}$ are strictly restricted to "objects" and "feature values" within each field of sense; a bridge never directly correlates "semantic links" themselves. Because a semantic link R is a relation strongly dependent on the specific context (span structure) of each schema $\mathcal{S}_{i}$, directly identifying links across different fields would once again induce structural collapse. Thus, distinct fields of sense are connected solely via correspondences between endpoint objects and feature values (bridges), while the relational structures of semantic links remain closed within their respective fields of sense.

I then define the Universe $\mathcal{U}$ as the global structure integrating all schema categories $\{\mathcal{S}_i\}$, their corresponding fields of sense (instance categories) $\{\mathcal{I}_i\}$, and the bridges $\{\mathcal{B}_{ij}\}$ connecting only objects and feature values. This Universe $\mathcal{U}$ is the objective "form of existence" that holds prior to the presence of any observer.

## 5. Conclusion: Phenomena as the Intension of the Universe and Non-Invertibility

From the foregoing formalization, the relationship between reality and cognition is concluded as follows:

- Proposition 5.1 (Form of Reality and Phenomena as "Intension"): Reality in this world consists of inhabitants of the Universe $\mathcal{U}$, formed by a collection of schema-governed fields of sense and the bridges between them. Furthermore, what we ordinarily call "phenomena" or "observation" is nothing other than the Intension of this Universe $\mathcal{U}$—a bundle of cognition folded within $\mathcal{U}$ and carved out through the filter of specific schemas and contexts.

Finally, we prove the most critical consequence derived from this structure: non-invertibility.

- Theorem 5.2 (Non-Invertibility from Observation): Solely from the data of observed phenomena (the intension of the Universe), it is impossible to uniquely invert or reconstruct the global structure of the original Universe $\mathcal{U}$ (i.e., which combination of schema categories $\mathcal{S}_{i}$ and bridges $\mathcal{B}_{ij}$ generated those phenomena).

## Proof

To prove this theorem, I formalize the observational process by which "phenomena (intensions)" are generated from the real Universe $\mathcal{U}$ as a category-theoretic projection (functor), and demonstrate in three stages that no inverse mapping can exist (failure of injectivity).

### Stage 1: Formalization of the Observational Process as a Projection (Forgetful Functor)

The real Universe $\mathcal{U}$ is a higher-order structure integrating multiple contextually distinct schema categories $\{\mathcal{S}_i\}$, their corresponding fields of sense $\{\mathcal{I}_i\}$, and the bridges $\{\mathcal{B}_{ij}\}$ linking them. In contrast, the human act of "observing" the world through everyday thought or scientific procedures and grasping it via models or language corresponds to applying a "filter"—such as a specific subjective schema or a category of lexical labels $\mathcal{W}$—to $\mathcal{U}$ to extract only observable aspects.

Within category theory, this observational process is formalized as a projection functor (forgetful functor) $\Pi: \mathcal{U} \to \mathcal{O}$ (where $\mathcal{O}$ denotes the category of observed phenomena) that strips away certain information (such as contextual differences and higher-order relational structures) from the rich structure of $\mathcal{U}$ and maps it onto a lower-order representation. As stated in Proposition 5.1, the "phenomena" we experience are precisely the intension of the Universe carved out by this projection functor $\Pi$.

### Stage 2: Two Structural Information Losses in the Projection Process

If the observational projection functor $\Pi$ completely preserved the structure of its preimage (the Universe $\mathcal{U}$)—that is, if it were fully faithful—it would be possible to uniquely reconstruct $\mathcal{U}$ from the observed result $\Pi(\mathcal{U})$. However, due to the structural constraints established in Chapters 3 and 4, applying $\Pi$ inevitably incurs two irreversible losses (degenerations) of information:

1. Degeneration of Fibers via Linguistic Labeling Polysemy:

    When mapping observational results onto a category of symbols or word labels $\mathcal{W}$, the non-injectivity (polysemy) of the labeling functor L causes distinct existents and semantic links belonging to different fields of sense $\mathcal{I}_{i}$ and $\mathcal{I}_{j}$ to be superimposed onto the inverse image (fiber) $L^{-1}(w)$ of the same label w. Through this folding (quotienting), the intrinsic differences possessed by distinct span structures cancel out, degenerating into a single, indistinguishable manifestation on the observational plane.
2. Non-Preservation of "Semantic Links" Across Bridges:

    As defined in Section 4.2, a bridge $\mathcal{B}_{ij}$ connecting distinct fields of sense $\mathcal{I}_{i}$ and $\mathcal{I}_{j}$ mediates only the correspondence between endpoint "objects" and "feature values," never directly correlating the "semantic links R" that depend on the specific context of each schema. Consequently, when observing the Universe through the window of a particular field of sense $\mathcal{I}_{i}$, even if the existence of objects in another field $\mathcal{I}_{j}$ across a bridge can be indirectly detected, information regarding what semantic links (relational structures) weave those objects together within $\mathcal{I}_{j}$ is completely dropped (forgotten) by the projection $\Pi$.

### Stage 3: Failure of Injectivity and Non-Existence of an Inverse Mapping

Because of these two structural information losses, the projection functor $\Pi: \mathcal{U} \to \mathcal{O}$ is not injective (not faithful). Specifically, given two distinct Universe substructures $\mathcal{U}_1 \neq \mathcal{U}_2$ possessing different schema partitions and different semantic link structures, whenever their relational differences degenerate via labeling polysemy and cross-bridge link structures are forgotten during projection (intensionalization), they necessarily yield completely identical manifestations as observed phenomena (intensions):

$$\mathcal{U}_{1}\ne \mathcal{U}_{2}\quad \text{while}\quad \Pi (\mathcal{U}_{1})\cong \Pi (\mathcal{U}_{2})$$

Mathematically and logically, a mapping that returns the same image for distinct preimages (a non-injective functor) admits no inverse mapping $\Pi^{-1}$ that uniquely determines the preimage from the image. Therefore, starting solely from the data of observed phenomena (the intension of the Universe), it is in principle impossible to uniquely invert or reconstruct the global structure of the real Universe $\mathcal{U}$ that generated them. $\blacksquare $

## Summary

Starting from a Kantian epistemological framework, this paper has category-theoretically formalized the underlying structure of "general modeling methodologies" spanning everyday thought to theoretical descriptions in the natural sciences. By defining "distinction" in cognition as the establishment of identity morphisms and strictly differentiating "feature values" (unidirectional morphisms) from "semantic links" (span structures carrying objects to their left and right), I adopted a dual perspective treating relations as the essence of reality, thereby elucidating the mechanism by which linguistic polysemy causes the collapse of meaning. Furthermore, I demonstrated that humans temporarily suspend unconscious yardsticks via phenomenological Epoché, partition the world into "Fields of Sense" using multiple schemas, and construct a Universe integrated by bridges connecting only objects and feature values.  In short, this architecture of the Universe---in which multiple fields of sense centered on relational span structures are loosely connected via bridges---constitutes the universal form of existence that holds regardless of the presence or absence of an observer. The phenomena we experience are the "intension" of this real Universe, making it in principle impossible to invert the global structure of reality from observation. These findings provide a mathematical foundation for Gabriel's thesis of "the non-existence of a single all-encompassing world," while demonstrating the limits of assuming a "single complete world description" in any modeling methodology and highlighting the necessity of grasping the world as a network of multiple schemas and bridges grounded in verified premises.

## References

- Bénabou, J. (1967). Introduction to Bicategories. In Lecture Notes in Mathematics (Vol. 47, pp. 1–77). Springer.
- Fong, B., & Spivak, D. I. (2019). An Invitation to Applied Category Theory: Seven Sketches in Compositionality. Cambridge University Press.
- Frege, G. (1892). Über Sinn und Bedeutung. Zeitschrift für Philosophie und philosophische Kritik, 100, 25–50.
- Gabriel, M. (2013). Warum es die Welt nicht gibt. Ullstein.
- Gabriel, M. (2015). Fields of Sense: A New Realist Ontology. Edinburgh University Press.
- Husserl, E. (1913). Ideen zu einer reinen Phänomenologie und phänomenologischen Philosophie. Erstes Buch: Allgemeine Einführung in die reine Phänomenologie. Max Niemeyer.
- Kant, I. (1781/1787). Kritik der reinen Vernunft. Johann Friedrich Hartknoch.
- Lawvere, F. W. (1963). Functorial Semantics of Algebraic Theories. Proceedings of the National Academy of Sciences, 50(5), 869–872.
- Mac Lane, S. (1998). Categories for the Working Mathematician (2nd ed.). Springer.
- Quine, W. V. O. (1969). Ontological Relativity and Other Essays. Columbia University Press.
- Spivak, D. I. (2012). Functorial Data Migration. Information and Computation, 217, 31–51.
- Wittgenstein, L. (1921). Logisch-Philosophische Abhandlung (Tractatus Logico-Philosophicus). Annalen der Naturphilosophie.
