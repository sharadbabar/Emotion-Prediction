# Third-party notices

## Emotion training dataset

The training notebook uses `dair-ai/emotion`, a dataset of English text labeled with six emotions. The dataset is downloaded during training; raw dataset files are not bundled in this repository. The model and tokenizer are training artifacts.

The dataset maintainers state that the dataset is for educational and research use and ask users to cite the associated paper. This repository does not grant broader rights to that dataset or assert that trained artifacts have a separate unrestricted license.

- [Dataset card and licensing information](https://huggingface.co/datasets/dair-ai/emotion/blob/main/README.md)
- [Dataset maintainers' usage instructions](https://github.com/dair-ai/emotion_dataset#usage)
- [Associated paper](https://aclanthology.org/D18-1404/)

Citation: Elvis Saravia, Hsien-Chi Toby Liu, Yen-Hao Huang, Junlin Wu, and Yi-Shin Chen. 2018. *CARER: Contextualized Affect Representations for Emotion Recognition*. Proceedings of the 2018 Conference on Empirical Methods in Natural Language Processing, pages 3687–3697. DOI: 10.18653/v1/D18-1404.

## Software dependencies and fonts

The application imports TensorFlow/Keras, FastAPI, Pydantic, NumPy, and Python standard-library modules. The training notebook additionally imports Hugging Face Datasets, pandas, seaborn, Matplotlib, and scikit-learn. Library source code is not vendored here; installed dependencies retain their upstream licenses and notices.

The web interface requests Fraunces, Space Grotesk, and JetBrains Mono from Google Fonts. Font files are not bundled in this repository. Their upstream terms remain applicable.

## Project licensing

No project license file or copyright notice was present in the inspected snapshot. No new project license has been selected for this republication.
