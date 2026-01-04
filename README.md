# FUTURE²: A FAIR-based, User-First, Transparent, Unified, Reproducible, Evolvable and Ethical Framework for Genomic Open Science

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18143817.svg)](https://doi.org/10.5281/zenodo.18143817)

Masaomi Hatakeyama  
GenomicsChain  
January 1, 2026

---

## Abstract

This position paper proposes FUTURE², a design philosophy for next-generation genomic data platforms that extends beyond FAIR principles to address emerging challenges in open science. Despite significant advances in data sharing guided by FAIR (Findable, Accessible, Interoperable, Reusable) principles [1](#references), critical gaps persist in current genomic infrastructures: analytical pipelines remain disconnected from datasets, invisible maintenance labor goes unrecognized, and existing platforms lack readiness for AI-mediated research workflows.

We make three primary contributions. First, we articulate seven integrated principles—**FAIR-based, User-first, Transparent, Unified, Reproducible, Evolvable, and Ethical**—that together form the FUTURE² framework. Second, we demonstrate how FUTURE² integrates FAIR with CARE [2](#references) (for indigenous data governance) and TRUST [3](#references) (for repository trustworthiness) principles, addressing the ethical turn in open science catalyzed by the 2024 CBD COP16 decisions on Digital Sequence Information [4](#references). Third, we present illustrative scenarios showing how these principles translate into platform design requirements. The superscript "²" signifies dual evolution: advancing both technological capability and ethical responsibility.

---

## Introduction

Modern genomics thrives on open culture: open data, open-source software, preprints, and collaborative workflows. The International Nucleotide Sequence Database Collaboration (INSDC)—comprising DDBJ, NCBI GenBank, and EBI ENA—now hosts over 20 petabytes of sequence data, with volumes doubling approximately every three years [5](#references). FAIR principles have improved findability, access, interoperability, and reuse [1](#references); however, significant challenges remain that current infrastructures do not adequately address.

Reproducibility still falters when code, parameters, and computational environments are not packaged alongside data [6](#references). Invisible labor—debugging, dependency updates, documentation, curation, and operations—remains undervalued despite being essential for sustainable infrastructure [7](#references). Usability frictions in key repositories further slow data reuse. Meanwhile, research practice is shifting toward AI-assisted and, soon, agent-mediated workflows, yet most infrastructures are not ready to tie agent actions back to responsible humans or to credit AI-mediated contributions without weakening accountability [8](#references).

Furthermore, the international landscape around genetic data has fundamentally shifted. The 2024 United Nations Biodiversity Conference (CBD COP16) in Cali, Colombia, marked a turning point, guiding Open Science toward a more ethical direction with decisions on Digital Sequence Information (DSI) governance [4](#references). INSDC has committed to aligning with these decisions, requiring richer metadata on country of origin and compliance with FAIR, CARE, and TRUST principles [5](#references).

We introduce FUTURE² (pronounced "FUTURE squared") to address these gaps. The seven principles—**FAIR-based, User-first, Transparent, Unified, Reproducible, Evolvable, and Ethical**—guide the architecture of next-generation genomic platforms. This position paper articulates these principles, situates them within the current landscape of genomic data management, and illustrates their application through concrete scenarios.

---

## Problem Statement

Current genomic data platforms face interconnected challenges across technical, social, and governance dimensions that FAIR principles alone do not resolve.

### Technical Fragmentation

Despite advances in workflow management systems such as Galaxy [9](#references), Nextflow [10](#references), and Snakemake [11](#references), analytical pipelines typically remain separate from the datasets they analyze. Researchers must manually locate compatible workflows, configure execution environments, and manage version dependencies. This separation creates reproducibility barriers: a 2016 study found that only 26% of published bioinformatics analyses could be reproduced, often due to missing code, parameters, or environmental specifications [6](#references). Cloud-based platforms like Terra [12](#references) and DNAnexus [13](#references) address some of these issues but remain siloed ecosystems with limited interoperability.

### Invisible Infrastructure Labor

The maintenance of scientific infrastructure—curating datasets, updating dependencies, fixing bugs, writing documentation, and operating services—remains largely invisible and uncredited [7](#references). Traditional academic incentive structures reward novel discoveries and first-author publications, not the sustained labor required to keep data resources usable. This creates sustainability risks: critical infrastructure may be abandoned when grant funding ends or maintainers move to other positions.

### AI Readiness Gap

Large language models and AI agents are increasingly capable of assisting with data analysis, literature review, and even experimental design [14](#references). However, current platforms lack mechanisms to: (a) authenticate and authorize AI agents acting on behalf of researchers; (b) maintain audit trails linking agent actions to responsible humans; (c) credit AI-mediated contributions appropriately; and (d) apply least-authority principles to limit potential harm from agent errors or misuse.

### Ethical and Sovereignty Dimensions

The 2010 Nagoya Protocol [15](#references) established principles for access and benefit-sharing of genetic resources, and the 2024 CBD COP16 extended these principles to Digital Sequence Information [4](#references). Genomic data is no longer simply "public data"—it may carry sovereign claims, require benefit-sharing arrangements, or demand respect for indigenous data governance principles [2](#references). Most current platforms lack mechanisms to track provenance, enforce access restrictions based on community governance requirements, or surface information about Material Transfer Agreements.

---

## Related Work

### Data Management Principles

The FAIR principles [1](#references)—Findable, Accessible, Interoperable, Reusable—have become the dominant framework for research data management since their publication in 2016. FAIR emphasizes machine-actionability through persistent identifiers, standardized metadata, and open protocols. However, FAIR is explicitly agnostic about data openness and does not address questions of power, sovereignty, or ethics.

The CARE principles [2](#references)—Collective benefit, Authority to control, Responsibility, Ethics—were developed by the Global Indigenous Data Alliance to address indigenous data sovereignty. CARE complements FAIR by centering the rights of indigenous peoples and local communities to govern data derived from their knowledge and resources.

The TRUST principles [3](#references)—Transparency, Responsibility, User focus, Sustainability, Technology—provide criteria for trustworthy digital repositories. TRUST addresses organizational governance, financial sustainability, and technical infrastructure quality.

### Genomic Data Platforms

Galaxy [9](#references) pioneered accessible, web-based genomic analysis with a focus on reproducibility through recorded histories. The Galaxy community has built extensive tool libraries and training resources. However, Galaxy instances typically operate independently with limited federation capabilities.

Terra [12](#references), developed by the Broad Institute and Verily, provides cloud-native genomic analysis integrated with Google Cloud Platform. Terra emphasizes scalability and integration with controlled-access datasets like gnomAD and the All of Us Research Program.

The Global Alliance for Genomics and Health (GA4GH) [16](#references) develops standards for genomic data sharing, including the Data Repository Service (DRS), Workflow Execution Service (WES), and Data Use Ontology (DUO). These standards enable interoperability but require individual platforms to adopt them.

### Workflow Management

Nextflow [10](#references) enables scalable, reproducible workflows using a domain-specific language and supports execution across diverse computing environments. Snakemake [11](#references) provides Python-based workflow management with automatic job scheduling and resource management. The Common Workflow Language (CWL) [17](#references) offers a vendor-neutral specification for describing analysis workflows.

### Provenance and Attribution

The W3C PROV family of specifications [18](#references)[19](#references) provides standard models for representing provenance information. The CRediT taxonomy [20](#references) standardizes contributor role descriptions in scholarly publications. However, systems for tracking and crediting ongoing infrastructure maintenance remain underdeveloped.

---

## The FUTURE² Principles

**Figure 1.** Conceptual representation of FUTURE² at the core of GenomicsChain's design. Seven principles form an interconnected framework aligning data, analysis tools, and contributors (human or AI) in a fluid, adaptive, and ethically responsible ecosystem.

![FUTURE² framework concept](/images/FUTURE_Fig1.png "Figure 1: FUTURE² framework concept")

### FAIR-based — Building on Open Standards

FUTURE² recommits to FAIR for all digital assets—datasets and workflows—using community standards for metadata, persistent identifiers, and formats [21](#references)[22](#references). Resources must be truly machine-actionable with well-documented APIs, persistent identifiers, and rich metadata enabling discovery, access, and reuse by both humans and AI agents.

**Design Requirements:**
- Implement GA4GH DRS for data access and WES for workflow execution
- Assign DOIs or other persistent identifiers to datasets, workflows, and analysis results
- Expose OpenAPI-documented interfaces for programmatic access
- Support standard metadata schemas (e.g., DataCite, Schema.org)

### User-first — Designed for Both Humans and AI

FUTURE² platforms serve two first-class user types: human researchers and AI agents. Intuitive, researcher-friendly interfaces support deposit, execution, and review workflows; parallel programmatic interfaces enable agents to query, launch, and monitor analyses on behalf of their humans.

**Design Requirements:**
- Provide web interfaces with progressive disclosure of complexity
- Implement OAuth 2.0 / OpenID Connect for human authentication
- Support agent authentication with capability-based tokens tied to human accounts
- Design APIs for both interactive and batch/automated use

### Transparent — Visible Processes and Decisions

FUTURE² platforms capture provenance at each step—who/what executed, versions, parameters, inputs/outputs—and make governance decisions public [18](#references)[19](#references). The historically invisible work of maintenance, curation, and operations is surfaced by recording and attributing all contributions [7](#references).

**Design Requirements:**
- Log all operations with W3C PROV-compatible provenance records
- Publish governance policies, change logs, and decision rationales
- Issue non-transferable Proof of Contribution attestations for all work types
- Make contribution histories visible in user profiles and citable

### Unified — Connected Across Platforms

FUTURE² platforms unify data, code, execution, and results so that datasets are always presented with runnable pipelines (containerized) and context. Rather than requiring researchers to hunt for compatible tools, platforms present datasets with ready-to-run analyses.

**Design Requirements:**
- Bundle datasets with associated workflows and execution configurations
- Support Nextflow, Snakemake, and CWL workflow definitions
- Enable workflow portability across execution environments
- Federate with other FUTURE²-compliant platforms

### Reproducible — Fully Replicable Methods

FUTURE² makes reproduction the default outcome through executable pipelines with preserved environments, automated checks when data or pipelines update, one-click reruns, and visible diffs when versions change [23](#references).

**Design Requirements:**
- Require containerized (Docker/Singularity) execution environments
- Automatically re-run analyses when dependencies change
- Badge analyses that have been independently reproduced
- Provide checksums and version locks for all dependencies

### Evolvable — Co-Evolving with Humans and AI

FUTURE² platforms evolve in accountable and sustainable ways. Policy Consoles and least-authority capability tokens define what AI agents may access or do, logging every action in an auditable timeline linked to responsible human accounts [24](#references). Recognition extends beyond discrete commits: Proof of Contribution evolves into Proof of Coevolution (PoC²), capturing the quality and impact of cooperative human-AI workflows.

The system relies on modular, standards-first integration, using containerized tools and explicit interfaces so that new methods or agent skills can be added without breaking past analyses. Open benchmarks over canonical datasets guide decisions about when to retire or upgrade methods. Regulation-aware evolution keeps sensitive data off-chain in verifiable storage, maintains explicit consent trails, and adapts policies as technical capabilities advance.

**Design Requirements:**
- Implement capability-based access control for AI agents
- Log all agent actions with links to authorizing human accounts
- Design modular plugin architectures for new tools and methods
- Maintain backward compatibility for existing analyses

### Ethical — Respecting Sovereignty and Responsible Data Governance

FUTURE² acknowledges that genomic data carries responsibilities and may involve sovereign rights [4](#references)[5](#references). The Ethical principle integrates CARE [2](#references) for indigenous data governance and TRUST [3](#references) for repository trustworthiness.

In alignment with CBD COP16 decisions guiding Open Science toward a more ethical direction, FUTURE² platforms support enhanced metadata requirements for country of origin and responsible DSI governance. Systems surface information about Material Transfer Agreements and permissions for samples derived from biological materials, maintaining clear records of consent, provenance, and restrictions on data use.

**Design Requirements:**
- Implement country-of-origin metadata fields aligned with INSDC requirements
- Support access restrictions based on community governance requirements (DUO terms)
- Surface MTA and consent information in dataset metadata
- Provide mechanisms for communities to assert governance over their data

---

## FAIR + CARE + TRUST: An Integrated Framework

While FAIR focuses on data discoverability and reuse, it does not inherently address questions of power, sovereignty, or ethics. CARE and TRUST complement FAIR:

| Framework | Focus | Key Contribution |
|-----------|-------|------------------|
| **FAIR** [1] | Data discoverability and reuse | Machine-actionable metadata, persistent identifiers |
| **CARE** [2] | Indigenous data governance | Collective benefit, authority to control, responsibility, ethics |
| **TRUST** [3] | Repository trustworthiness | Transparency, responsibility, user focus, sustainability, technology |

**Figure 2.** FAIR, CARE, and TRUST address complementary dimensions of responsible data management. FAIR enables technical interoperability; CARE ensures respect for data sovereignty; TRUST provides organizational governance criteria. FUTURE² integrates all three.

FUTURE² integrates all three frameworks, recognizing that truly open science must also be responsible science. This integration is particularly important as genomic data platforms navigate the post-COP16 landscape where ethical considerations are becoming regulatory requirements.

---

## The COP16 Context: Open Science Toward Ethical Direction

The 2024 United Nations Biodiversity Conference (CBD COP16) in Cali, Colombia, marked a watershed moment for genomic data governance [4](#references). This conference represented an ethical turn in Open Science, as the international community recognized that unrestricted open access to genetic data must be balanced with ethical considerations, including respect for data sovereignty and responsible governance.

Key developments include:

1. **DSI Governance Framework**: New international frameworks for responsible management of Digital Sequence Information on genetic resources
2. **Enhanced Metadata Requirements**: Country of origin and provenance tracking becoming standard expectations
3. **INSDC Response**: Major sequence databases committing to richer metadata requirements and FAIR, CARE, and TRUST principles [5](#references)

FUTURE² aligns with this ethical evolution, providing transparent provenance tracking, metadata enrichment capabilities, and governance structures that can adapt to evolving international requirements. Importantly, FUTURE² positions platforms to comply with emerging requirements rather than requiring costly retrofitting as regulations solidify.

---

## Illustrative Scenarios

The following scenarios demonstrate how FUTURE² principles translate into concrete platform behaviors.

### Scenario 1: DSI-Compliant Data Submission

Dr. Chen has sequenced soil microbiome samples collected in collaboration with indigenous communities in Brazil. Under FUTURE²:

1. **Ethical**: The submission interface prompts for country of origin, community partnerships, and any governance requirements. Dr. Chen uploads the memorandum of understanding with the community, which specifies that derived analyses must acknowledge the community and that commercial use requires separate negotiation.

2. **Transparent**: The platform records this governance information as machine-readable metadata using GA4GH Data Use Ontology terms. The submission provenance captures Dr. Chen's institutional affiliation and the collection context.

3. **FAIR-based**: The dataset receives a DOI and is indexed with rich metadata including taxonomic content, sequencing technology, and geographic origin. Machine-readable access conditions enable automated compliance checking.

4. **Unified**: Dr. Chen attaches the analysis pipeline used for initial characterization. Future users can reproduce her analyses or extend them with compatible workflows.

### Scenario 2: AI-Assisted Analysis with Audit Trail

Dr. Yamamoto wants to use an AI agent to screen 500 published genomic datasets for antibiotic resistance genes. Under FUTURE²:

1. **User-first**: Dr. Yamamoto authenticates to the platform and authorizes the AI agent to act on her behalf, specifying a capability token limited to read-only access for datasets with "unrestricted" access terms.

2. **Evolvable**: The AI agent queries the platform's API, filtering for compatible datasets. For each dataset, it launches a standardized AMR gene detection workflow. All actions are logged with timestamps and links to Dr. Yamamoto's account.

3. **Transparent**: Dr. Yamamoto can review the agent's actions in real-time through a dashboard. The platform generates a provenance record showing which datasets were analyzed, which workflows were used, and what parameters were applied.

4. **Reproducible**: Any other researcher can re-run the identical analysis by referencing the provenance record. The platform automatically checks whether any source datasets have been updated since the original analysis.

### Scenario 3: CARE-Compliant Access Request

A pharmaceutical company wants to analyze genomic data from traditional medicinal plants, some of which are governed by indigenous community protocols. Under FUTURE²:

1. **Ethical**: The platform's discovery interface shows that certain datasets have CARE-compliant governance requiring community consultation. The interface provides contact information and protocol guidance.

2. **Transparent**: The company submits an access request through the platform, describing intended use. This request is routed to designated community representatives and logged in the platform's governance record.

3. **FAIR-based**: For datasets with unrestricted access, the company can immediately begin analysis. For restricted datasets, the platform enforces access controls until community approval is recorded.

4. **Evolvable**: As community governance requirements evolve, the platform can update access policies without breaking existing compliant uses. The company receives notification of policy changes affecting their access.

---

## Discussion

### Adoption Considerations

Implementing FUTURE² requires effort across multiple dimensions. Platform developers must implement new metadata schemas, access control mechanisms, and provenance tracking systems. Researchers must provide richer metadata at submission time. Institutions must allocate resources for platform maintenance and community engagement. However, these costs are justified by several factors:

1. **Regulatory Anticipation**: Post-COP16 requirements are still being specified. Platforms implementing FUTURE² now will be positioned for compliance rather than requiring costly retrofits.

2. **Reproducibility Benefits**: The unified approach to data-workflow bundling directly addresses the reproducibility crisis that wastes an estimated $28 billion annually in preclinical research alone [25](#references).

3. **AI Readiness**: As AI agents become more capable, platforms lacking proper authentication, authorization, and audit mechanisms will face security and accountability risks.

### Standardization Opportunities

FUTURE² aligns with and extends existing standards from GA4GH, W3C, and other bodies. We envision collaboration with:

- **GA4GH**: Extending DRS and WES to support FUTURE² provenance and governance requirements
- **RDA**: Contributing to Research Data Alliance working groups on data citation and attribution
- **INSDC**: Aligning metadata requirements with evolving DSI governance frameworks
- **GIDA**: Ensuring CARE implementation guidance reflects indigenous community input

### Relationship to Existing Platforms

FUTURE² is not intended to replace existing platforms but to provide principles they can adopt. Galaxy, Terra, and similar systems could implement FUTURE² principles incrementally:

- Adding capability-based agent authentication
- Enriching metadata with provenance and governance fields
- Bundling workflows with datasets
- Implementing Proof of Contribution tracking

---

## Limitations and Future Directions

### Current Limitations

This position paper presents FUTURE² as a design philosophy rather than a complete technical specification. Several aspects require further development:

1. **Proof of Contribution Mechanics**: The specific algorithms for measuring and attributing maintenance work, curation quality, and collaborative impact require empirical validation.

2. **Capability Token Standards**: While we draw on capability-based security literature [24](#references), standards for genomic platform agent authentication do not yet exist.

3. **Cross-Platform Federation**: Mechanisms for FUTURE²-compliant platforms to interoperate require protocol specification and reference implementations.

4. **Governance Scaling**: How community governance requirements scale across hundreds of datasets from diverse communities remains underexplored.

### Future Directions

We envision the following development trajectory:

**Near-term (1-2 years)**:
- Publish detailed technical specifications for FUTURE² compliance
- Develop reference implementations for key components (agent authentication, provenance tracking)
- Pilot FUTURE² principles in GenomicsChain platform development

**Medium-term (2-5 years)**:
- Establish FUTURE² certification criteria for platforms
- Build federation protocols enabling cross-platform workflows
- Develop training materials and community adoption support

**Long-term (5+ years)**:
- Integrate FUTURE² requirements into funder data management plan requirements
- Evolve principles based on community feedback and technological change
- Address emerging challenges (e.g., quantum computing impacts on data security)

---

## Conclusion

FUTURE² reframes open genomics infrastructure as a living, auditable, and ethically responsible system:

- **FAIR-based** and machine-actionable, building on established data management principles [1](#references)
- **User-first** for humans and AI agents alike
- **Transparent** in provenance and governance, surfacing invisible labor [7](#references)[18](#references)[19](#references)
- **Unified** across data, tools, and results [10](#references)[11](#references)[17](#references)
- **Reproducible** by default through containerization and environment preservation [23](#references)
- **Evolvable** through accountable human–AI co-evolution [8](#references)[24](#references)
- **Ethical** in respecting sovereignty and integrating CARE and TRUST alongside FAIR [2](#references)[3](#references)[4](#references)

By embracing FUTURE², genomics platforms can meet the technical demands of modern research while honoring the evolving ethical and international frameworks that govern genetic resources. The superscript "²" signifies this dual evolution: advancing both technological capability and ethical responsibility. We invite the genomics community to engage with these principles, critique and refine them, and collaborate on implementations that serve the next generation of open science.

---

## Acknowledgments

We acknowledge the Global Indigenous Data Alliance for developing the CARE principles that inform our approach to data sovereignty. This work builds on the collective efforts of the FAIR, TRUST, and GA4GH communities.

---

## References

[1] Wilkinson, M. D., et al. (2016). The FAIR Guiding Principles for scientific data management and stewardship. *Scientific Data*, 3, 160018. [https://doi.org/10.1038/sdata.2016.18](https://doi.org/10.1038/sdata.2016.18)

[2] Carroll, S. R., Garba, I., Figueroa-Rodríguez, O. L., et al. (2020). The CARE Principles for Indigenous Data Governance. *Data Science Journal*, 19(1), 43. [https://doi.org/10.5334/dsj-2020-043](https://doi.org/10.5334/dsj-2020-043)

[3] Lin, D., Crabtree, J., Dillo, I., et al. (2020). The TRUST Principles for digital repositories. *Scientific Data*, 7, 144. [https://doi.org/10.1038/s41597-020-0486-7](https://doi.org/10.1038/s41597-020-0486-7)

[4] Convention on Biological Diversity (2024). Decision on Digital Sequence Information on Genetic Resources (CBD COP16, Cali, Colombia). [https://www.cbd.int/dsi-gr/](https://www.cbd.int/dsi-gr/)

[5] Arita, M., Karsch-Mizrachi, I., & Cochrane, G. (2021). The international nucleotide sequence database collaboration. *Nucleic Acids Research*, 49(D1), D15–D18. [https://doi.org/10.1093/nar/gkaa967](https://doi.org/10.1093/nar/gkaa967)

[6] Ioannidis, J. P. A., et al. (2009). Repeatability of published microarray gene expression analyses. *Nature Genetics*, 41(2), 149–155. [https://doi.org/10.1038/ng.295](https://doi.org/10.1038/ng.295)

[7] Brand, A., Allen, L., Altman, M., et al. (2015). Beyond authorship: attribution, contribution, and accountability in science. *Learned Publishing*, 28(2), 151–155. [https://doi.org/10.1087/20150211](https://doi.org/10.1087/20150211)

[8] Buterin, V., Weyl, E. G., & Ohlhaver, P. (2022). Decentralized Society: Finding Web3's Soul. *SSRN Working Paper* 4105763.

[9] Afgan, E., et al. (2018). The Galaxy platform for accessible, reproducible and collaborative biomedical analyses: 2018 update. *Nucleic Acids Research*, 46(W1), W537–W544. [https://doi.org/10.1093/nar/gky379](https://doi.org/10.1093/nar/gky379)

[10] Di Tommaso, P., et al. (2017). Nextflow enables reproducible computational workflows. *Nature Biotechnology*, 35(4), 316–319. [https://doi.org/10.1038/nbt.3820](https://doi.org/10.1038/nbt.3820)

[11] Köster, J., & Rahmann, S. (2012). Snakemake—A scalable bioinformatics workflow engine. *Bioinformatics*, 28(19), 2520–2522. [https://doi.org/10.1093/bioinformatics/bts480](https://doi.org/10.1093/bioinformatics/bts480)

[12] Broad Institute. Terra: A cloud-native platform for biomedical research. [https://terra.bio/](https://terra.bio/)

[13] DNAnexus. DNAnexus Platform. [https://www.dnanexus.com/](https://www.dnanexus.com/)

[14] Thirunavukarasu, A. J., et al. (2023). Large language models in medicine. *Nature Medicine*, 29, 1930–1940. [https://doi.org/10.1038/s41591-023-02448-8](https://doi.org/10.1038/s41591-023-02448-8)

[15] Convention on Biological Diversity (2010). Nagoya Protocol on Access to Genetic Resources and the Fair and Equitable Sharing of Benefits Arising from their Utilization. [https://www.cbd.int/abs/](https://www.cbd.int/abs/)

[16] Global Alliance for Genomics and Health. (2016). A federated ecosystem for sharing genomic, clinical data. *Science*, 352(6291), 1278–1280. [https://doi.org/10.1126/science.aaf6162](https://doi.org/10.1126/science.aaf6162)

[17] Amstutz, P., et al. (2016). Common Workflow Language, v1.0. *Figshare*. [https://doi.org/10.6084/m9.figshare.3115156](https://doi.org/10.6084/m9.figshare.3115156)

[18] Moreau, L., et al. (2013). PROV-DM: The PROV Data Model. W3C Recommendation. [https://www.w3.org/TR/prov-dm/](https://www.w3.org/TR/prov-dm/)

[19] Lebo, T., Sahoo, S., & McGuinness, D. (2013). PROV-O: The PROV Ontology. W3C Recommendation. [https://www.w3.org/TR/prov-o/](https://www.w3.org/TR/prov-o/)

[20] Brand, A., et al. (2015). Beyond authorship: Attribution, contribution, collaboration, and credit. *Learned Publishing*, 28(2), 151–155.

[21] DataCite Metadata Working Group. (2021). DataCite Metadata Schema Documentation for the Publication and Citation of Research Data, Version 4.4. [https://doi.org/10.14454/3w3z-sa82](https://doi.org/10.14454/3w3z-sa82)

[22] Haak, L. L., et al. (2012). ORCID: A system to uniquely identify researchers. *Learned Publishing*, 25(4), 259–264. [https://doi.org/10.1087/20120404](https://doi.org/10.1087/20120404)

[23] Merkel, D. (2014). Docker: Lightweight Linux containers for consistent development and deployment. *Linux Journal*, 2014(239).

[24] Miller, M. S., Shapiro, J., & Tribble, E. (2003). Capability Myths Demolished. Technical Report, Johns Hopkins University.

[25] Freedman, L. P., Cockburn, I. M., & Simcoe, T. S. (2015). The economics of reproducibility in preclinical research. *PLoS Biology*, 13(6), e1002165. [https://doi.org/10.1371/journal.pbio.1002165](https://doi.org/10.1371/journal.pbio.1002165)

