# astro-issue-baseTag-minRepro
A minimal reproduction of an issue in Astro v1.0.0-beta-17 where &lt;base> tags are not respected by relative imports in scripts generated by `astro build`.

## Steps

1. Clone this repo.
1. Make a new GitHub repo. 
1. Substitute your own info in the following places:
   - [ ] `astro.config.mjs -> .site` << "https://your-github-username.github.io"
   - [ ] `astro.config.mjs -> .base` << "your-new-repos-name"
   - [ ] `.github/workflows/main.yml -> env.githubEmail` << Your GitHub account's email address.
   - [ ] `.github/workflows/main.yml -> env.deployToRepo` << Your new repo's name
   - [ ] `src/pages/index.astro -> html>head>base[href]` << "/your-new-repos-name/"
1. Create a new repo secret called API_TOKEN_GITHUB. Set it to an access token with `repo` privileges. 
1. Add your GitHub repo as a remote. Commit and push.
1. Go to `https://<your-github-username>.github.io/<your-remote-repo-name>/`
1. Click the button. You'll see that it doesn't work.
1. Enter DevTools. Inspect the `404` on `/entry.XXXXXX.js`
```