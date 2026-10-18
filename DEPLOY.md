# Génie Civil Pro: deployment guide

## A. Test on your PC (10 min)
1. Install Python 3.11 or 3.12 (python.org). On Windows tick "Add Python to PATH".
2. Open a terminal in this folder, then:
   ```
   python -m venv venv
   venv\Scripts\activate        (Mac/Linux: source venv/bin/activate)
   pip install -r requirements.txt
   streamlit run app.py
   ```
3. Click through every section. With no passwords set the app is open (local use only).

## B. Free database (so data is not lost)
Create a free Postgres on Neon or Supabase and copy the connection string.
Without it, the app uses a SQLite file that free hosts erase on restart.

## C. GitHub
Create a PRIVATE repo, upload this folder (the .gitignore keeps secrets and .db files out).

## D. Streamlit Community Cloud
1. share.streamlit.io > New app > pick the repo, branch main, main file `app.py`.
2. Advanced settings > Secrets: paste the contents of `.streamlit/secrets.toml.example`
   with REAL passwords and your DATABASE_URL.
3. Deploy. First launch takes a few minutes.

## E. Check and hand over
- Open the URL, log in with ADMIN_PASSWORD, add a site and an expense, export a PDF.
- Reboot the app from the dashboard and confirm the data is still there.
- Give your friend the URL and the three passwords; add him as GitHub collaborator.
- Free apps sleep after inactivity; check current free-tier limits.
