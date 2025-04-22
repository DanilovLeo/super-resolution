Comparison analysis of super-resolution methods (SD, SDXL, Real-ESRGAN)
Project Description
This repository consists of a research project, focused on comparative analysis of effectiveness of various approaches to the problem of super-resolution of images with accent on processing both pictures with text and without. 

In the research thrree contemporary models are used:

Stable Diffusion (SD)
Stable Diffusion XL (SDXL)
Real-ESRGAN

Repository Structure
├── data/                      # data
│   ├── images_no_text/        # Images without text elements 
│   ├── images_with_text/      # Images with text elements
│   └── enhanced_gan_text/     # Output images of the real-ESRGAN model with text
|   └── enhanced_gan_no_text/  # Output images of the real-ESRGAN model without text
│   └── enhanced_sd/           # Output images of the SD model (all)
|   └── enhanced_sdxl_text/      # Output images of the SDXL model (with text)
|   └── enhanced_sdxl_no_text/   # Output images of the SDXL model (no text)
|
├── notebooks/                # Jupyter notebooks
│   ├── sdxl.ipynb            # SDXL
│   ├── real_esrgan.ipynb     # Real-ESRGAN
│   └── sd.ipynb              # Basic SD
│
├── results/                   # Результаты экспериментов
│   ├── metrics/               # Количественные метрики
│   └── visual_samples/        # Визуальные примеры результатов
│
├── src/                       # Исходный код
│   ├── models/                # Настройки и адаптации моделей
│   ├── preprocessing/         # Скрипты предобработки данных
│   ├── evaluation/            # Код для оценки результатов
│   └── utils/                 # Вспомогательные функции
│
├── thesis/                    # Материалы дипломной работы
│   ├── text/                  # Текст дипломной работы
│   └── presentation/          # Презентация
│
├── requirements.txt           # Зависимости проекта
├── setup.py                   # Скрипт установки
└── README.md                  # Этот файл

Downloading and settings

Requirements:
Python 3.8+
CUDA-compatible gpu with no less than 8GB
PyTorch 1.9+
Diffusers
OpenAI API key (optional)

Settings:

Clone the repository:

bashgit clone https://github.com/username/image-superresolution-comparison.git
cd image-superresolution-comparison

Download dependencies:

bashpip install -r requirements.txt

Set the paths to models and data:

bash # Create necessary directories
mkdir -p data/images_no_text data/images_with_text results/metrics results/visual_samples

Usage

Data preprocessing
bashpython src/preprocessing/prepare_data.py --input-dir /path/to/raw/images --output-dir data/

Запуск экспериментов
Stable Diffusion XL
bashpython src/models/run_sdxl.py --data-dir data/ --output-dir results/
Real-ESRGAN
bashpython src/models/run_esrgan.py --data-dir data/ --output-dir results/
Оценка результатов
bashpython src/evaluation/calculate_metrics.py --results-dir results/ --metrics psnr ssim lpips

