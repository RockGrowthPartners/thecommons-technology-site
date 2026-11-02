# The Commons Technology website

The company site at [thecommons.technology](https://thecommons.technology) for The Commons Technology, Inc., the Delaware corporation that publishes The Commons, Picture Daily and Fanthology. It's the website listed for Apple Developer Program and Google Play developer enrollment, and it hosts the support and privacy pages each app links to from its store listing.

## How it goes live

Every push to `main` is built and deployed by Cloudflare Workers Builds (Worker name `thecommons-technology`), usually within a minute or two. There is nothing to upload by hand.

- `public/` holds everything the site serves.
- `wrangler.jsonc` tells Cloudflare which Worker to deploy to and where the files are.

To change the site, edit files in `public/` and push to `main`. To undo a change, roll back under the Worker's **Deployments** tab in Cloudflare, or revert the commit.

## Pages

| Page | URL | Use it for |
| --- | --- | --- |
| `index.html` | `/` | Company home: legal name, apps, contact |
| `support.html` | `/support` | App Store and Google Play support URL |
| `privacy.html` | `/privacy` | Company privacy policy |
| `404.html` | any unknown path | Not-found page |

Each app has its own support anchor for its store listing:

- The Commons: `https://thecommons.technology/support#the-commons`
- Picture Daily: `https://thecommons.technology/support#picture-daily`
- Fanthology: `https://thecommons.technology/support#fanthology`

Before an app is released, add its privacy notice (for example `public/privacy/fanthology.html`, served at `/privacy/fanthology`) and link it from the list on `privacy.html`.

## Contact details

The email address and phone number appear on every page. If the contact email changes, search the `public/` folder for `daniel@thecommonsspeech.com` and replace each one, including the `"email"` value in the structured data near the top of `index.html`.
