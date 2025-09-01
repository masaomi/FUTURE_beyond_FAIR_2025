# FUTURE: A FAIR-based, User-First, Transparent, Unified, Reproducible, Evolvable Framework for Genomic Open Science

*Masaomi Hatakeyama (GenomicsChain)*
*2025.09.01*

---

## Abstract

Open science and data-sharing initiatives in genomics have achieved tremendous gains in collaboration and reproducibility, guided by FAIR data management \[1]. Yet practical gaps persist: pipelines are separated from data, invisible maintenance work goes uncredited, and interfaces remain cumbersome for researchers and machines. We propose FUTURE—a design philosophy for next-generation platforms such as GenomicsChain—standing for FAIR-based, User-first, Transparent, Unified, Reproducible, Evolvable. This revision emphasizes Evolvable as accountable co-evolution between humans and AI agents: agent actions are linked to a responsible human, governed by least-authority capability tokens \[12], surfaced in an auditable action timeline, and recognized alongside human work. We outline how FUTURE integrates data, code, and governance to deliver immediate reproducibility, reward invisible labor (e.g., through non-transferable Proof of Contribution attestations), and prepare for AI-assisted research.

---

## Introduction

Modern genomics thrives on open culture—open data, open-source software, preprints, and collaborative workflows. FAIR has improved findability, access, interoperability, and reuse \[1]; however, reproducibility still falters when code, parameters, and environments are not packaged with data. Invisible labor—debugging, dependency updates, documentation, curation, operations—remains undervalued \[10]. Usability frictions in key repositories further slow reuse. Meanwhile, research practice is shifting toward AI-assisted and, soon, agent-mediated workflows. Most infrastructures are not ready to tie agent actions back to a responsible human or to credit AI-mediated contributions without weakening accountability \[11].

We introduce FUTURE to address these gaps. The six principles—FAIR-based, User-first, Transparent, Unified, Reproducible, Evolvable—guide the architecture of GenomicsChain and similar platforms. This revision strengthens the Evolvable pillar: platforms must adapt not only technically, but also in how people and AI agents learn and work together under explicit governance.

---

## The FUTURE Principles for GenomicsChain

**Figure 1.** Conceptual representation of FUTURE at the core of GenomicsChain’s design. Six principles (FAIR-based, User-first, Transparent, Unified, Reproducible, Evolvable) form an interconnected framework aligning data, analysis tools, and contributors (human or AI) in a fluid, adaptive ecosystem.

![FUTURE framework concept](/images/FUTURE_Fig1.png "Figure 1: FUTURE framework concept")

### FAIR-based — building on open standards

Recommit to FAIR for all digital assets—datasets and workflows—using community standards for metadata, persistent identifiers, and formats \[8]\[9]. Make resources truly machine-actionable with well-documented APIs, persistent IDs, and rich metadata so both humans and agents can discover, access, and reuse them.

### User-first — designed for both humans and AI

Serve two first-class user types: researchers and AI agents. Provide intuitive, researcher-friendly deposit/run/review workflows; in parallel expose reliable programmatic interfaces so agents can query, launch, and monitor analyses on behalf of their humans.

### Transparent — visible processes and decisions

Capture provenance at each step—who/what ran, versions, parameters, inputs/outputs—and keep governance decisions public \[6]\[7]. Surface the historically invisible work by recording and attributing maintenance, curation, and operational contributions \[10]. Platforms may optionally issue non-transferable Proof of Contribution attestations that appear in contributor profiles and are citable.

### Unified — connected across platforms

Unify data, code, execution, and results so that a dataset is always presented with runnable pipelines (containerized) and context. Workflow managers such as Nextflow \[3] and Snakemake \[4] have shown the importance of this integration, as has the Common Workflow Language \[5].

### Reproducible — fully replicable methods

Make reproduction the default outcome: executable pipelines with preserved environments; automated checks when data/pipelines update; one-click reruns; and visible diffs when versions change. Workflow reproducibility is reinforced by containerization technologies like Docker \[2]. Badge analyses that have been independently reproduced to incentivize rigor and reuse.

