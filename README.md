This repo contains code for the blog

## OuickStart

To install use `pacman -S hugo`

Create a new site using `hugo new site <sitename>`

## Posts

cd to the site folder

Add Posts using `hugo new content posts/<somefile.md>`, files will be added to 'content/posts/'

To develope `hugo server -D`

## Deployment 

- Create a repo with `<website-name>.github.io`
- Add the url to the .toml file
- Change the branch to `main` and create a first commit for the repo
- Add the repo as submodule to public `git submodule add <repo> public`
- Run the hugo server
- Execute `hugo -t PaperMod<themeName>` 
