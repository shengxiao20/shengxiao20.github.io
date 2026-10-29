# Michael Hu — Personal Homepage

A static personal portfolio and blog-style homepage based on the public content of [github.com/shengxiao20](https://github.com/shengxiao20).

## Local preview

```bash
python3 -m http.server 8080
```

Open <http://localhost:8080>.

## Update npm downloads and deploy

Open **Actions → Update npm downloads and publish → Run workflow** (select `main`).
The workflow fetches cumulative npm downloads for the packages marked with
`data-npm-downloads` in `index.html`, updates their totals and the UTC cutoff date,
commits the page to `main`, and deploys the static site to GitHub Pages.

Statistics include all available npm download history from 2015-01-10 through
UTC yesterday. Failed API requests or malformed responses fail the workflow;
no estimated values or cached substitutes are used. Each manual run records a
commit, including when the totals have not changed.

The updater is shared from
[`shengxiao20/shengxiao20/.github/actions/update-npm-downloads`](https://github.com/shengxiao20/shengxiao20/tree/main/.github/actions/update-npm-downloads).
It uses the public npm API and GitHub's built-in `GITHUB_TOKEN`; no npm token or
custom repository secret is needed.

In **Settings → Pages → Build and deployment**, select **GitHub Actions**.
After editing and pushing the site, run the workflow to publish it.
