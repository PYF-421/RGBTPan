# RGBTPan

Offline foundation-model supervision for label-efficient low-light RGB-thermal panoptic segmentation.

Official repository for the manuscript *Offline Foundation-Model Supervision for Label-Efficient
Low-Light RGB-T Panoptic Segmentation* (Yufan Pu, Shi Yi, Tianming Yang, Huiqi Wu, Junwei Huang),
currently under review.

Panoptic labels for RGB-T pairs are expensive: every pair needs dense stuff regions *and*
instance-resolved thing masks. This work builds full-class supervision offline instead. A prompted
foundation teacher (SAM 3, thermal input) produces thing masks over an unlabeled pool, a frozen
target-domain checkpoint completes the stuff classes under a conservative confidence/purity gate,
and a compact student is trained on the result. The student keeps a frozen DINOv3 backbone and
fuses the two modalities with a reliability gate, so it handles either illumination regime in a
single RGB-T forward pass.

## Available now

- **Data archive.** Derived panoptic annotations, the frozen data-role and split manifests, the
  cross-modal integrity records and the offline pseudo-label banks:
  [10.5281/zenodo.22664863](https://doi.org/10.5281/zenodo.22664863). Source imagery is not
  redistributed and must be obtained from DroneVehicle and SemanticRT under their own terms.
- **Reproducibility tables.** [REPRODUCIBILITY.md](REPRODUCIBILITY.md) records the experimental
  configuration, the data-role counts, the nested labeled subsets, the perceptual-grouping and
  neighbour-exposure rulesets, and the corruption severity definitions.

## Coming with publication

Training, evaluation and metric unit-test code will be released here when the paper is published,
matching the Code availability statement in the manuscript. The release will carry the frozen
configuration, the pre-registered experiment protocols, the single evaluator behind every reported
table, and the pre-run integrity gates.

## Citation

```bibtex
@article{pu2026rgbtpan,
  title   = {Offline Foundation-Model Supervision for Label-Efficient
             Low-Light RGB-T Panoptic Segmentation},
  author  = {Pu, Yufan and Yi, Shi and Yang, Tianming and Wu, Huiqi and Huang, Junwei},
  year    = {2026},
  note    = {Manuscript under review}
}

@dataset{pu2026rgbtpan_data,
  title     = {RGBTPan: dual-view low-light RGB-T panoptic annotations and
               offline pseudo-label banks},
  author    = {Pu, Yufan and Yi, Shi and Yang, Tianming and Wu, Huiqi and Huang, Junwei},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.22664863}
}
```

---

# 
