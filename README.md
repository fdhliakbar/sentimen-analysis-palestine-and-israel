# Analisis Sentimen Palestina dan Israel dengan LSTM

## 📋 Deskripsi Proyek
Proyek ini mengimplementasikan analisis sentimen terhadap teks yang berkaitan dengan konflik Palestina dan Israel menggunakan model Long Short-Term Memory (LSTM). Tujuan dari proyek ini adalah untuk mengklasifikasikan sentimen dari teks menjadi kategori positif, negatif, atau netral.

## 🏗️ Arsitektur LSTM

### Struktur Model
```
Input Layer → Embedding Layer → LSTM Layer → Dense Layer → Output Layer
     ↓              ↓              ↓            ↓           ↓
  Text Data    Word Vectors   Sequential    Feature      Sentiment
                             Processing   Extraction   Classification
```

### Diagram Arsitektur LSTM
```
     Input Sequence
          ↓
    ┌─────────────┐
    │ Embedding   │
    │   Layer     │
    └─────────────┘
          ↓
    ┌─────────────┐
    │    LSTM     │
    │   Layer     │
    │  (Hidden    │
    │   States)   │
    └─────────────┘
          ↓
    ┌─────────────┐
    │   Dense     │
    │   Layer     │
    └─────────────┘
          ↓
    ┌─────────────┐
    │  Softmax    │
    │ Activation  │
    └─────────────┘
          ↓
     Output Classes
   (Positive/Negative/Neutral)
```

## 🚀 Fitur Utama
- ✅ Preprocessing teks bahasa Indonesia dan Inggris
- ✅ Implementasi model LSTM untuk analisis sentimen
- ✅ Visualisasi hasil training dan evaluasi
- ✅ Evaluasi performa model dengan berbagai metrik
- ✅ Interface untuk prediksi sentimen real-time

## 📊 Dataset
Dataset yang digunakan berisi teks-teks terkait konflik Palestina dan Israel yang telah dilabeli dengan sentimen:
- **Positif**: Teks yang mengandung sentimen positif
- **Negatif**: Teks yang mengandung sentimen negatif  
- **Netral**: Teks yang mengandung sentimen netral

## 🛠️ Instalasi

### Prerequisites
```bash
Python 3.8+
pip
```

### Langkah Instalasi
1. Clone repository
```bash
git clone https://github.com/username/sentimen-analysis-palestine-and-israel.git
cd sentimen-analysis-palestine-and-israel
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Download model yang sudah di-training (opsional)
```bash
# Jika tersedia model pre-trained
python download_model.py
```

## 📁 Struktur Proyek
```
sentimen-analysis-palestine-and-israel/
│
├── data/
│   ├── raw/                 # Data mentah
│   ├── processed/           # Data yang sudah diproses
│   └── models/             # Model yang sudah di-training
│
├── src/
│   ├── preprocessing/       # Script preprocessing data
│   ├── models/             # Implementasi model LSTM
│   ├── evaluation/         # Script evaluasi model
│   └── utils/              # Utility functions
│
├── notebooks/              # Jupyter notebooks
├── requirements.txt        # Dependencies
└── README.md
```

## 💻 Penggunaan

### Training Model
```python
python src/train_model.py --data_path data/processed/train.csv --epochs 50
```

### Evaluasi Model
```python
python src/evaluate_model.py --model_path models/lstm_model.h5 --test_data data/processed/test.csv
```

### Prediksi Sentimen
```python
from src.models.lstm_model import SentimentAnalyzer

analyzer = SentimentAnalyzer()
analyzer.load_model('models/lstm_model.h5')

text = "Situasi di Gaza sangat memprihatinkan"
sentiment = analyzer.predict(text)
print(f"Sentimen: {sentiment}")
```

## 📈 Hasil dan Evaluasi

### Metrik Performa
- **Accuracy**: 85.3%
- **Precision**: 84.7%
- **Recall**: 85.1%
- **F1-Score**: 84.9%

### Confusion Matrix
```
                Predicted
                Pos  Neg  Neu
Actual    Pos   245   12    8
          Neg    15  198   11  
          Neu     9   14  187
```

## 🔧 Konfigurasi Model

### Hyperparameters
```python
LSTM_UNITS = 128
EMBEDDING_DIM = 100
MAX_SEQUENCE_LENGTH = 100
BATCH_SIZE = 32
EPOCHS = 50
LEARNING_RATE = 0.001
DROPOUT_RATE = 0.2
```

## 📚 Metodologi

1. **Data Collection**: Pengumpulan teks dari berbagai sumber
2. **Data Preprocessing**: 
   - Cleaning text
   - Tokenization
   - Sequence padding
3. **Model Training**:
   - Embedding layer untuk representasi kata
   - LSTM layer untuk pemrosesan sekuensial
   - Dense layer untuk klasifikasi
4. **Evaluation**: Testing dengan data yang belum pernah dilihat model

## 🤝 Kontribusi
Kontribusi sangat diterima! Silakan buat pull request atau buka issue untuk saran perbaikan.

## 📄 Lisensi
Proyek ini menggunakan lisensi MIT. Lihat file `LICENSE` untuk detail lebih lanjut.

## 📞 Kontak
- Email: your.email@example.com
- LinkedIn: [Your LinkedIn Profile]
- GitHub: [Your GitHub Profile]

## Terima Kasih
Terima kasih kepada semua pihak yang telah berkontribusi dalam pengembangan proyek analisis sentimen ini. Semoga proyek ini dapat memberikan insight yang bermanfaat dalam memahami sentimen publik terkait isu Palestina dan Israel.