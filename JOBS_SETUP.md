# Oak Rise Point Jobs System Setup

This system is separate from the existing candidate, employer, and contact forms.

## Files

- `JobsCode.gs` — new Google Apps Script service for client leads, public jobs, and job applications.
- `JobsAdmin.html` — private recruiting dashboard available only through the private deployment.
- `jobs.html` — public Jobs page for `oakrisepoint.net`.

## Setup sequence

1. Create a new standalone Google Apps Script project while signed in to the Oak Rise Point Google account.
2. Replace `Code.gs` with the contents of `JobsCode.gs`.
3. Add a new HTML file named exactly `JobsAdmin` and paste the contents of `JobsAdmin.html`.
4. Run `setupJobsSystem` once and approve access. The function creates:
   - `Oak Rise Point Jobs System` spreadsheet;
   - `Oak Rise Point Job Applications - Resumes` Drive folder;
   - three separate sheets: Client Leads, Public Jobs, and Job Applications.
5. Create a private web-app deployment:
   - Execute as: Me
   - Who has access: Only myself
   - Open its URL with `?view=admin` for the private dashboard.
6. Create a second public web-app deployment:
   - Execute as: Me
   - Who has access: Anyone
   - Copy its `/exec` URL.
7. In `jobs.html`, replace `REPLACE_WITH_NEW_JOBS_WEB_APP_URL` with the public `/exec` URL.
8. Upload `jobs.html` and the updated `index.html` to the Oak Rise Point GitHub repository.

Do not replace or edit the existing Oak Rise Point forms script. This jobs system has its own script and storage.
