# IndoTTS-Book
you can access the dataset here: https://s.itk.ac.id/audiobooks

## Overview
This dataset is designed for training Text-to-Speech (TTS) models, specifically for the Indonesian language. It is derived from a publicly available audiobook titled *Sejarah Dunia yang Disembunyikan* (The Secret History of the World) by Jonathan Black, narrated by Rahman Trahira. The audiobook was processed into a custom Indonesian speech corpus, structured similarly to the LJSpeech dataset. This dataset supports the development of high-quality TTS models for Indonesian, using architectures like Tacotron 2 and HiFi-GAN.

The source material was processed into 2,087 utterances, with durations ranging from 0.40 to 10.10 seconds, and an average duration of 4.28 seconds. The total audio duration is 8,936 seconds. The audio was preprocessed, including downsampling from 44.1 kHz to 22.05 kHz, converting stereo to mono, and applying dereverberation using FFmpeg to minimize echo artifacts. Segmentation was performed automatically based on silence thresholds, and each segment was transcribed using Whisper to avoid timestamp drift. Metadata was formatted to match the LJSpeech standard.

## Dataset Structure
The dataset is organized as follows:
/IndoTTS-Book
   metadata.csv
   /Speech
   - BOOK003-0001.wav
   - BOOK003-0002.wav
   - ...

**metadata.csv**: Contains the mappings between audio files and their corresponding text transcriptions, including phonetic transcriptions for TTS model training.
**/Speech**: Contains the segmented `.wav` files (mono, 22.05 kHz sample rate) representing the utterances from the audiobook. Each file is named according to the structure `BOOK003-xxxx.wav`, where `BOOK003` corresponds to the audiobook ID and `xxxx` denotes the segment number.

### Metadata Format (`metadata.csv`)
The `metadata.csv` file consists of the following columns:
1. **Audio File Name**: The name of the audio file (e.g., `BOOK003-0001.wav`).
2. **Original Text**: The transcription of the audio in Indonesian.
3. **Phonetic Text**: A phonetic transcription of the Original Text.

Example:\
BOOK003-0001|Sejarah dunia yang disembunyikan|Sejarah dunia yang disembunyikan\
BOOK003-0002|Karya buku Jonathan Black|Karya buku Jonathan Black\
BOOK003-0003|bab 25|bab dua puluh lima


## Acknowledgements
The dataset is based on the audiobook "Sejarah Dunia yang Disembunyikan" (The Secret History of the World by Jonathan Black), narrated by Rahman Trahira.

Transcriptions were generated using Whisper ASR and further refined by the dataset creators.

## License
This dataset is provided for research purposes only. Redistribution or commercial use without explicit permission is prohibited.
