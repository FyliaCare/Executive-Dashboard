# Intertek Geronimo — Executive Insights (Streamlit)

This package contains a rewritten single-file Streamlit dashboard with improvements you requested:
- Deleting a client will also delete related action points (explicit deletion implemented).
- Ticking a task's checkbox marks it as **Done** and the task vanishes from the dashboard.
- Demo (seed) data is optional and controlled via the sidebar checkboxes.
- Includes export tools (CSV / Excel), snapshots, and the visual suite (KPIs, weekly progression, sector histogram, 3D radar, map, funnel).

## Files
- `app_executive_insights_full.py` — main Streamlit app.
- `requirements.txt` — suggested Python packages.
- `README.md` — this file.

## Quick start
1. Create a Python environment and install dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate   # or venv\\Scripts\\activate on Windows
   pip install -r requirements.txt
   ```

2. Run app:
   ```bash
   streamlit run app_executive_insights_full.py
   ```

3. In the app sidebar you'll find **Data & DB** controls. Use the **Seed demo data (only if DB empty)** toggle to insert demo data. Use **Force seed demo data** only for demonstrations (destructive).

## Notes & design choices
- The app uses a local SQLite database (default `crm_actions.db`) in the current working directory. You can set `CRM_DB` environment variable to another path.
- The app avoids force-seeding demo data unless you explicitly ask for it in the sidebar.
- Deletion of clients explicitly removes related action points to guarantee they are removed immediately.
- Ticking a task triggers an update and the dashboard refreshes so the item vanishes from the view.

## For the presentation
- If you want a pristine demo experience for tomorrow, toggle **Force seed demo data (CLEAR DB & seed)** and confirm (this will drop existing tables and recreate a seeded demo dataset).
- If you need me to prepare slides, a screenshot set, or export sample CSV/Excel snapshots included in the zip, tell me which snapshots you want and I will include them.