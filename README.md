# Syllable Structure in Andic Languages

Course paper (HSE University, 2024) on how syllable structure changes across eight closely related Andic languages of the Nakh-Daghestanian family: Karata, Botlikh, Akhvakh, Ghodoberi, Andi, Chamalal, Tindi and Bagvalal.

The idea is simple. If we find words that come from a common ancestor (cognates) and compare how they are syllabified in each language, we can see which syllable patterns turn into which, and which languages behave alike.

## Pipeline

1. **Data preparation** (`dataprep_lexstat.ipynb`)
   Starting point is the [Comparative Andic Dictionary Database](https://github.com/phon-dicts-project/comparative_andic_dictionary_database). I cleaned the transcriptions, reviewed part of the entries by hand (`to_edit_andic_dicts.csv`) and converted the data to the LingPy input format (`4ls.qlc`).
2. **Cognate detection** (`dataprep_lexstat.ipynb`)
   Automatic cognate detection with LexStat from [LingPy](https://lingpy.org). Output: `res_ls.qlc`, merged into `grouped_data.csv`.
3. **Syllable analysis** (`data_analyse.ipynb`)
   Every word is converted to a CV skeleton (for example `bekːʷ'aɬa` → `CVCVCV`). Then I compare syllable structures within each language and across cognate pairs, with a separate look at changes at the beginning and at the end of the word.

## Files

| File | What it is |
|---|---|
| `dataprep_lexstat.ipynb` | Data cleaning and LexStat cognate detection |
| `data_analyse.ipynb` | Syllable structure analysis and pairwise language comparison |
| `andic_dicts.csv.zip` | Source dictionary data |
| `to_edit_andic_dicts.csv.zip` / `edited_andic_dicts.csv.zip` | Manually reviewed and cleaned data |
| `4ls.qlc`, `res_ls.qlc` | LexStat input and output |
| `grouped_data.csv` | Concepts with cognates and CV skeletons for all eight languages |
| `pairwise_comparison.csv` | Pairwise comparison of cognates |
| `beg_change.csv.zip`, `end_change.csv.zip` | Syllable changes at the beginning and at the end of the word |
| `appendix/` | Figures from the paper |

## How to run

```bash
pip install lingpy pandas numpy matplotlib jupyter
unzip "*.zip"
jupyter notebook dataprep_lexstat.ipynb   # then data_analyse.ipynb
```

## Tools

Python, pandas, NumPy, Matplotlib, LingPy (LexStat).

## Related work

This paper grew out of my work on the Typological Atlas of the Languages of Daghestan, where I studied how the hortative is expressed across Nakh-Daghestanian languages.
