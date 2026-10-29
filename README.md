# PARDA

A short documentary on girls' education in Pakistan, and the site that presents it.
Spoken in Urdu, subtitled in English. Running time 1:55.

The site is one static page. There is no build step, no framework and no server —
just open `index.html` in a browser and it works.

```
index.html    the whole site: markup, styles and script in one file
parda.mp4     the film (720p, 13 MB, web-optimised)
poster.jpg    the still shown before the film plays
hero.jpg      the still behind the title on narrow screens
```

## Put it on GitHub Pages

1. Create a new repository on GitHub. A public repo is required for free Pages.
2. Upload these four files (plus `.nojekyll`) to the root of the repo:

   ```bash
   git init
   git add .
   git commit -m "PARDA documentary site"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
   git push -u origin main
   ```

   Or use **Add file → Upload files** on the GitHub web page and drag them in —
   that works fine and skips the command line entirely.

3. In the repo, go to **Settings → Pages**. Under *Build and deployment*, set
   **Source** to `Deploy from a branch`, **Branch** to `main` and the folder to
   `/ (root)`. Save.
4. Wait about a minute. The site appears at
   `https://YOUR-USERNAME.github.io/YOUR-REPO/`.

`.nojekyll` tells GitHub to serve the files as they are instead of running them
through its blog engine. Keep it.

## Changing things

Everything is in `index.html`.

- **Text in the page** (headings, the hero, the credits) is plain HTML — search for
  the words you want to change and edit them in place.
- **The narration, the statistics and the action list** are JavaScript arrays near
  the bottom of the file: `STORY`, `FACTS` and `ACTIONS`. Edit the entries there and
  the page rebuilds those sections on load.
- **The quote timecodes** are the `data-t` attributes on each `.voice` button, in
  seconds. Changing one changes where the film jumps to when that line is clicked.
- **Colours and fonts** are CSS variables in the `:root` block at the top of the
  `<style>`. Change `--gold` and the accent changes everywhere.

## A note on the video

`parda.mp4` is a compressed 720p copy, about 13 MB. That is deliberate — a smaller
file loads faster for anyone visiting the site, and the page uses it twice (once as
the ambient loop behind the title, once in the player).

If you would rather serve the original master, replace `parda.mp4` with your own
file under the same name. GitHub allows files up to 100 MB, so a larger master is
fine; the page will pick it up with no other changes.

If the film ever outgrows that, host it on YouTube or Vimeo instead and swap the
`<video>` element in the film section for their embed. The rest of the page is
unaffected.

## Custom domain

If you buy a domain, add it under **Settings → Pages → Custom domain** and create a
`CNAME` record at your registrar pointing to `YOUR-USERNAME.github.io`. Tick
*Enforce HTTPS* once the certificate is issued.

## Credits

The cut is edited from six source films on girls' education, listed in the
*Footage* section at the bottom of the page.
