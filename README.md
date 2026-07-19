# hack-nation-2026

## Challenge

**Hack-Nation 6th Global AI Hackathon — Challenge 06**
**Genome Firewall: An AI Defense System Against Superbugs**
*In collaboration with MIT Club of Northern California and MIT Club of Germany, powered by Hack-Nation, enabled by OpenAI*

### Overview

Use artificial intelligence to predict which antibiotics may fail from a bacterial genome — before standard laboratory results arrive.

Antibiotic-resistant infections are associated with more than 4.7 million deaths each year, and over one million people die directly because existing antibiotics no longer work. Standard laboratory testing to determine which antibiotic will work usually takes one to three days, forcing healthcare teams to treat patients with incomplete information in the meantime.

Much of the answer is already written in a bacterium's DNA. Once a genome has been sequenced and reconstructed, AI can identify patterns that predict which antibiotics are likely to work — potentially days before standard lab testing is complete.

### Our Task

Build **Genome Firewall**, a research prototype that takes a reconstructed, quality-checked genome from **one supported bacterial species (Klebsiella pneumoniae)** and predicts, for each antibiotic, whether it is:

- **likely to fail**
- **likely to work**
- **no-call** (uncertain, evidence insufficient)

Each prediction includes a calibrated confidence score, an explicit no-call option, and the genes or DNA changes supporting it. This is strictly **defensive, decision-support software** — it must never design, modify, or suggest changes to an organism, and every result must be confirmed by standard laboratory testing before any treatment decision is made.

### Required Modules

1. **Genome Reader** — turns a reconstructed bacterial genome into AI-usable features (resistance gene/mutation detection via AMRFinderPlus)
2. **Predictor** — per-antibiotic prediction (likely to fail / likely to work / no-call), gated by the presence of each drug's molecular target, trained with sequence-homology de-duplication between train and test sets
3. **Decision Report** — a working demo (Streamlit/Gradio) presenting each result with a calibrated confidence score, an evidence category, and a mandatory "confirm with standard lab testing" disclaimer

### Responsibility Requirement

The system must be defensive by construction, generalize honestly across genetically related bacterial groups, return well-calibrated confidence with a no-call option, clearly separate known resistance genes from statistical associations, and remain decision support that requires human (clinical/laboratory) oversight — never an autonomous treatment decision.
