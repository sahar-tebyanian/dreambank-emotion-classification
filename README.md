# dreambank-emotion-classification
# Emotion Classification in DreamBank Dream Reports

Code for the paper "Compatibility, Not Confirmation: What Emotion Patterns
in 27,952 DreamBank Reports Can and Cannot Tell Us About Dream Theories."

## What this does
Classifies the dominant Hall and Van de Castle (HVDC) emotion code in
dream reports using TF-IDF features and a linear SVM, evaluated with
five-fold cross-validation grouped by dreamer, with two baseline
classifiers for comparison.

## Data
Reports come from DreamBank (https://dreams.ucsc.edu). The data file is
not included here. Download it from the source, save it as `train.csv`
in the same folder as the notebook, and check DreamBank's terms of use.
Expected columns: id, name, number, time, date, gender, age, report,
character, emotion (27,952 rows).

## How to run this 
1. Install packages: `pip install -r requirements.txt`
2. Put `train.csv` next to the notebook.
3. Open `dreambank_article_v2.ipynb` and run all cells.

## Main results (dreamer-grouped 5-fold CV, 11,808 coded reports)
| Model | Macro F1 |
|---|---|
| Linear SVM | 0.640 ± 0.018 |
| Most-frequent baseline | 0.103 |
| Stratified baseline | 0.196 |

Random seed: 42.

## Limitations
Only the first-listed emotion code per report is used. The data come
from 72 dreamers, and the largest series is 17% of coded reports.

## License
MIT