### Evolvable — co-evolving with humans and AI

1. **Agent-ready controls & accountability.** Provide a Policy Console and least-authority capability tokens \[12] defining what an agent may access or do. Log every agent action in an auditable timeline and link it to a responsible human account.
2. **From PoC to PoC².** Extend recognition beyond discrete commits to capture the quality and impact of cooperative workflows—maintenance that raises rerun success, curation that improves discovery, or agent-assisted optimization that reduces compute while preserving accuracy. Inspired partly by decentralized identity and reputation concepts \[11].
3. **Modular, standards-first integration.** Adopt containerized tools and explicit interfaces so new methods and agent skills can be plugged in without breaking past analyses.
4. **Continuous evaluation.** Maintain open, periodic benchmarks over canonical datasets to decide when to retire/upgrade methods.
5. **Regulation-aware evolution.** Keep sensitive data off-chain with verifiable off-chain storage and explicit consent trails; evolve policies alongside capabilities.

---

## Discussion

Transparent provenance plus PoC/PoC² makes maintenance, curation, and operations visible and valuable, encouraging sustainable participation \[10]. Unified, containerized workflows embedded next to data eliminate the data/code round-trip \[2]\[3]\[4]. Agent-readiness, capability tokens, and policy consoles \[12] make agent-mediated research tractable: compliant by design, reproducible by default, and credit-aware.

---

## Conclusion

FUTURE reframes open genomics infrastructure as a living, auditable system: FAIR-based and machine-actionable \[1], user-first for humans and AI, transparent in provenance and governance \[6]\[7]\[10], unified across data, tools, and results \[3]\[4]\[5], reproducible by default \[2], and evolvable through accountable human–AI co-evolution \[11]\[12].

---

## References

\[1] Wilkinson, M. D., et al. (2016). The FAIR Guiding Principles for scientific data management and stewardship. *Scientific Data*, 3, 160018. [https://doi.org/10.1038/sdata.2016.18](https://doi.org/10.1038/sdata.2016.18)
\[2] Merkel, D. (2014). Docker: Lightweight Linux containers for consistent development and deployment. *Linux Journal*, 2014(239).
\[3] Di Tommaso, P., et al. (2017). Nextflow enables reproducible computational workflows. *Nature Biotechnology*, 35(4), 316–319. [https://doi.org/10.1038/nbt.3820](https://doi.org/10.1038/nbt.3820)
\[4] Köster, J., & Rahmann, S. (2012). Snakemake—A scalable bioinformatics workflow engine. *Bioinformatics*, 28(19), 2520–2522. [https://doi.org/10.1093/bioinformatics/bts480](https://doi.org/10.1093/bioinformatics/bts480)
\[5] Amstutz, P., et al. (2016). Common Workflow Language, v1.0. *arXiv preprint* arXiv:1608.09145.
\[6] Moreau, L., et al. (2013). PROV-DM: The PROV Data Model. W3C Recommendation.
\[7] Lebo, T., Sahoo, S., & McGuinness, D. (2013). PROV-O: The PROV Ontology. W3C Recommendation.
\[8] DataCite Metadata Working Group. (2021). DataCite Metadata Schema Documentation for the Publication and Citation of Research Data, Version 4.4.
\[9] Haak, L. L., et al. (2012). ORCID: A system to uniquely identify researchers. *Learned Publishing*, 25(4), 259–264. [https://doi.org/10.1087/20120404](https://doi.org/10.1087/20120404)
\[10] Brand, A., Allen, L., Altman, M., et al. (2015). Beyond authorship: attribution, contribution, and accountability in science. *Learned Publishing*, 28(2), 151–155. [https://doi.org/10.1087/20150211](https://doi.org/10.1087/20150211)
\[11] Buterin, V., Weyl, E. G., & Ohlhaver, P. (2022). Decentralized Society: Finding Web3’s Soul. *SSRN Working Paper* 4105763.
\[12] Miller, M. S., Shapiro, J., & Tribble, E. (2003). Capability Myths Demolished. EROS and Capabilities (HP Labs / Johns Hopkins APL technical report).

-