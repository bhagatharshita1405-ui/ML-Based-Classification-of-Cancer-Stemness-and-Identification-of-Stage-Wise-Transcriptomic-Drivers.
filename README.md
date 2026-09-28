# ML-Based-Classification-of-Cancer-Stemness-and-Identification-of-Stage-Wise-Transcriptomic-Drivers.
This project consists of stage-wise transcriptomic analysis of TCGA-COAD data using mRNAsi Scoring and ML algorithms.
Stage-Wise Transcriptomic Analysis of Cancer Stem Cell Identity in Colorectal Adenocarcinoma
ML-based classification of cancer stemness and identification of stage-wise transcriptomic drivers (TCGA-COAD)

Overview
This project integrates TCGA-COAD RNA-seq data with pre-computed mRNAsi stemness scores (Malta et al., 2018) to study how cancer stem cell-like features change across AJCC stages I-IV. It combines stage-wise differential expression, GSEA, stemness integration, machine learning (Random Forest, XGBoost + SHAP), proliferation (MKI67) validation, survival, tumour microenvironment and drug-sensitivity analyses.

Key results
Finding	Value
Cohort	445 primary tumours, 19,962 protein-coding genes (428 matched to mRNAsi)
Trend DEGs / pairwise DEGs / high-confidence	
1,009 / 134 / 126
Top GSEA pathways	
IFN-gamma response down (NES -2.92), EMT up (NES +2.57)
mRNAsi vs stage	Spearman rho = -0.133, p = 0.006
Triple-overlap genes:	CRYAB, BMERB1, SHISA4
XGBoost / Random Forest test
AUC	0.988 / 0.947 
(benchmark: 0.659, Gao et al. 2022)
Top SHAP driver:	CDC6
mRNAsi variance independent of MKI67	93.6%
Pipeline
Module	Description	Language	Script
1	Data acquisition & preprocessing
2	Stage-wise DEA + GSEA	R	
3	mRNAsi scoring & MKI67 extraction	
4	DEG x stemness integration	
5	ML classification + SHAP	Python	
5b	MKI67 proliferation validation	

```
Notes and limitations
PanCanStem OCLR weights were unavailable, so a correlation-based 500-gene proxy stemness signature was used.
Drug sensitivity uses a literature-based gene-correlation proxy (GDSC2/oncoPredict unavailable).
mRNAsi was not an independent prognostic factor once AJCC stage and age were included.
References
Malta et al., 2018 (mRNAsi); Gao et al., 2022; Ji et al., 2022. See `docs/` for the full reference set.
License
Add a license (e.g. MIT) after checking with your supervisor/institution.
