# Persian-ASR

## Project Overview

This project aims to convert Persian speech into its equivalent text. evaluated the accuracy of three speech-to-text models on Persian audio data and fine-tune one model for improved performance.

## Objectives

1. Evaluate the accuracy of three speech-to-text models on Persian audio data:
   - stt_fa_fastconformer_hybrid_large
   - seamless-m4t-v2-large
   - whisper-large-v3
2. Fine-tune the stt_fa_fastconformer_hybrid_large model using a Persian speech dataset and the NEMO tool
3. Visualize the results using TensorBoard.

## Dataset

Used a Persian speech dataset sourced from YouTube for both evaluation and fine-tuning. Due to the large size of the original dataset, I created two preprocessed versions with reduced data:

1. [preprocessed_asr_youtube_farsi](https://huggingface.co/datasets/kamyar-mroadian/preprocessed_asr_youtube_farsi)
2. [preprocessed_asr_youtube_farsi_chunk_10](https://huggingface.co/datasets/kamyar-mroadian/preprocessed_asr_youtube_farsi_chunk_10)

Both datasets are preprocessed and converted to a 16000 Hz sampling rate.

Original datasets:
1. [Automatic Speech Recognition Farsi YouTube 30-Second Chunks](https://huggingface.co/datasets/pourmand1376/asr-farsi-youtube-chunked-30-seconds)
2. [Automatic Speech Recognition Farsi YouTube 10-Second Chunks](https://huggingface.co/datasets/pourmand1376/asr-farsi-youtube-chunked-10-seconds)

## Models

1. **stt_fa_fastconformer_hybrid_large**: A model specifically designed for Persian speech recognition
2. **seamless-m4t-v2-large**: A multilingual speech-to-text model
3. **whisper-large-v3**: OpenAI's large speech recognition model

## Methodology

Our approach consists of two main phases:

1. **Performance Evaluation**: assessd the initial performance of all three models on the Persian YouTube dataset.
2. **Fine-tuning**: fine-tuned the stt_fa_fastconformer_hybrid_large model using the NEMO tool to improve its performance on Persian speech recognition tasks.

## Implementation

The project is implemented using Python, leveraging libraries such as:
- Transformers
- Datasets
- Evaluate
- Torch
- TensorBoard
- NEMO

Key steps in the implementation include:
1. Data loading and preprocessing
2. Model initialization and evaluation
3. Fine-tuning process using NEMO
4. Post-fine-tuning evaluation and visualization of the process

## Evaluation Metrics

Used standard speech recognition metrics for evaluation:
- Word Error Rate (WER)
- Character Error Rate (CER)

## Visualization

Utilized TensorBoard to visualize the training process and model development:

1. **TensorBoard Integration**: Used TensorBoard to log training metrics.
2. **Metrics Tracked**: 
   - Training loss
   - Learning rate
   - Epoch progress
   - WER
   - etc.
3. **Visualization Process**:
   - TensorBoard logs are saved during the training process
   - To view the logs, run TensorBoard in the terminal:
     ```
     tensorboard --logdir ./logs
     ```
   - Access the TensorBoard interface in your web browser to see real-time training progress and performance metrics.

## Results

The notebook includes detailed results of the evaluation process, comparing the performance of both models before and after fine-tuning. The results are presented in terms of exact match scores, F1 scores, and similarity scores.

Here's a berief result acheived before fine-tuning:
1. **whisper-large-v3**: 
    - WER: 0.56
    - CER:  0.45
2. **seamless-m4t-v2-large**: 
    - WER: 0.64
    - CER: 0.44
3. **stt_fa_fastconformer_hybrid_large**:
    - WER: 0.74
    - CER: 0.59

Also, here's the result after finetuning **stt_fa_fastconformer_hybrid_large**:
- WER: 0.3747325742382022 
- CER: 0.19

## Usage

To replicate this project:

1. Clone the repository
2. Install the required dependencies
3. Download the preprocessed datasets from Hugging Face
4. Run the evaluation and fine-tuning scripts

## License

This project is under MIT LICENSE.