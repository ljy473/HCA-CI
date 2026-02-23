# HCA-CI
HCA-CI is a text-based person retrieval framework that addresses semantic misalignment and compositional drift via hierarchical concept alignment and counterfactual contrastive learning, and introduces SPRank-k as a semantic-consistency evaluation perspective beyond strict ID matching.

**Human Consistency Study for SPRank-k**

To validate the reliability of the proposed SPRank-k metric and to mitigate potential model-induced bias, we conduct a small-scale human consistency study on ID-mismatch retrieval cases.

**Data Composition**

We randomly sample 200 ID-mismatch query–gallery cases from the CUHK-PEDES test set, including:

100 SPRank-positive samples (ranked as positive by SPRank-k)

100 SPRank-negative samples (ranked as negative by SPRank-k)

For reproducibility, we release the human votes and the corresponding sample indices / image file names (or relative paths) for each query–gallery pair.
We do not redistribute any raw images and only provide metadata, in order to respect the dataset ownership and usage terms.
Researchers should obtain CUHK-PEDES from the dataset authors/maintainers (or other authorized sources) and use the provided indices/paths to locate the images locally.

Each sample is independently annotated by three human raters, who are asked to judge whether the image pair is:

SAME (semantically consistent / human-match),

DIFFERENT (semantically inconsistent / human-mismatch), or

UNSURE (ambiguous or difficult to judge).

The final human label is determined by majority voting.
Samples with no clear majority—i.e., three UNSURE votes, or SAME + DIFFERENT + UNSURE—are treated as uncertain and excluded from quantitative evaluation.

**The raw annotations and merged voting results are provided in:**

IDmismatch_SPRankPos_sample100_*.xlsx

IDmismatch_SPRankNeg_sample100_*.xlsx

POS_human_vote_merged.xlsx

NEG_human_vote_merged.xlsx

Quantitative Results

After removing uncertain samples, 187 non-uncertain cases remain for evaluation.

**Quantitatively:**

POS precision (human match rate within SPRank-positive) is 0.7447

NEG precision (human mismatch rate within SPRank-negative) is 0.8710

The overall human agreement accuracy reaches 0.8075

These results indicate that SPRank-k exhibits strong consistency with human semantic judgment, supporting its validity as a semantic-consistency–oriented evaluation perspective beyond strict ID matching.


<img width="995" height="567" alt="image" src="https://github.com/user-attachments/assets/f78d78c5-16a6-440f-9c2b-77ec92cd74d0" />


Human-SPRank agreement vs. visual similarity. Green/red points denote SPRank-k predictions (POS/NEG). Opaque points indicate that the SPRank-k prediction agrees with the human majority-vote label (match for POS, mismatch for NEG), while translucent points indicate disagreement. ‘×’ marks samples labeled as uncertain under human voting (majority unsure or no majority). GT Image refers to the ground-truth image of the query identity.

