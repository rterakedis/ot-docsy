# Docsy Example

[Docsy][] is a [Hugo theme module][] for technical documentation sites, providing easy
site navigation, structure, and more. This **Docsy Example Project** uses the Docsy
theme component as a hugo module and provides a skeleton documentation structure for you to use.
You can clone/copy this project and edit it with your own content, or use it as an example.

In this project, the Docsy theme component is pulled in as a Hugo module, together with other module dependencies:

```bash
$ hugo mod graph
hugo: collected modules in 566 ms
hugo: collected modules in 578 ms
github.com/google/docsy-example github.com/google/docsy@v0.5.1-0.20221017155306-99eacb09ffb0
github.com/google/docsy-example github.com/google/docsy/dependencies@v0.5.1-0.20221014161617-be5da07ecff1
github.com/google/docsy/dependencies@v0.5.1-0.20221014161617-be5da07ecff1 github.com/twbs/bootstrap@v4.6.2+incompatible
github.com/google/docsy/dependencies@v0.5.1-0.20221014161617-be5da07ecff1 github.com/FortAwesome/Font-Awesome@v0.0.0-20220831210243-d3a7818c253f
```

You can find detailed theme instructions in the [Docsy user guide][].

This Docsy Example Project is hosted on [Netlify][] at [example.docsy.dev][].
You can view deploy logs from the [deploy section of the project's Netlify
dashboard][deploys], or this [alternate dashboard][].

This is not an officially supported Google product. This project is currently maintained.

## Using the Docsy Example Project as a template

A simple way to get started is to use this project as a template, which gives you a site project that is set up and ready to use. To do this: 

1. Click **Use this template**.

2. Select a name for your new project and click **Create repository from template**.

3. Make your own local working copy of your new repo using git clone, replacing https://github.com/me/example.git with your repo’s web URL:

```bash
git clone --depth 1 https://github.com/me/example.git
```

You can now edit your own versions of the site’s source files.

If you want to do SCSS edits and want to publish these, you need to install `PostCSS`

```bash
npm install
```

## Running the website locally

Building and running the site locally requires a recent `extended` version of [Hugo](https://gohugo.io).
You can find out more about how to install Hugo for your environment in our
[Getting started](https://www.docsy.dev/docs/getting-started/#prerequisites-and-installation) guide.

Once you've made your working copy of the site repo, from the repo root folder, run:

```
hugo server
```


## Troubleshooting

As you run the website locally, you may run into the following error:

```
➜ hugo server

INFO 2021/01/21 21:07:55 Using config file: 
Building sites … INFO 2021/01/21 21:07:55 syncing static files to /
Built in 288 ms
Error: Error building site: TOCSS: failed to transform "scss/main.scss" (text/x-scss): resource "scss/scss/main.scss_9fadf33d895a46083cdd64396b57ef68" not found in file cache
```

This error occurs if you have not installed the extended version of Hugo.
See this [section](https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#install-hugo) of the user guide for instructions on how to install Hugo.

Or you may encounter the following error:

```
➜ hugo server

Error: failed to download modules: binary with name "go" not found
```

This error occurs if you have not installed the `go` programming language on your system.
See this [section](https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#install-go-language) of the user guide for instructions on how to install `go`.

Or the following error:

```
➜ hugo server
Start building sites … 
hugo v0.105.0-0e3b42b4a9bdeb4d866210819fc6ddcf51582ffa+extended darwin/arm64 BuildDate=2022-10-28T12:29:05Z VendorInfo=gohugoio
Error: Error building site: "/Users/rterakedis/Documents/Git-Repos/ot-docsy/content/en/_index.html:7:1": failed to extract shortcode: template for shortcode "blocks/cover" not found
```

This error may be from cache problems. Try running `hugo mod clean --all` and then `hugo server` again.   You can also run `npm install` to install the required dependencies.

Or the following error:

```
hugo server -D                             
go: github.com/FortAwesome/Font-Awesome@v0.0.0-20220831210243-d3a7818c253f: invalid version: git ls-remote -q origin in /var/folders/r8/y4bg72d56lq9ry7fry3s1yc80000gp/T/hugo_cache/modules/filecache/modules/pkg/mod/cache/vcs/a81254f0cf90f611158215d1cb50586eccc323b54ab825bb7e9c8b2580ac9fb3: exit status 128:
        fatal: 'origin' does not appear to be a git repository
        fatal: Could not read from remote repository.

        Please make sure you have the correct access rights
        and the repository exists.
hugo: collected modules in 514 ms
Error: failed to download modules: failed to execute 'go [mod download]': failed to execute binary "go" with args [mod download]: go: github.com/FortAwesome/Font-Awesome@v0.0.0-20220831210243-d3a7818c253f: invalid version: git ls-remote -q origin in /var/folders/r8/y4bg72d56lq9ry7fry3s1yc80000gp/T/hugo_cache/modules/filecache/modules/pkg/mod/cache/vcs/a81254f0cf90f611158215d1cb50586eccc323b54ab825bb7e9c8b2580ac9fb3: exit status 128:
        fatal: 'origin' does not appear to be a git repository
        fatal: Could not read from remote repository.

        Please make sure you have the correct access rights
        and the repository exists.
```

This error required clearing the hugo cache: `sudo rm -R $TMPDIR/hugo_cache`



[alternate dashboard]: https://app.netlify.com/sites/goldydocs/deploys
[deploys]: https://app.netlify.com/sites/docsy-example/deploys
[Docsy user guide]: https://docsy.dev/docs
[Docsy]: https://github.com/google/docsy
[example.docsy.dev]: https://example.docsy.dev
[Hugo theme module]: https://gohugo.io/hugo-modules/use-modules/#use-a-module-for-a-theme
[Netlify]: https://netlify.com


## Update your Docsy Hugo Module

```bash
cd /path/to/my-existing-site
hugo mod get -u github.com/google/docsy
```

Other options include the following:
* Specific Version:   `hugo mod get -u github.com/google/docsy@v0.5.1`
* Specific Commit:    `hugo mod get -u github.com/google/docsy@99eacb09ffb0`