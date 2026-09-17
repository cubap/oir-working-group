# Oir Working Group Charter (v0.1 – provisional)

*This charter is a draft intended to demonstrate a viable governance and labor structure for the Oir Knowledge Graph project. Sections marked `UNVERIFIED` indicate factual claims that require external validation (e.g., survey results, repository commitments).*

---

## 1. Users (priority ranking)
1. **Scholars of medieval Irish studies** – primary researchers who need reliable, ambiguity‑aware data for interpretive work. *(UNVERIFIED – needs community endorsement)*
2. **Cultural heritage institutions** (DRI, VRTI, Logainm, museums) – providers of source data and partners for long‑term sustainability. *(UNVERIFIED – pending outreach)*
3. **Digital humanities developers & data scientists** – contributors of tools, AI models, and standards implementations. *(UNVERIFIED – identified via informal network)*
4. **Educators & students** – secondary users for teaching and training. *(UNVERIFIED – outreach plan pending)*
5. **General public** – optional public‑facing API and visualisations. *(UNVERIFIED – resource constraints)*

---

## 2. Data Scope (inclusion rule)
- **In‑scope**: Any medieval Irish entity (person, place, text, artifact) that appears in digitised, *legally reusable* repositories (e.g., DRI, VRTI, Logainm, CELT, ISOS, excavation reports) and can be linked to at least one primary source record.
- **Out‑of‑scope**: Materials lacking open licensing, undocumented provenance, or whose preservation status is unknown. Decisions on borderline cases will be made by the **Scope Committee** (see Section 6).
- **Evidence requirement**: Every added entity must reference at least one digital anchor (IIIF manifest, DOI, or archival identifier) stored as a RERUM *digital document*.

---

## 3. Encoding Standards (ambiguity‑preserving)
- **Core ontology**: JSON‑LD using CIDOC‑CRM extensions for provenance, plus RDF★STAR qualifiers for competing assertions.
- **Ambiguity model**: Multiple statements about the same subject are stored in separate named graphs, each with its own `prov:wasGeneratedBy` and a confidence score (0–1). No single statement is treated as canonical.
- **Standoff annotation**: All annotations live in RERUM, referencing the original source without modification.
- **Technical stack**: RERUM (v2.3+), JSON‑LD context `http://oor.org/context/oir.jsonld`, SPARQL 1.1 endpoint.
- **UNVERIFIED**: Exact JSON‑LD context details and CIDOC‑CRM mapping awaiting confirmation from the RERUM documentation.

---

## 4. Attribution Model
- **Contributor credit**: Each assertion records `prov:wasAttributedTo` (person or automated agent) and the institution owning the source.
- **AI‑generated suggestions**: Tagged with `prov:wasGeneratedBy` = `oir:LLM‑Engine` and a confidence qualifier; human reviewers must approve before promotion to the main knowledge graph.
- **Institutional requirements**: Follow partner repository citation policies (e.g., Logainm’s required attribution format). *(UNVERIFIED – pending partner policy review)*

---

## 5. Assertion & Confidence Model
- **State machine**: `proposed → reviewed → accepted → deprecated`.
- **Confidence**: Numeric score attached to each assertion; thresholds for automatic acceptance (`≥0.85`) and manual review (`0.5‑0.85`).
- **Provenance audit**: All changes logged via RERUM’s versioning; periodic audit reports generated for the **Governance Committee**.
- **UNVERIFIED**: Exact confidence threshold values to be finalized after pilot testing.

---

## 6. Governance & Labor Structure
- **Technical Leads**: Patrick Cuba (RERUM & platform) and Bryan Haberberger (infrastructure, HPC access). They own the AI/LLM pipeline and are responsible for maintaining the RERUM instance.
- **Scholarly Lead**: Thomas J. Finan – provides domain expertise, defines research priorities, and oversees community engagement.
- **Community Committee**: Representatives from each partner repository (DRI, VRTI, Logainm, etc.) meet quarterly to review scope, standards, and attribution policies.
- **Advisory Board**: External scholars (e.g., Christian Frey, Victoria McAlister) consulted annually.
- **Post‑doc / Student Fellows**: One post‑doctoral researcher (to be hired) and graduate student interns to perform data ingestion, validation, and UI prototyping.
- **Funding Model**: No core grant required for year 1; resources provided by SLU Research Computing (HPC time) and in‑kind contributions from partners. Re‑application for external funding can be pursued after the first deliverable is published.

---

## 7. First‑Year Deliverable (Proof‑of‑Concept)
Create a **single contested entity** (e.g., the medieval figure *Toirdhealbhach Briain*) with at least three historically documented name variants, each stored as a separate assertion with provenance links to the Annals of the Four Masters, a Tudor fiant, and a papal letter. The entity will be published in the public API as a demonstration of the ambiguity‑preserving model.

---

## 8. Next Steps (draft agenda)
1. **Kick‑off virtual meeting** (Week 1) – introduce charter, assign roles, schedule milestones.
2. **Repository outreach** (Weeks 2‑4) – invite DRI, VRTI, Logainm contacts to join the Community Committee.
3. **Data model validation** (Weeks 5‑8) – confirm JSON‑LD context with RERUM team; finalize `UNVERIFIED` items.
4. **Prototype contested entity** (Weeks 9‑12) – implement the proof‑of‑concept and publish via the API.
5. **Review & publish charter** (Week 13) – incorporate feedback, mark sections as `VERIFIED` where appropriate.

---

*Prepared by the Oir Working Group (2026‑09‑17).*
