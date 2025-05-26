# Image-Reconstruction-With-VIT

**Project Description**


This project explores Vision Transformers (ViT) for masked image modeling, inspired by masked language modeling in NLP. The key idea is to divide an image into small patches (e.g., 16x16 pixels) and treat these patches as a sequence of tokens, similar to how words are handled in NLP models. These patch tokens are then processed using a Transformer model to learn image representations.

The masking strategy involves hiding a portion of the image patches (e.g., 50%) and training the model to reconstruct the missing patches using only the visible ones. This reconstruction task is similar to that of autoencoders but with a crucial difference: instead of compressing the image into a continuous latent space, the model predicts missing patches solely based on contextual information from the visible patches.

**Methodology**

1. **Image Patch Extraction:**  The image is split into a grid of fixed-size patches. Each patch is then flattened and projected into a one-dimensional embedding space.

2. **Positional Encoding and Masking:** Positional embeddings are added to retain spatial information. Then, a subset of the patches is masked (replaced with a special token). Several masking strategies are applied, including: Random masking, Line-wise masking, Column-wise masking, Importance-based masking

3. **Transformer Processing**: The sequence of visible and masked patch embeddings is passed through a Transformer model. The model learns contextual relationships to infer the missing patches.

4. **Patch Reconstruction:** The model generates predictions for the masked patches based on the information from visible patches.

5. **Evaluation:** Using metrics such as SSIM (Structural Similarity Index), MSE (Mean Squared Error), Visualization: side-by-side comparison of original, masked, and reconstructed images.

6. **Experiments:** Test different masking ratios (30%, 50%, 70%), Compare performance with a classical autoencoder as a baseline (done in class)
