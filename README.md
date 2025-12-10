# Voice Conversion GAN Project

This project implements a voice conversion GAN that converts a person's voice (Speaker A) to another person's voice (Speaker B) using a pretrained HiFi-GAN model. The project is structured to facilitate training, inference, and evaluation of the voice conversion process.

## Project Structure

```
voice-conversion-gan
├── data
│   ├── speaker_A
│   │   └── train
│   │       └── (WAV files for speaker A)
│   ├── speaker_B
│   │   └── train
│   │       └── (WAV files for speaker B)
│   └── validation
│       ├── speaker_A
│       └── speaker_B
├── notebooks
│   └── cvd-hifigan-ok.ipynb
├── src
│   ├── app.ts
│   ├── models
│   │   └── index.ts
│   ├── pipelines
│   │   └── index.ts
│   └── types
│       └── index.ts
├── scripts
│   ├── preprocess.py
│   ├── train_gan.py
│   └── infer.py
├── configs
│   ├── hifigan_config.json
│   └── gan_config.json
├── hifi-gan
│   ├── generator_v1
│   └── config_v1.json
├── package.json
├── tsconfig.json
└── README.md
```

## Setup Instructions

1. **Clone the Repository**: 
   Clone this repository to your local machine.

   ```bash
   git clone <repository-url>
   cd voice-conversion-gan
   ```

2. **Install Dependencies**: 
   Install the required Python packages for the project. You can use a virtual environment for better package management.

   ```bash
   pip install -r requirements.txt
   ```

3. **Prepare Data**: 
   Place the WAV audio files for Speaker A in `data/speaker_A/train` and for Speaker B in `data/speaker_B/train`. Ensure that the validation audio files are placed in the appropriate directories under `data/validation`.

4. **Run Preprocessing**: 
   Use the `preprocess.py` script to preprocess the audio files. This step includes normalization and conversion to the required format for training the GAN.

   ```bash
   python scripts/preprocess.py
   ```

5. **Train the GAN**: 
   Execute the training script to train the GAN model using the audio data from both speakers.

   ```bash
   python scripts/train_gan.py
   ```

6. **Inference**: 
   After training, you can use the `infer.py` script to convert audio from Speaker A to Speaker B's voice.

   ```bash
   python scripts/infer.py --input <path_to_input_audio> --output <path_to_output_audio>
   ```

## Usage

- The Jupyter notebook `notebooks/cvd-hifigan-ok.ipynb` provides an interactive environment to visualize the training process, evaluate the model, and listen to the converted audio samples.
- The `src/app.ts` file serves as the entry point for the application, initializing the necessary components for training and inference.

## Examples

- Example audio files for both speakers can be found in the respective `train` directories.
- The validation directory contains audio files for testing the model's performance after training.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.# VoiceGanAB
