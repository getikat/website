# [getikat.com](https://getikat.com)

The website for Ikat: the home page, how to get the app, how Ikat handles data (security and privacy), and support. Plain static
files, with no build step, no scripts and no trackers.

## Run it

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Links are root-relative (`/privacy/`), so serve from the folder's root.

## How it is published

GitHub Pages serves this repository at getikat.com (`CNAME`); `.nojekyll` stops GitHub from processing the files. Pages cannot set
response headers, so each page carries a strict Content-Security-Policy in a `<meta>` tag. Changes arrive by pull request and are
merged by Alan.

## What is on it

| Page | Path |
|---|---|
| Home | `/` |
| Get the app | `/app/` |
| Security (the paragraph the app's "Read more" opens) | `/security/` |
| Privacy | `/privacy/` |
| Support | `/support/` |

The security and privacy text is a short contract: each sentence is something the app does. Change it in the same change as the code
it describes.

## Experiments

`experiments.json` lists the experiments the app is running, for the app to read (it is not part of the pages). Each experiment has an
`id` and variants with a `name` and a `weight`; ids and names are letters and digits only. The app picks its own variant from a
random number kept on the phone, so adding an experiment here changes nothing about who is in it until the app next checks, and the
site never learns who saw what. An empty list means none are running.

## License

All rights reserved. This repository is public so the site can be hosted from it, and no license is granted to reuse it.
