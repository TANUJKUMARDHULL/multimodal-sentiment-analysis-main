# Deploying to Streamlit Community Cloud

Recommended and safe steps to deploy this project to Streamlit Community Cloud:

1. Remove any secrets from the repository. We removed `.env` from version control — keep local copies only.

2. Set sensitive values as Streamlit Secrets (recommended):

   - Visit https://share.streamlit.io and log in.
   - Click **New app** → Select GitHub repository `TANUJKUMARDHULL/multimodal-sentiment-analysis-main` → Branch `master` → `app.py` as the main file.
   - In the app's settings page, open **Secrets** and add the following keys:

     - `VISION_MODEL_DRIVE_ID` = your Google Drive vision model file ID
     - `AUDIO_MODEL_DRIVE_ID` = your Google Drive audio model file ID
     - `VISION_MODEL_FILENAME` = resnet50_model.pth
     - `AUDIO_MODEL_FILENAME` = wav2vec2_model.pth

   Streamlit will expose these via `st.secrets` at runtime.

3. Use `requirements.txt` (already present) to ensure packages are installed by Streamlit Cloud.

4. After creating the app, click **Deploy**. The app will build and start; logs are visible in the Streamlit Cloud dashboard.

Notes:
- Avoid committing real secret values to the repo. Use `st.secrets` (Streamlit) or GitHub Secrets for CI.
- If you want, I can open the Streamlit app creation page for you or walk through the exact steps in the web UI.