# Buffer ❤️ Open Source
Static site generator (made with [Hugo](https://gohugo.io/)) for [Buffer's Open Source Site](https://bufferapp.github.io/)

## Setup

1. [Install Hugo](https://gohugo.io/#action). It's easy with Homebrew:
  `brew update && brew install hugo`

2. Clone the repo
`git clone --recursive git@github.com:bufferapp/buffer-opensource.git`

3. Run the Hugo server
`hugo server`

4. Open the site at [http://localhost:1313/](http://localhost:1313)

## Adding a new project

It's important to note that the code to generate this site in this repo is separate from the actual generated site, which is in a submodule in the `public` directory.

When making changes it's important to commit and push to the repo in the `public` directory as a separate step, which will deploy the changes to [bufferapp.github.io](https://bufferapp.github.io)

1. Edit an existing project area `.toml` file in the `data/projects` directory, or create a new file for a new area.

2. If it's a new file, add an `AreaName` value at the top of the file.

3. To add a project, create a new entry that looks something like this:

  ```toml
  [[projects]]
  name =  "The project name (Appears in the heading)"
  repo = "The name of the repo on github (excluding 'bufferapp/')"
  description = "A short description of the project"
  ```
4. Run the hugo server, check if everything looks OK locally
5. Generate the site in the root directory with hugo
  ```sh
  hugo
  ```
  
  It might be a good idea to run git status at this point:
  ```sh
  git status
  ``` 
  
  Make sure you aren't detached from the head or anything weird. If you are, you can fix it with:
  ```sh
  git checkout master
  git pull
  ```
  And that should get you back in shape.
  
6. Commit and push changes to `bufferapp.github.io`

  ```sh
  cd public
  git add --all
  git commit -m "Added my new shiny project"
  git push origin master
  ```
7. Don't forget to commit changes to this repo too!
  ```sh
  cd -
  git add --all
  git commit -m "Added my new shiny project"
  git push origin master
  ```
