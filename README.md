# Genes and Health documentation

The aim of this documentation is to provide clear and helpful instructions to our end users of the Genes and Health Trust Research Environment. The docs are available at [https://genesandhealth.pages.dev/](https://genesandhealth.pages.dev/)

# To contribute to this documentation
There are 2 main ways you can contribute:

1. Make an issue if you see something missing or out of date
2. Make a pull request to this repo to directly update the docs. 

## Instructions updating the docs

1. `git clone` this repo to your computer 
2. If you do not have this already, download just

MacOS
```bash
brew install just
```

3. From your terminal, go to this repo (now locally on your computer) and make a new branch. Git has some excellent instructions on git branching. For reference, do:

```
git checkout -b "name_of_new_branch"
```

4. Make a virtual environment, with the command:
```
just virtualenv
```

If you want to do this manually, you can make a virtualenv through the normal methods - `python -m virtualenv .venv`. 

5. Activate this virtual environment and install all the dependencies in the requirements.txt file. There is a shortcut for the installation step using `just`. 

```
just devenv
```

6. Run the docs locally. This will make the docs available at `http://127.0.0.1:8000/` in your browser. 

```
just serve
```

7. Make any changes you want in a text editor (recommend VS code)
8. Add and commit any changes in files and then push back to Github. Make a pull request. A member of the admin team will review the changes and approve or comment on them. 

> Note that when you make a pull request, a live version of your changes will be created by Cloudflare which we are using for hosting. The cloudflare bot will comment on your pull request with the URL for this. 
