# Petalcore Select

Petalcore Select is the plant-recommendation frontend for Petalcore Platform. It sends validated preferences to the shared recommendation endpoint, which ranks the current cloud-database catalog and returns match reasons.

## Data and security

- Recommendations use the current Platform plant records; this project does not maintain a separate plant catalog.
- The page loads its public Select client key from `/config/select`; it contains no database or admin credentials.
- Plant photos come from the shared Platform image endpoint, with local photos retained as a fallback.
- Record creation, updates, and deletion stay in Platform's protected admin tools.
- This project no longer carries an unused in-memory API.

## Use

Open Petalcore Platform and choose **Select**. To deploy this frontend separately, set the Vercel project root to `api/`, keep `PETALCORE_API_ORIGIN` in `api/config.js` pointed at the Platform deployment, and allow that frontend's origin in the Platform API's `ALLOWED_ORIGINS` setting.
