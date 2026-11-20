# Relay — ASL concept prototype

Nine screens from the **CONCEPT ASL** Figma frames, built in plain HTML/CSS/JS on
Orange OUDS tokens, plus three layers the static frames could not carry:

- **Camera AI** — the phone locks onto a hand, draws 21 landmarks, and turns signs
  into English one sign at a time, with a confidence figure on each.
- **Voice AI** — speech arrives as captions that correct themselves as the
  recogniser settles.
- **Avatar ASL** — the reply plays back on the signing avatar, with a progress line
  and the English tracking word by word underneath it.

Both are **simulations**. No camera or microphone is accessed, nothing is uploaded,
and there is no network call at runtime.

## Run it locally

Open `index.html` in a browser. No build step, no dependencies.

## Publish it on GitHub Pages

1. Create an empty repository on github.com (public — Pages needs that on a free plan).
2. From this folder:

       git remote add origin https://github.com/<you>/<repo>.git
       git push -u origin main

3. In the repository: **Settings → Pages → Source: Deploy from a branch → main / (root)**.
4. The page appears at `https://<you>.github.io/<repo>/` in a minute or two.

### One thing to fix after step 4

`index.html` sets the WhatsApp/Slack link preview image with a relative path. Make it
absolute so the preview card shows:

    sed -i '' 's|content="assets/share.png"|content="https://<you>.github.io/<repo>/assets/share.png"|' index.html

Then commit and push again.

## Files

- `index.html` — everything: markup, styles and both AI layers.
- `assets/` — the photo, logo lockup, card glyphs and OUDS icons exported from Figma,
  plus `share.png` for link previews.

## Note on the assets

`assets/cam.jpg` is a photograph of an identifiable person taken from the Figma file.
A public repository makes it public. Check you have the right to publish it before
pushing, or swap it for a placeholder.
