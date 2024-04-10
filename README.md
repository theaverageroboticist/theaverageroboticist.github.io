This repo used hugo to create a [blog](https://jayamuruganravikumar.github.io/theaverageroboticist/)

## OuickStart

To install use `pacman -S hugo`

Create a new site using `hugo new site <sitename>`

## Posts

cd to the site folder

Add Posts using `hugo new content posts/<somefile.md>`, files will be added to 'content/posts/'

To develope `hugo server -D`

## Deployment 

- Run the hugo server
- Execute `hugo -t PaperMod<themeName>` 
- Change the source to github actions
- Configure hugo.yaml for workflow
- Commit and push
- Go to actions to see the build and the published website

### Tags

["linux, shell"]

Confuguration of .toml file [PaperMod](https://github.com/adityatelange/hugo-PaperMod/wiki/Features#home-info-mode)
