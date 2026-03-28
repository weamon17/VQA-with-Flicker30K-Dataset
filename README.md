```markdown
# 📖 Visual Question Answering (VQA) with Flickr30k Dataset

## 📝 Introduction
This project implements and compares four different Deep Learning architectures for the **Visual Question Answering (VQA)** task using the **Flickr30k** dataset.

The system allows users to input an image and a question (in English). The models then analyze the visual and textual data to generate an appropriate answer. The project also includes a user-friendly Graphical User Interface (GUI) to easily test and compare the predictions of all four models side-by-side.

## 📂 Project Structure

* **`Task2_Flicker30kDataset.ipynb`**: The Jupyter Notebook containing the end-to-end pipeline:
    * Downloading the Flickr30k dataset (via `kagglehub`).
    * Data preprocessing (image resizing, transformations, text tokenization).
    * Automatic question generation based on available image captions.
    * Building the vocabulary and saving it to `vocab.pkl`.
    * Training and evaluating (via BLEU score) four different VQA models.
* **`Test_Models.py`**: A Desktop application (GUI) built with `Tkinter`. This script allows you to:
    * Upload an image from your local machine.
    * Enter a text-based question.
    * Use the trained models to predict answers and display a visual comparison.

## 🧠 Implemented Models
The project builds and evaluates four model variants to demonstrate the impact of Transfer Learning and Attention mechanisms:
1.  **Model 1 (Base Model)**: Trained from scratch using a custom CNN Encoder and an LSTM Decoder.
2.  **Model 2 (CNN + LSTM + Attention)**: Adds an Attention mechanism to help the model focus on relevant regions of the image when generating the answer.
3.  **Model 3 (Transfer Learning)**: Uses a pre-trained **ResNet50** model as the image feature extractor (Encoder) combined with an LSTM Decoder.
4.  **Model 4 (ResNet50 + Attention)**: The most advanced variant, combining the powerful ResNet50 feature extractor with an Attention mechanism to optimize accuracy.

## ⚙️ Requirements
Ensure you have the following Python libraries installed before running the code:

```bash
pip install torch torchvision pandas numpy pillow nltk tqdm matplotlib kagglehub datasets
```
*(Note: The `tkinter` library is usually included by default with standard Python installations).*

## 🚀 How to Use

### 1. Training the Models
1. Run the code blocks sequentially in the `Task2_Flicker30kDataset.ipynb` notebook.
2. This process will create and save the vocabulary to a `vocab.pkl` file.
3. The model weight files (`.pth`) will be generated after training is complete (e.g., `best_model_base.pth`, etc.).
4. *Recommendation: Run the notebook in an environment with GPU support (like Google Colab or a local machine with an NVIDIA GPU) to significantly speed up training.*

### 2. Testing with the GUI (Inference)
1. Ensure that the `vocab.pkl` file and the trained weight files (`.pth`) from Step 1 are placed in the same directory as `Test_Models.py`.
2. Run the GUI application using the following command:
   ```bash
   python Test_Models.py
   ```
3. On the interface:
   * Click the button to select an image.
   * Enter your question (e.g., *"what is the man doing"*, *"how many people are there"*).
   * The system will display the predictions from all 4 models simultaneously so you can evaluate their performance.

## 👤 Author
* **[Your Name]** - *Main Developer* - [GitHub Profile Link]
* Feel free to reach out at [Your Email Address] for any questions or collaborations!

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. (If you don't have a LICENSE file yet, the MIT license basically allows anyone to use, modify, and distribute your code as long as they give you credit).
```