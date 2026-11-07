# Abhishek Sharma | Portfolio

A fast, single-page personal portfolio for **Abhishek Sharma**, an MBA (Marketing) candidate at SIMS Pune (2026 – 2028). It brings together experience, projects, skills, certifications and education in one place, with a one-click resume download.

## What's on the site

| Section | What it covers |
| --- | --- |
| **Hero and Quick facts** | A short introduction, current studies, the roles I am looking for, and the tools and skills I use |
| **Who I am** | A summary of my background and how I approach marketing and analytics |
| **Experience** | Founder's Office and Strategy Intern, Junior Coordinator (NOESIS Club), Cybersecurity Intern, ML and AI Trainee and student club roles |
| **Projects** | An automated customer feedback and sentiment dashboard, a B2B LinkedIn campaign plan and a competitor profile analysis |
| **Skills and Certifications** | Marketing, data and AI, events and design, and cloud, development and security, followed by dated certifications |
| **Education** | MBA, B.Tech and school qualifications |
| **Contact** | Email (with a copy button), LinkedIn and GitHub |

## Features

- **Dynamic visuals.** Animated gradient background with a subtle grid, a skills marquee, scroll-triggered reveals, a scroll-progress bar, an active-section navigation highlight, and cards that glow and tilt towards the cursor. All motion switches off automatically for visitors who prefer reduced motion, and the effects that need a mouse are skipped on touch devices.
- **One-click resume download.** The round icon at the top right downloads `Abhishek_Sharma_Resume.pdf` straight away. The PDF is stored inside `index.html`, so it works on any host and offline, with no server or extra file needed.
- **Print-ready.** Printing the page (`Ctrl + P` or `Cmd + P`) produces a clean, light, resume-style layout without the navigation or decorative elements.
- **Responsive.** Designed for phones, tablets and desktops, with no horizontal scrolling.
- **Accessible.** Semantic HTML, labelled controls, visible keyboard focus and support for reduced-motion settings (the animated cursors switch off automatically).
- **Lightweight.** No frameworks, no build step, no trackers and no external scripts. The only external request is Google Fonts.

## Tech stack

- HTML5, CSS3 and vanilla JavaScript, all in a single `index.html`
- [Outfit](https://fonts.google.com/specimen/Outfit) and [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) from Google Fonts

## Repository structure

```text
.
├── index.html                    # The complete portfolio (HTML, CSS, JS and the embedded resume)
├── Abhishek_Sharma_Resume.pdf    # Source copy of the downloadable resume
└── README.md
```

## Run locally

No installation is needed. Clone the repository and open `index.html` in a browser:

```bash
git clone https://github.com/commderabhi/<repository-name>.git
cd <repository-name>
open index.html        # macOS; on Windows use: start index.html
```

To serve it over a local web server instead:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy with GitHub Pages

1. Push `index.html`, `Abhishek_Sharma_Resume.pdf` and `README.md` to the `main` branch.
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose `main` and the `/ (root)` folder, then click **Save**.
4. After a minute or two, the site will be live at `https://commderabhi.github.io/<repository-name>/`.

## Updating the resume

The download icon serves the PDF embedded in `index.html`. After editing `Abhishek_Sharma_Resume.pdf`, run this from the repository folder to refresh the embedded copy:

```bash
python3 - << 'EOF'
import base64
s = open('index.html', encoding='utf-8').read()
pdf = base64.b64encode(open('Abhishek_Sharma_Resume.pdf', 'rb').read()).decode()
start = s.index('var R="') + 7
end = s.index('";\nfunction bytes', start)
open('index.html', 'w', encoding='utf-8').write(s[:start] + pdf + s[end:])
EOF
```

Commit both files together so the repository copy and the downloadable copy always match.

## Contact

- **Email:** [sharma1412abhishek@gmail.com](mailto:sharma1412abhishek@gmail.com)
- **LinkedIn:** [linkedin.com/in/abhishekcoder111](https://www.linkedin.com/in/abhishekcoder111)
- **GitHub:** [github.com/commderabhi](https://github.com/commderabhi)

## Copyright

© 2026 Abhishek Sharma. All rights reserved. Please do not reuse the content or design without permission.
