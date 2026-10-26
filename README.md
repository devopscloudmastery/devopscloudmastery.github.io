# DevOps Learning Hub — GitHub Pages LMS

A static, responsive LMS starter for **4 Docker lessons**. Includes landing page, course catalogue, lesson notes, quiz scoring, interview Q&A, assignments, and browser-local progress. No build tools required.

## Deploy to GitHub Pages

1. Create a GitHub repository (for example `devops-lms`).
2. Upload **the contents of this folder** to the repository root (index.html must be in the root).
3. In GitHub: **Settings → Pages → Build and deployment → Deploy from a branch**.
4. Select `main` and `/ (root)`; save.
5. Open `https://YOUR_USERNAME.github.io/devops-lms/` after deployment. If your repository is named `YOUR_USERNAME.github.io`, the URL is `https://YOUR_USERNAME.github.io/`.

## Add Google Drive videos

Edit `data/lessons.json` and set `videoUrl` for each lesson. Example: `https://drive.google.com/file/d/FILE_ID/view`. The LMS embeds the Google Drive preview player for standard file URLs. **Google Drive permissions still control who can watch.** Test with a student account; embedding may be limited by file type, account restrictions, or browser settings. Do not put confidential recordings or secrets into this public repository.

## Add lessons

Add another object to `data/lessons.json` with a unique `id` and all the existing fields. The course list and sidebar update automatically. Add more courses later by extending the data and course navigation.

## Local preview

Run `python -m http.server 8000` in this folder and open `http://localhost:8000`. Opening HTML via `file://` may block JSON loading.

## Important limitations

- GitHub Pages is public static hosting. It cannot enforce login, payment, or protect course notes/quiz answers.
- Video access can be limited by Google Drive sharing permissions, but the HTML/JSON source remains public.
- Quiz scores are shown in the current session only; completion and assignment checkboxes use browser localStorage, which is not synchronized between devices and is not a verified student record.
- Sample passwords in the WordPress/MySQL lab are for disposable training environments only. Use proper secret management in production.
- Quiz questions: 5 per lesson in this starter release (20 total). The approved lesson drafts can later be expanded to 10–15 each.

## Google Drive lesson recordings

All four Docker lessons have their supplied Google Drive recording URLs in `data/lessons.json` under `videoUrl`. The lesson page embeds `/preview` and offers an **Open recording in Google Drive** link if embedding is restricted. Students must be explicitly granted access to each recording in Google Drive; GitHub Pages does not manage Drive permissions.
