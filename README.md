# Long-non-coding-RNA Analysis

<img src="https://lmg-labmanager.s3.amazonaws.com/assets/articleNo/24747/aImg/45875/12-31-20-dna.jpg" width="1000" height="350">

## Build Prediction Model
### build.py <br>
Used to build model using the given training data
(mRNA/lncRNA transcripts)


| Option            | Description                                  |
|-------------------|----------------------------------------------|
| -p, --prediction_out | Output file name where information will be saved |
| -i, --infile       | Input sequence file                          |
| -m, --model        | Model file                                   |
| -o, --outdir       | Output directory name                        |
| -d, --db           | Path to BLAST database                       |

```bash
plncpro build -p plncpro_data/plant_new_fasta/monocot/train/monocot_pct_train.fa -n plncpro_data/plant_new_fasta/monocot/train/monocot_lnct_train.fa  -m monocot.mode -o monocot_model -d uniprot/uniprotdb 
```

## Predict lncRNA Sequences
### prediction.py <br>
To label lncRNAs and mRNAs. This file reads an input
file containing sequences and then classifies the sequences as coding or
non-coding. It outputs a file containing class label and class probabilities for each
sequence.

| Option            | Description                                  |
|-------------------|----------------------------------------------|
| -p, --pos         | mRNA sequence file                           |
| -n, --neg         | lncRNA sequence file                         |
| -m, --model       | Output model name                            |
| -o, --outdir      | Output directory name                        |
| -d                | Path to BLAST database                       |

```bash
$ plncpro predict -p predicciones.txt -i sample_data/test/test.fa -m monocot_model/monocot.model -v -r -o PLncPRO -d uniprot/uniprotdb 
```





