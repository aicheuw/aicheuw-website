# Reference Guide

To make initializing new projects and adding content to the site reproducible even after a long time, this user manual is written to provide a detailed, step-by-step guide.

The website is built with [Hugo](https://gohugo.io/), a static site generator based on Go, and uses the theme [LoveIt](https://github.com/dillonzq/LoveIt) with theme customizations. The site is deployed with [Netlify](https://www.netlify.com/), allowing Git-based continuous deployment.

## Initializing a new site project

### Create new site

To create a new site, `cd` into the directory that you want a new site to be created, then type:

```bash
hugo new site site_name
```

### Add to Git

To add the directory to version control, `cd` into the website directory, then type:

```bash
git init -b main
```

Or use [GitHub Desktop](https://desktop.github.com/) to add new repository.

### Add theme

To add the theme [`hugo-serif-theme`](https://github.com/zerostaticthemes/hugo-serif-theme) into the project, `cd` into the website directory, then type:

```bash
git submodule add https://github.com/zerostaticthemes/hugo-serif-theme.git themes/hugo-serif-theme
```

### Add configuration

Edit the website configuration in `config.toml` according to the examples in the documentation.

### Remove Git information

To remove the website directory from git, `cd` into the website directory, then type:

```bash
rm -rf .git
```

### Local preview

To preview the website build, `cd` into the website directory, then type:

```bash
hugo serve
```

For full rebuilds, type

```bash
hugo server --disableFastRender
```

### Remove sensitive content from Git*

To [remove sensitive content](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository) committed to git, download [BFG Repo-Cleaner](https://rtyley.github.io/bfg-repo-cleaner/). `cd` into the directory and type

```bash
java jar "<YOUR-PATH/bfg.jar>" --delete folders "<YOUR-SENSITIVE-FOLDER-PATH>"
```

e.g.

```bash
java -jar "C:/Softwares/BFG Repo Cleaner/bfg.jar" --delete-folders "sensitive/password"
```

Then, push to remote

```bash
git push --force
```
