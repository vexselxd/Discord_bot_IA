# Discord Bot IA · Image Classifier

> A Discord bot that tells you whether an image contains a swallow or a pigeon. Computer vision, live in chat.

---

## Stack

![Python](https://img.shields.io/badge/Python-0a0a2e?style=for-the-badge&logo=python&logoColor=f5c842)
![TensorFlow](https://img.shields.io/badge/TensorFlow-0a0a2e?style=for-the-badge&logo=tensorflow&logoColor=f5c842)
![Keras](https://img.shields.io/badge/Keras-0a0a2e?style=for-the-badge&logo=keras&logoColor=f5c842)
![discord.py](https://img.shields.io/badge/discord.py-0a0a2e?style=for-the-badge&logo=discord&logoColor=f5c842)
![Teachable Machine](https://img.shields.io/badge/Teachable_Machine-0a0a2e?style=for-the-badge&logo=google&logoColor=f5c842)

---

## What it does

Send an image to the bot and it responds with a classification — swallow or pigeon — using a trained Keras model running live inside Discord.

```
User:  [uploads image]
Bot:   🐦 This looks like a swallow. (94.3% confidence)
```

---

## How it was built

### 1. Training
The model was trained using **Google Teachable Machine** — a visual tool that lets you train image classifiers by uploading example photos per class. Two classes: swallow and pigeon.

Teachable Machine handles the neural network architecture internally and exports a ready-to-use Keras model.

### 2. Export
The trained model was exported as:
- `keras_model.h5` — model weights and architecture
- `labels.txt` — class names mapped to model outputs
- `converted_keras.zip` — full export package from Teachable Machine

### 3. Discord integration
The exported model was loaded into a `discord.py` bot. When a user sends an image, the bot:
1. Downloads the image
2. Preprocesses it to match the model's input format
3. Runs inference
4. Replies with the predicted class and confidence score

The technical challenge here isn't the model — it's wiring real-time image handling inside a Discord event loop cleanly.

---

## Project structure

```
Discord_bot_IA/
├── main.py              # Discord bot + inference logic
├── model.py             # Model loading and prediction
├── keras_model.h5       # Trained model weights
├── labels.txt           # Class labels (swallow / pigeon)
└── converted_keras.zip  # Full Teachable Machine export
```

---

## What I learned

- Teachable Machine is a fast way to validate a CV idea before investing in a custom training pipeline
- The real complexity in ML bots isn't the model — it's handling image input, preprocessing, and async inference inside a bot event loop
- Exporting and deploying a Keras model outside of the training environment requires attention to input shape and normalization

---

## Author

![Portfolio](https://img.shields.io/badge/Portfolio-0a0a2e?style=for-the-badge&logoColor=f5c842&label=✦)
![GitHub](https://img.shields.io/badge/GitHub-0a0a2e?style=for-the-badge&logo=github&logoColor=f5c842)

**Christopher** · [vexsel.pythonanywhere.com](https://vexsel.pythonanywhere.com) · [github.com/vexselxd](https://github.com/vexselxd)
