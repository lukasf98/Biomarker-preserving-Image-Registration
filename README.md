# Biomarker-Preserving Image Registration

Code for our entry to **Learn2Reg 2026, Task 1 (PSMAReg)**: longitudinal whole-body PSMA PET/CT registration that keeps the tumour biomarkers PSMA-TV and TL-PSMA intact.

> **Auxiliary Segmentation Supervision and Biomarker-Preserving Instance Optimisation for Longitudinal Whole-Body PSMA PET/CT Registration**\
> Lukas Förner, Thomas Wendler\
> Learn2Reg 2026 challenge proceedings (to appear) · paper link coming soon

**Status:** the code is being cleaned up and will be released in this repository soon. Watch the repository to be notified.

## Method

1. **Rigid pre-alignment** of the two CT scans (ANTs), which preserves lesion volumes.
2. **TransMorph** (time-varying velocity, half resolution) with auxiliary organ and lesion segmentation heads.
3. **Biomarker-aware instance optimisation** per case, driven by predicted organ and lesion masks, with PSMA-TV and TL-PSMA losses and a lesion-local Jacobian penalty.
4. **Fold repair** that smooths the field only where folding is counted, to stay below the challenge's %NDV tolerance.

## Results

2nd on the validation leaderboard (DSC 0.797, HD95 5.14 mm, PSMA-TV error 1.45 %, TL-PSMA error 1.57 %) and 6th in the test phase, 3rd on both biomarker metrics.

## Citation

```bibtex
@inproceedings{foerner2026biomarker,
  title     = {Auxiliary Segmentation Supervision and Biomarker-Preserving Instance
               Optimisation for Longitudinal Whole-Body {PSMA} {PET/CT} Registration},
  author    = {F{\"o}rner, Lukas and Wendler, Thomas},
  booktitle = {Learn2Reg 2026 Challenge Proceedings (to appear)},
  year      = {2026}
}
```

## Acknowledgements

Built on [TransMorph / MIR](https://github.com/junyuchen245/MIR). Organ masks come from [TotalSegmentator](https://github.com/wasserth/TotalSegmentator), lesion masks from the winning model of autoPET III.

## Contact

Lukas Förner, lukas.foerner@uk-augsburg.de, or open an issue.
