# LSTM-Machine-Translation
LSTM-based translation model for translating English sentences into French. 
It includes:
- Custom PyTorch Dataset and DataLoader
- Tokenization and vocabulary creation
- Many-to-many LSTM sequence prediction
- Translation inference

## Dataset
We use the Opus Books dataset from Hugging Face, which provides aligned bilingual data.
Split Used: 25% of dataset was used for training
Source Language: English (en)
Target Language: French (fr)

## Model Architecture
A simple many-to-many LSTM model is used (no encoder-decoder split).

Model Components:
- Embedding: Word embeddings (128-dimensional)
- LSTM: Single-layer LSTM with hidden size of 256
- Dropout: 20% dropout
- Linear: Fully connected layer for token prediction

## Training
- Loss Function: CrossEntropyLoss
- Optimizer: Adam
- Batch Size: 64
- Epochs: 100
- Device: CUDA

## Inference/Translation
Translation is performed by feeding an English sentence through the model and decoding the most likely token at each step.
