# Data

This folder contains the training dataset and generated model used for the GOR IV secondary structure prediction pipeline.

---

## Files

| File | Description |
|---|---|
| `pc25_train_set.db` | Protein dataset used for model training |
| `gor4_model_cull.txt` | Trained GOR IV model generated from the dataset |

---

## Dataset Information

The training dataset was generated using the PISCES protein sequence culling server with a maximum sequence identity threshold of 25% to reduce redundancy between proteins.

### Dataset Statistics

| Metric | Value |
|---|---|
| Proteins | 5720 |
| Residues | 1,324,683 |
| Minimum Length | 6 |
| Maximum Length | 1298 |
| Mean Length | 231.59 |
| Median Length | 197.00 |
| Helix Residues (H) | 490,566 (37.03%) |
| Sheet Residues (E) | 315,295 (23.80%) |
| Coil Residues (C) | 518,822 (39.17%) |

---

## Training Command

The model was generated using:

```bash
java -jar gor4.jar --db data/pc25_train_set.db --method gor4 --model data/gor4_model_cull.txt
```

---

## Dataset Format

The dataset follows a Seclib-style format:

```text
>protein_id
AS AMINOACIDSEQUENCE
SS SECONDARYSTRUCTURE
```

Example:

```text
>1ABC
AS MVLSPADKTNVKAAWGKVGAHAGEYGAEALERMF
SS CCCCCCHHHHHHHHHHHCCCCCCEEEECCCCCCC
```
