# Cyber
**Steganography: Hide Messages in Images**

This project lets you **hide secret messages** inside images using a mix of **LSB (Least Significant Bit)** and **DCT (Discrete Cosine Transform)**. It’s designed to be **invisible** and **secure**, while keeping the image quality high.

**Features**
- **Hybrid Method**: Combines LSB (simple hiding) and DCT (math-based hiding) for better security.
- **Brightness Layer**: Hides data in the **brightness (Y channel)** of the image, making it hard to notice.
- **PSNR Check**: Measures image quality after hiding data.
- **Google Colab Ready**: Runs in your browser with **no setup**.

**How It Works**
1. **Hide a Message**:
   - Converts your message to binary.
   - Applies math (DCT) to the image’s brightness layer.
   - Hides the message in the **middle frequencies** of the math data.
   - Saves the new image with the hidden message.

2. **Extract a Message**:
   - Reads the hidden data from the image using the same math (DCT).
   - Converts it back to your original message.

3. **Check Quality**:
   - Compares the original and new images to ensure they look almost the same.
**Requirements**
- Python 3.x
- Libraries: `opencv-python`, `numpy`, `matplotlib`, `Pillow`
- Platform: **Google Colab** (easiest) or any Python environment.

---

**Usage**
1. **Run in Google Colab**:
   - Open the notebook.
   - Upload an image.
   - Enter your secret message.
   - The script will:
     - Hide the message.
     - Show the original and new images.
     - Extract the message and check quality.
     - Save the new image.

2. **Run Locally**:
   - Install libraries:
     ```bash
     pip install opencv-python numpy matplotlib Pillow
     ```
   - Run the script and follow the prompts.


**Example**
```python
# Hide a message
stego_image = embed_lsb_dct(cover_image, "Secret Message")

# Extract the message
extracted_message = extract_lsb_dct(stego_image)

# Check quality
psnr_value = calculate_psnr(cover_image, stego_image)
print(f"PSNR: {psnr_value:.2f} dB")
```
**Results**
- **High Quality**: The new image looks almost the same as the original.
- **Accurate Extraction**: Your message is recovered perfectly.
- **Hard to Detect**: Better than basic hiding methods.

**Future Ideas**
1. Add **encryption** for extra security.
2. Make it work on **mobile apps**.
3. Improve resistance to detection tools.
**Contributing**
Feel free to:
- Report issues.
- Suggest improvements.
- Add new features.
