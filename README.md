# FUTURE²: A FAIR-based, User-First, Transparent, Unified, Reproducible, Evolvable and Ethical Framework for Genomic Open Science

Masaomi Hatakeyama  
GenomicsChain  
January 1, 2026
DOI: 10.5281/zenodo.XXXXXXXX (to be assigned)

---

## Abstract

Open science and data-sharing initiatives in genomics have achieved tremendous gains in collaboration and reproducibility, guided by FAIR data management [1](#references). Yet practical gaps persist: pipelines are separated from data, invisible maintenance work goes uncredited, and interfaces remain cumbersome for researchers and machines. We propose FUTURE², a design philosophy for next-generation platforms, standing for **FAIR-based, User-first, Transparent, Unified, Reproducible, Evolvable and Ethical**. This revision extends the original FUTURE framework by incorporating an explicit Ethical dimension, reflecting the international community's evolving stance on Digital Sequence Information (DSI) governance following the 2024 United Nations Biodiversity Conference (CBD COP16) decisions. We integrate principles from CARE [13](#references) (Collective benefit, Authority to control, Responsibility, Ethics) and TRUST [14](#references) (Transparency, Responsibility, User focus, Sustainability, Technology), alongside FAIR, to ensure genomic data platforms respect indigenous data sovereignty, support benefit-sharing mechanisms, and maintain trustworthy digital repositories. The "Evolvable and Ethical" pillar now encompasses accountable co-evolution between humans and AI agents, as well as ethical governance of genetic resources in alignment with international frameworks.

---

## Introduction

Modern genomics thrives on open culture, open data, open-source software, preprints, and collaborative workflows. FAIR has improved findability, access, interoperability, and reuse [1](#references); however, reproducibility still falters when code, parameters, and environments are not packaged with data. Invisible labor—debugging, dependency updates, documentation, curation, operations—remains undervalued [10](#references). Usability frictions in key repositories further slow reuse. Meanwhile, research practice is shifting toward AI-assisted and, soon, agent-mediated workflows. Most infrastructures are not ready to tie agent actions back to a responsible human or to credit AI-mediated contributions without weakening accountability [11](#references).

Furthermore, the international landscape around genetic data has fundamentally shifted. The 2024 United Nations Biodiversity Conference (CBD COP16) in Cali, Colombia, established a multilateral mechanism for benefit-sharing from the utilization of Digital Sequence Information (DSI), including the creation of the Cali Fund [15](#references). The International Nucleotide Sequence Database Collaboration (INSDC)—comprising DDBJ, NCBI GenBank, and EBI ENA—has committed to aligning with these decisions, requiring richer metadata on country of origin and compliance with FAIR, CARE, and TRUST principles [16](#references).

We introduce FUTURE² (pronounced "FUTURE squared") to address these gaps. The seven principles—**FAIR-based, User-first, Transparent, Unified, Reproducible, Evolvable, and Ethical**—guide the architecture of GenomicsChain and similar platforms. This revision strengthens the final pillar: platforms must adapt not only technically, but also in how people and AI agents learn and work together under explicit governance, while respecting the ethical, legal, and sovereignty dimensions of genetic resources.

---

## The FUTURE² Principles for GenomicsChain

**Figure 1.** Conceptual representation of FUTURE² at the core of GenomicsChain's design. Seven principles (FAIR-based, User-first, Transparent, Unified, Reproducible, Evolvable, Ethical) form an interconnected framework aligning data, analysis tools, and contributors (human or AI) in a fluid, adaptive, and ethically responsible ecosystem.

![FUTURE² framework concept](/images/FUTURE_Fig1.png "Figure 1: FUTURE² framework concept")

### FAIR-based — Building on Open Standards

Recommit to FAIR for all digital assets—datasets and workflows—using community standards for metadata, persistent identifiers, and formats [8](#references)[9](#references). Make resources truly machine-actionable with well-documented APIs, persistent IDs, and rich metadata so both humans and agents can discover, access, and reuse them. FAIR principles remain the foundation, but they are now complemented by CARE and TRUST to address dimensions that FAIR alone does not cover.

### User-first — Designed for Both Humans and AI

Serve two first-class user types: researchers and AI agents. Provide intuitive, researcher-friendly deposit/run/review workflows; in parallel, expose reliable programmatic interfaces so agents can query, launch, and monitor analyses on behalf of their humans.

### Transparent — Visible Processes and Decisions

Capture provenance at each step—who/what ran, versions, parameters, inputs/outputs—and keep governance decisions public [6](#references)[7](#references). Surface the historically invisible work by recording and attributing maintenance, curation, and operational contributions [10](#references). Platforms may optionally issue non-transferable Proof of Contribution attestations that appear in contributor profiles and are citable.

### Unified — Connected Across Platforms

Unify data, code, execution, and results so that a dataset is always presented with runnable pipelines (containerized) and context. Workflow managers such as Nextflow [3](#references) and Snakemake [4](#references) have shown the importance of this integration, as has the Common Workflow Language [5](#references).

### Reproducible — Fully Replicable Methods

Make reproduction the default outcome: executable pipelines with preserved environments; automated checks when data/pipelines update; one-click reruns; and visible diffs when versions change. Workflow reproducibility is reinforced by containerization technologies like Docker [2](#references). Badge analyses that have been independently reproduced to incentivize rigor and reuse.

### Evolvable — Co-Evolving with Humans and AI

The platform is built to evolve in accountable and sustainable ways:

- **Agent-ready controls**: Policy Console and least-authority capability tokens define what an AI agent may access or do, logging every action in an auditable timeline and linking it to a responsible human account [12](#references).
- **Recognition beyond commits**: Proof of Contribution extends to Proof of Coevolution (PoC²), capturing the quality and impact of cooperative workflows—maintenance that improves rerun success, curation that enhances discovery, or agent-assisted optimization that reduces compute cost while preserving accuracy.
- **Modular, standards-first integration**: Containerized tools and explicit interfaces enable new methods or agent skills to be added without breaking past analyses.
- **Continuous evaluation**: Open benchmarks over canonical datasets guide when to retire or upgrade methods.
- **Regulation-aware evolution**: Sensitive data stays off-chain in verifiable storage, explicit consent trails are maintained, and policies adapt as technical capabilities advance.

### Ethical — Respecting Sovereignty and Enabling Benefit-Sharing

The Ethical principle acknowledges that genomic data is no longer simply "public data"—it carries responsibilities and may involve sovereign rights [15](#references)[16](#references):

- **CARE Principles Integration**: Respect Collective benefit, Authority to control, Responsibility, and Ethics as articulated by the Global Indigenous Data Alliance [13](#references). Recognize that some genetic resources are subject to community governance and require explicit acknowledgment.
- **TRUST Principles Alignment**: Ensure Transparency, Responsibility, User focus, Sustainability, and Technology standards for trustworthy digital repositories [14](#references).
- **CBD COP16 Compliance**: Support the decisions of the 2024 United Nations Biodiversity Conference regarding DSI, including contribution to the Cali Fund for benefit-sharing and enhanced metadata requirements for country of origin [15](#references).
- **INSDC Alignment**: Follow INSDC's evolving policies on DSI, including richer metadata requirements and submitter notifications regarding benefit-sharing obligations [16](#references).
- **Material Transfer Agreement Awareness**: Surface information about MTAs and permissions for samples derived from foreign biological materials.
- **Consent and Provenance Tracking**: Maintain clear records of consent, provenance, and any restrictions on data use.

---

## FAIR + CARE + TRUST: An Integrated Framework

While FAIR focuses on making data findable, accessible, interoperable, and reusable, it does not inherently address questions of power, sovereignty, or ethics. CARE and TRUST complement FAIR:

| Framework | Focus | Key Contribution |
|-----------|-------|------------------|
| **FAIR** [1] | Data discoverability and reuse | Machine-actionable metadata, persistent identifiers |
| **CARE** [13] | Indigenous data governance | Collective benefit, authority to control, responsibility, ethics |
| **TRUST** [14] | Repository trustworthiness | Transparency, responsibility, user focus, sustainability, technology |

FUTURE² integrates all three frameworks, recognizing that truly open science must also be responsible science.

---

## The COP16 Context: Digital Sequence Information and the Cali Fund

The 2024 United Nations Biodiversity Conference (CBD COP16) in Cali, Colombia, marked a watershed moment for genomic data governance [15](#references):

- **Multilateral Mechanism**: A new global framework was established for sharing benefits arising from the use of Digital Sequence Information (DSI) on genetic resources.
- **Cali Fund**: A global fund to channel contributions from DSI users, particularly those in for-profit sectors, to biodiversity conservation and sustainable use.
- **Timeline**: Contribution rates and enterprise scope will be finalized at COP17 (Armenia, October 2026).
- **INSDC Response**: The major sequence databases (DDBJ, NCBI, ENA) have committed to enhanced metadata requirements, submitter notifications, and alignment with FAIR, CARE, and TRUST principles [16](#references).

GenomicsChain's FUTURE² framework is designed to support these developments by providing transparent provenance tracking, metadata enrichment capabilities, and governance structures that can adapt to evolving international requirements.

---

## Discussion

Transparent provenance plus PoC/PoC² makes maintenance, curation, and operations visible and valuable, encouraging sustainable participation [10](#references). Unified, containerized workflows embedded next to data eliminate the data/code round-trip [2](#references)[3](#references)[4](#references). Agent-readiness, capability tokens, and policy consoles [12](#references) make agent-mediated research tractable: compliant by design, reproducible by default, and credit-aware.

The addition of the Ethical dimension reflects a maturing understanding within the genomics community that open access alone is insufficient. As Dr. Masaki Arita of DDBJ has noted, "Genome data is no longer simply 'public data'"—it may carry sovereign claims, require benefit-sharing, and demand richer provenance information [16](#references). FUTURE² acknowledges these realities while maintaining the core commitment to open science that has driven genomics forward.

---

## Conclusion

FUTURE² reframes open genomics infrastructure as a living, auditable, and ethically responsible system:

- **FAIR-based** and machine-actionable [1](#references)
- **User-first** for humans and AI
- **Transparent** in provenance and governance [6](#references)[7](#references)[10](#references)
- **Unified** across data, tools, and results [3](#references)[4](#references)[5](#references)
- **Reproducible** by default [2](#references)
- **Evolvable** through accountable human–AI co-evolution [11](#references)[12](#references)
- **Ethical** in respecting sovereignty, enabling benefit-sharing, and integrating CARE and TRUST alongside FAIR [13](#references)[14](#references)[15](#references)

By embracing FUTURE², genomics platforms can meet the technical demands of modern research while honoring the evolving ethical and international frameworks that govern genetic resources. The superscript "²" in FUTURE² signifies this dual evolution: advancing both technological capability and ethical responsibility.

---

## References

[1] Wilkinson, M. D., et al. (2016). The FAIR Guiding Principles for scientific data management and stewardship. *Scientific Data*, 3, 160018. [https://doi.org/10.1038/sdata.2016.18](https://doi.org/10.1038/sdata.2016.18)

[2] Merkel, D. (2014). Docker: Lightweight Linux containers for consistent development and deployment. *Linux Journal*, 2014(239).

[3] Di Tommaso, P., et al. (2017). Nextflow enables reproducible computational workflows. *Nature Biotechnology*, 35(4), 316–319. [https://doi.org/10.1038/nbt.3820](https://doi.org/10.1038/nbt.3820)

[4] Köster, J., & Rahmann, S. (2012). Snakemake—A scalable bioinformatics workflow engine. *Bioinformatics*, 28(19), 2520–2522. [https://doi.org/10.1093/bioinformatics/bts480](https://doi.org/10.1093/bioinformatics/bts480)

[5] Amstutz, P., et al. (2016). Common Workflow Language, v1.0. *arXiv preprint* arXiv:1608.09145.

[6] Moreau, L., et al. (2013). PROV-DM: The PROV Data Model. W3C Recommendation.

[7] Lebo, T., Sahoo, S., & McGuinness, D. (2013). PROV-O: The PROV Ontology. W3C Recommendation.

[8] DataCite Metadata Working Group. (2021). DataCite Metadata Schema Documentation for the Publication and Citation of Research Data, Version 4.4.

[9] Haak, L. L., et al. (2012). ORCID: A system to uniquely identify researchers. *Learned Publishing*, 25(4), 259–264. [https://doi.org/10.1087/20120404](https://doi.org/10.1087/20120404)

[10] Brand, A., Allen, L., Altman, M., et al. (2015). Beyond authorship: attribution, contribution, and accountability in science. *Learned Publishing*, 28(2), 151–155. [https://doi.org/10.1087/20150211](https://doi.org/10.1087/20150211)

[11] Buterin, V., Weyl, E. G., & Ohlhaver, P. (2022). Decentralized Society: Finding Web3's Soul. *SSRN Working Paper* 4105763.

[12] Miller, M. S., Shapiro, J., & Tribble, E. (2003). Capability Myths Demolished. EROS and Capabilities (HP Labs / Johns Hopkins APL technical report).

[13] Carroll, S. R., Garba, I., Figueroa-Rodríguez, O. L., et al. (2020). The CARE Principles for Indigenous Data Governance. *Data Science Journal*, 19(1), 43. [https://doi.org/10.5334/dsj-2020-043](https://doi.org/10.5334/dsj-2020-043) | [GIDA Global](https://www.gida-global.org/care)

[14] Lin, D., Crabtree, J., Dillo, I., et al. (2020). The TRUST Principles for digital repositories. *Scientific Data*, 7, 144. [https://doi.org/10.1038/s41597-020-0486-7](https://doi.org/10.1038/s41597-020-0486-7)

[15] Convention on Biological Diversity (2024). Decision on Digital Sequence Information on Genetic Resources (CBD COP16, Cali, Colombia). [https://www.cbd.int/dsi-gr/](https://www.cbd.int/dsi-gr/)

[16] Arita, M. (2025). Ethics and International Issues in Open Science. Presentation at the Annual Meeting of the Molecular Biology Society of Japan. DDBJ Center, National Institute of Genetics.


