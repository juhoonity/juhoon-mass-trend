[README.md](https://github.com/user-attachments/files/33648706/README.md)
# JUHOON / CORTIS Mass Trend Hub

A responsive, static fan-made campaign hub. It provides campaign cards, multilingual interface labels, searchable comments, language/topic/platform filters, and copy buttons.

## Files

- `index.html` — page structure
- `styles.css` — responsive styling and visual design
- `campaigns.js` — **edit this file to add/change campaigns and comments**
- `app.js` — filtering, language switching, rendering and copy behavior

No backend, database, build step, API key or login is required.

## Preview locally

1. Download and unzip the project.
2. Open `index.html` in a modern browser.
3. For the most reliable clipboard behavior, use a local server or deploy the page to HTTPS. Clipboard permissions vary by browser when opening a local file.

Optional local server if Python is installed:
- Open a terminal in this folder.
- Run `python -m http.server 8000`
- Open `http://localhost:8000`

## Deploy free with GitHub Pages

1. Sign in to GitHub and create a new **public** repository, e.g. `juhoon-mass-trend-hub`.
2. Upload `index.html`, `styles.css`, `campaigns.js`, `app.js`, and `README.md` to the repository root.
3. Open the repository's **Settings → Pages**.
4. Under the build/deployment source, select **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then save.
6. Wait for the published URL shown in the Pages section. It usually resembles `https://YOUR-USERNAME.github.io/juhoon-mass-trend-hub/`.

GitHub's interface can change, so follow the current labels shown in your repository settings.

## Deploy with Cloudflare Pages

1. Create a GitHub repository and upload the project files.
2. In Cloudflare, open Workers & Pages and create a Pages project connected to that repository.
3. Choose no framework / static site. No build command is needed; use the repository root as the output directory.
4. Deploy and use the generated `pages.dev` URL.

## How to add a campaign

Open `campaigns.js`. Copy one object inside the `campaigns` array and paste it as another item, remembering to add a comma between campaign objects. Give the new campaign a unique `id`.

Each campaign uses this shape:

```js
{
  id: "unique-campaign-id",
  number: "04",
  status: "ACTIVE",
  title: { en: "Campaign title", vi: "Tên chiến dịch", ko: "캠페인 제목" },
  short: { en: "Short card description", vi: "Mô tả ngắn", ko: "짧은 설명" },
  description: { en: "Full instructions", vi: "Hướng dẫn đầy đủ", ko: "상세 안내" },
  dates: "2026-11-01 · 18:00 ICT",
  objective: { en: "Objective", vi: "Mục tiêu", ko: "목표" },
  hashtags: ["#JUHOON", "#주훈"],
  comments: [
    { id: "NEW001", language: "en", topic: "support", platform: "x", text: "Your prepared comment #JUHOON" },
    { id: "NEW002", language: "vi", topic: "support", platform: "general", text: "Câu bình luận mẫu #JUHOON" }
  ]
}
```

Supported statuses: `ACTIVE`, `COMMUNITY`, `EVERGREEN`.
Supported comment languages: `en`, `vi`, `ko`, `ja` (other language codes can still display, but the language label may show as the code).
Supported topics: use concise values such as `support`, `talent`, `performance`, `group`.
Supported platforms: `x`, `instagram`, `tiktok`, `general`.

The UI labels are translated in the `ui` object at the bottom of `campaigns.js`. Add another UI language there if needed. The actual comment text stays exactly as written.

## Update campaign dates

Replace placeholder values such as `Update dates before launch` with the real campaign window and time zone. Do not publish a time as confirmed until organizers have verified it.

## Before publishing

- Replace sample comments and placeholder dates with verified campaign content.
- Check all hashtags, spelling, translations, and platform-specific length/format.
- Make sure the fan project is clearly labeled as fan-made and unofficial.
- Do not ask fans for passwords, verification codes or private account information.
- Do not automate account actions or encourage repetitive spam. Follow the rules of each platform.
- Test copy buttons on mobile and desktop after deployment.
