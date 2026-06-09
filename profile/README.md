# Integrated Knowledge (IKE)

**Integrated Knowledge, and the ability to Exchange this knowledge** is built on a foundation of versioned knowledge graphs with pluggable formalisms. We embrace OWL/RDF semantics and property graph models as foundational—and extend them with STAMP versioning and cross-formalism integration they weren't designed to provide. Every vertex carries STAMP coordinates (Status, Time, Author, Module, Path), enabling precise tracking of when content was valid, who authored it, and how versions relate. And because change-sets are first-class constructs, you get collaborative development out of the box—supporting both iterative work-in-progress and publication of finalized artifacts for any formalism.

Within this substrate, any knowledge structure can be represented as traversable, versionable content. EL++ terminology definitions, BPMN process models, clinical decision logic—each retains its semantics while becoming composable and version-aware. A workflow can reference a SNOMED concept that contains its own axiom structure, and when either evolves, dependencies are explicit and trackable.

This matters because knowledge systems fail silently. Clinical decision support malfunctions—where alerts stop firing because an identifier changed upstream, or rules break from untracked edits—[affect virtually every healthcare organization](https://pubmed.ncbi.nlm.nih.gov/27026616/). These aren't edge cases; they're version coordination failures that current tools can't prevent or detect. STAMP versioning&mdash;within an integrated ecosystem&mdash;makes the invisible visible.

As AI systems increasingly depend on structured knowledge—for training data, retrieval-augmented generation, and decision grounding—curation quality becomes critical infrastructure. Flawed knowledge at scale fails *confidently*—and the burden of catching it falls to you. IKE enables principled knowledge curation at scale: expert judgment captured in version-controlled, machine-processable form, so human expertise and modern computation reinforce each other rather than working at cross-purposes.

IKE grew out of the [Tinkar](https://www.hl7.org/implement/standards/product_brief.cfm?product_id=573) (Terminology Knowledge Architecture) and [ANF](https://www.hl7.org/implement/standards/product_brief.cfm?product_id=523) (Analysis Normal Form) efforts published through HL7—and provides a community for their continued evolution and open-source implementation. Whether you're coming from knowledge graph development, clinical terminology management, or ontology engineering, if you're working on systems where knowledge changes and correctness matters, you're in the right place.

## Try IKE in 10 minutes

The quickest path to seeing the build pipeline and documentation
toolchain in action:

- **[example-project](https://github.com/IKE-Network/example-project)** — Java 25 reference project. Clone, run `./mvnw verify -Ppdf`, and you have a built jar plus a rendered PDF.
- **[doc-example](https://github.com/IKE-Network/doc-example)** — docs-only template using the `ike-doc` packaging. Same flow, no Java module.

Prerequisites: JDK 25 and the included Maven 4 wrapper.

## Repositories

IKE publishes two lines of work: the **build platform** that
downstream projects consume, and the **documentation pipeline**.
One tracker coordinates both.

### Templates — start new projects here

| Repo | What it is |
|---|---|
| [example-project](https://github.com/IKE-Network/example-project) | Java + docs reference template. Inherits `ike-parent`, produces jar + HTML + PDF. |
| [doc-example](https://github.com/IKE-Network/doc-example) | Doc-only template with `ike-doc` packaging. Multi-renderer PDF (Prawn / FOP) + HTML. |

### Platform — what your POMs depend on

| Repo | What it provides |
|---|---|
| [ike-platform](https://github.com/IKE-Network/ike-platform) | `ike-parent`, `ike-bom`, `ike-workspace-maven-plugin` (`ws:*` goals for multi-repo orchestration). |
| [ike-docs](https://github.com/IKE-Network/ike-docs) | `ike-doc-maven-plugin` (`idoc:*` goals + `ike-doc` packaging), Koncept AsciiDoc extension, DocBook XSL, shared doc resources, semantic-linebreak reformatter. |
| [ike-tooling](https://github.com/IKE-Network/ike-tooling) | Workspace model, Claude build standards, foundational `ike-maven-plugin` support libraries. |

### Governance

| Repo | What it is |
|---|---|
| [ike-issues](https://github.com/IKE-Network/ike-issues) | **Unified issue tracker** for everything above. File bugs and enhancements here with the component dropdown. |

### Release cascade

Releases flow left to right — each layer consumes the one before it:

```
ike-tooling  →  ike-docs  →  ike-platform  →  { doc-example, example-project }
```

Workspace aggregators that coordinate multi-repo builds and the
Komet desktop application are being reorganized; they'll return
to this index once the new structure lands.

## Get Involved

Join the conversation on [IKE&#8217;s Zulip](https://ike.zulipchat.com)—an open-source, threaded chat platform where discussions stay organized and searchable over time. Whether you're asking questions, proposing ideas, or collaborating on implementations, Zulip is where the community connects.

File bugs and enhancement requests in [ike-issues](https://github.com/IKE-Network/ike-issues) — one tracker across all components, with a dropdown to tag the affected layer.

## Powered by IKE

Building on or integrating with IKE? Show it with the **Powered by IKE** badge.

<a href="https://ike.network">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://ike.network/brand/powered-by/powered-by-ike-color-on-dark.svg">
    <img alt="Powered by IKE" height="28" src="https://ike.network/brand/powered-by/powered-by-ike-color-on-light.svg">
  </picture>
</a>

Grab the files, snippets, and usage rules at **[ike.network/brand](https://ike.network/brand.html)**. Quick Markdown:

```markdown
[![Powered by IKE](https://ike.network/brand/powered-by/powered-by-ike-color-on-light.svg)](https://ike.network)
```

---

**Topics:** knowledge graphs · description logic · terminology management · clinical informatics · SNOMED CT · LOINC · RxNorm · EL++ · clinical decision support · version control · STAMP · ontology · healthcare AI · OWL
