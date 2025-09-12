## Repository Structure

eeg-ad-ftd-classification/
│
├── README.md
├── requirements.txt
│
├── data/
│ ├── raw/ # chứa file .set gốc (88 subjects)
│ ├── processed_png/ # chứa ảnh spectrogram sau khi preprocessing
│ └── processed_npy/ # (optional) lưu tensor dạng npy
│
├── preprocessing/
│ ├── preprocess_eeg.py # script chính: segmentation + spectrogram
│ └── utils.py # hàm phụ trợ (ví dụ: spectrogram, save file)
│
├── training/
│ ├── train_cnn.py # huấn luyện CNN cơ bản
│ ├── train_resnet.py # huấn luyện ResNet
│ ├── train_transformer.py # (option) thử transformer
│ └── dataset_loader.py # class PyTorch Dataset để load PNG/Numpy
│
├── models/
│ ├── cnn.py # định nghĩa CNN
│ ├── resnet.py # ResNet backbone
│ └── transformer.py # Vision Transformer hoặc EEG-Transformer
│
└── notebooks/
├── eda.ipynb # EDA, visualization dữ liệu EEG
├── spectrogram_demo.ipynb # thử convert 1 file → spectrogram
└── training_demo.ipynb # chạy thử train model nhỏ

### Notes
- **data/**: tổ chức theo 3 mức — dữ liệu gốc, dữ liệu ảnh (spectrogram), dữ liệu tensor.  
- **preprocessing/**: xử lý EEG thô → spectrogram.  
- **training/**: chứa script huấn luyện theo từng kiến trúc (CNN, ResNet, Transformer).  
- **models/**: định nghĩa kiến trúc mạng.  
- **experiments/**: tách riêng log, checkpoint, config để tiện quản lý.  
- **notebooks/**: dùng để EDA, demo pipeline, visualization.  