# NeuroScan AI – Brain Tumor MRI Classifier

Streamlit app (custom HTML/CSS styling) that classifies brain MRI slices into
**Glioma, Meningioma, Pituitary tumor, No tumor** using a **pretrained model **
–

Model: [`the-shoaib2/Brain_Tumor_MRI_Classification`](https://huggingface.co/the-shoaib2/Brain_Tumor_MRI_Classification)
(Xception, Keras; its model card reports ~97.9% validation accuracy).

## Run
```bash
pip install -r requirements.txt
streamlit run app.py
```
On first run the model is downloaded from Hugging Face and cached; later runs are fast.
Then upload an MRI image (JPG/PNG), view the prediction and click **Download PDF report**.

## If the model fails to load
- The model page may be gated. Log in to Hugging Face, open the model page and accept the terms, create a
  *read* access token (Settings → Access Tokens), and paste it into the sidebar field
  (or set `HF_TOKEN` before running).
- Use another compatible 4-class Keras model by changing the **Hugging Face model ID** in the sidebar
  (or set `MODEL_REPO`). Class order must be: glioma, meningioma, notumor, pituitary.

## Files
- `app.py` – UI, inference, PDF generation
- `requirements.txt`

## Disclaimer
Research/educational prototype. Not a medical device; outputs must be reviewed by a qualified clinician.
