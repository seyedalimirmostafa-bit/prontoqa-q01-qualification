# A bounded qualification of PrOntoQA-OOD

**Finite generator capacity and citation-local scoring**

**Author:** SeyedAli Mirmostafa  
**Study:** PrOntoQA Q01 (frozen 10 October 2026; retrospective audit 11 October 2026)  
**Status:** Public technical research note; **not peer reviewed**. Substantial AI assistance is disclosed.

> **RC3 attribution correction pending:** The files currently in the repository are from an older release. New RC3 files correcting the author spelling to **SeyedAli Mirmostafa** are prepared, but have not yet been uploaded. Do not cite the repository as the finalized RC3 release until both files match the checksums below.

## Publication files

- [Research note — PDF](PrOntoQA_Q01_Public_Note.pdf) — four-page technical note.
- [Reproducibility and evidence archive — ZIP](PrOntoQA_Q01_Public_Evidence.zip) — frozen records, failed attempts, code, saved reviews, attribution, licenses and validation instructions.

The *corrected RC3 versions* must match these SHA-256 checksums exactly:

| File | SHA-256 |
| --- | --- |
| `PrOntoQA_Q01_Public_Note.pdf` | `e27713fea96dff7cabb88393cdc50cbeef4c6ba1101ade255477e9396c7479f6` |
| `PrOntoQA_Q01_Public_Evidence.zip` | `66b32e0085085ea6a2190c47b0aba805e2e7f4207b621376a9521d2c2b75c53f` |

## Summary

This is a **configuration-specific implementation qualification**, not a novel recursive self-improvement finding or a claim about language-model reasoning performance. It evaluates the supply of valid problems under a pinned PrOntoQA-OOD generator configuration and separately qualifies a citation-local symbolic scorer.

- Each of two identical saved passes attempted **1,574** generations and returned **44** valid examples; the replay adds no new formal examples.
- Under the relevant-distractor setting, depths **5** and **7** returned **0/400** examples each. Source-level analysis shows **depth 7 is impossible under this exact configuration**: an accepted construction would require at least 15 initial property families, while 13 are available. This does **not** prove depth-5 impossibility or apply to other configurations.
- The registered scorer fixtures matched **25/25** expected cases. The saved 2SAT/exhaustive-check report records **5,120** comparisons with zero mismatches, but individual comparison rows were not retained.
- The study includes **44** matched valid/invalid citation-local reasoning pairs. This is not a measured LLM benchmark result.
- The pre-specified relevant-depth-5 supply gate **failed**, so the original experimental verdict remains **STOP**. No LLM inference, model improvement or RSI was tested.

**Pinned upstream revision:** [asaparov/prontoqa @ `0a6412b6fddf46324a1cb96e066dd7b3d89b87d6`](https://github.com/asaparov/prontoqa/tree/0a6412b6fddf46324a1cb96e066dd7b3d89b87d6) (PrOntoQA-OOD on `main`, not original `v1`).

## Inspecting the evidence

After downloading and extracting the evidence ZIP into a disposable folder, run with Python 3.9+:

```bash
python verify_release.py
```

This **only validates saved archive records** and performs no generator, scorer, model inference or network execution. Its assertions are bounded; it is not a reproduction of the original experiment. The ZIP's `README.txt` provides full instructions and requirements for an **optional fresh reproduction** (recorded environment: Windows x64, PowerShell 7, Python 3.12.14, NumPy 2.3.5). That reproduction was not run as part of public-release preparation. Review executable code before using it and do not run experiments in the archived evidence directory.

## Licensing and attribution

- Author-controlled Q01 **original code and scripts:** [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
- Author-controlled **research note, documentation and records:** [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).
- **Upstream PrOntoQA source snapshot:** retains its existing Apache-2.0 license and original notices. No rights are claimed beyond what the author can license.

The archive includes full license texts, `LICENSE_MAP.json`, `LICENSING.txt` and `NOTICE.txt`, and credits the upstream authors and papers.

**AI-assistance disclosure:** OpenAI Codex assisted with the Q01 protocol, harness and scorer, experimental execution, interpretation and preparation of the technical note. Separate AI agents performed audits and critical review; they are **not independent human peer reviewers**. The paper describes the evidence, limitations, and the scope of these contributions.

## References

- Saparov & He, *Language Models Are Greedy Reasoners: A Systematic Formal Analysis of Chain-of-Thought*, ICLR 2023, [arXiv:2210.01240](https://arxiv.org/abs/2210.01240).
- Saparov et al., *Testing the General Deductive Reasoning Capacity of Large Language Models Using OOD Examples*, NeurIPS 2023, [arXiv:2305.15269](https://arxiv.org/abs/2305.15269).

The report documents a narrow, auditable finding and does not claim benchmark invalidity, general impossibility, established originality, or human peer review.
