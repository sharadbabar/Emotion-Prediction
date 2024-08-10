# Emotion-Prediction

A text emotion classification project using a bidirectional GRU, a FastAPI backend, and the Moodline web interface. It predicts six labels: sadness, joy, love, anger, fear, and surprise.

## Project history

The project owner reports that original development began in 2023. This repository republishes a later snapshot that includes updates and model artifacts from 2026. The repository was republished on October 8, 2026. At the owner's request, its initial commit uses a reconstructed author and committer date of August 10, 2024. That date is not an original development timestamp for the published files.

## Contents

- `main.py`: FastAPI application and inference endpoints.
- `static/`: HTML, CSS, and JavaScript for the Moodline interface.
- `final_clean.ipynb`: training notebook comparing RNN, LSTM, GRU, and bidirectional GRU models. Saved execution outputs have been cleared.
- `Artifacts/BiGRU_Model.keras`: serialized trained model.
- `Artifacts/tokenizer.pkl`: serialized text tokenizer.
- `requirements.txt` and `runtime.txt`: the supplied application dependency pins and Python runtime specification.

## Run locally

Use Python 3.11 and run commands from the repository root so the application can find its model and static files.

```bash
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m uvicorn main:app --reload
```

Open <http://127.0.0.1:8000> for the interface or <http://127.0.0.1:8000/docs> for the API documentation.

The supplied runtime is Python 3.11.9. TensorFlow package availability depends on the operating system and processor. The bundled model records Keras 3.13.2 as its export version. Dependency pins are retained from the supplied snapshot; end-to-end inference has not been verified as part of republication.

## API

- `GET /`: web interface.
- `GET /health`: server and model loading status.
- `POST /predict`: predicts an emotion for a JSON body such as `{"text": "I feel happy today"}`. Input is limited to 2,000 characters and model sequences to 50 tokens.

The response includes `predicted_emotion`, `confidence`, and `all_probabilites` (the spelling used by the supplied API). Confidence is a model score, not a guarantee of the writer's emotional state.

## Training

The notebook needs additional packages: `datasets`, `pandas`, `seaborn`, `matplotlib`, and `scikit-learn`. These are separate from the API dependency list. Training downloads the external dataset rather than bundling it here.

The notebook currently exports its model as `Artifacts/BiGRU_Modle.keras`. To use a newly trained model with the supplied API, rename that file to `Artifacts/BiGRU_Model.keras`.

## Dataset and third-party material

Training uses the [DAIR.AI emotion dataset](https://huggingface.co/datasets/dair-ai/emotion). Its maintainers specify educational and research use and request citation of the associated paper. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for the citation and upstream links.

The original snapshot contains no project license. This republication does not add a new license or change third-party terms. External libraries and remotely loaded fonts retain their respective upstream terms.
