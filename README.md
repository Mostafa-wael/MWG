# MWG
A simple script to automate my git workflow.

            MMMMMMMM               MMMMMMMMWWWWWWWW                           WWWWWWWW      GGGGGGGGGGGGG
            M:::::::M             M:::::::MW::::::W                           W::::::W   GGG::::::::::::G
            M::::::::M           M::::::::MW::::::W                           W::::::W GG:::::::::::::::G
            M:::::::::M         M:::::::::MW::::::W                           W::::::WG:::::GGGGGGGG::::G
            M::::::::::M       M::::::::::M W:::::W           WWWWW           W:::::WG:::::G       GGGGGG
            M:::::::::::M     M:::::::::::M  W:::::W         W:::::W         W:::::WG:::::G              
            M:::::::M::::M   M::::M:::::::M   W:::::W       W:::::::W       W:::::W G:::::G              
            M::::::M M::::M M::::M M::::::M    W:::::W     W:::::::::W     W:::::W  G:::::G    GGGGGGGGGG
            M::::::M  M::::M::::M  M::::::M     W:::::W   W:::::W:::::W   W:::::W   G:::::G    G::::::::G
            M::::::M   M:::::::M   M::::::M      W:::::W W:::::W W:::::W W:::::W    G:::::G    GGGGG::::G
            M::::::M    M:::::M    M::::::M       W:::::W:::::W   W:::::W:::::W     G:::::G        G::::G
            M::::::M     MMMMM     M::::::M        W:::::::::W     W:::::::::W       G:::::G       G::::G
            M::::::M               M::::::M         W:::::::W       W:::::::W         G:::::GGGGGGGG::::G
            M::::::M               M::::::M          W:::::W         W:::::W           GG:::::::::::::::G
            M::::::M               M::::::M           W:::W           W:::W              GGG::::::GGG:::G
            MMMMMMMM               MMMMMMMM            WWW             WWW                  GGGGGG   GGGG



[![GitHub issues](https://img.shields.io/github/issues/Mostafa-wael/MWG)](https://github.com/Mostafa-wael/MWG/issues)
[![GitHub forks](https://img.shields.io/github/forks/Mostafa-wael/MWG)](https://github.com/Mostafa-wael/MWG/network)
[![GitHub stars](https://img.shields.io/github/stars/Mostafa-wael/MWG)](https://github.com/Mostafa-wael/MWG/stargazers)
[![GitHub license](https://img.shields.io/github/license/Mostafa-wael/MWG)](https://github.com/Mostafa-wael/MWG/blob/master/LICENSE)

## About
Most of us use git to manage our projects. We start by adding the files we want to track, then we commit them, and finally we push them to the remote repository. Then, we may want to add a tag to the commit, or we may want to create a release.
We do this over and over again, and it can get a bit tedious. So, I decided to automate this process. I hope it helps you too!

## Installation
1. Clone the repo.
2. If you used the download options:
   - Go to the downloads: `cd ~/Downloads/`
   - Unzip the file: `unzip MWG.zip`
3. Go to the script: `cd MWG-main`
4. Give the script the required permissions: `chmod u+x mwg`
5. Add it to your binaries: `sudo cp ./mwg /usr/local/bin`
6. To solve some permission issues: `sudo chown -R $(whoami) /usr/local/bin/mwg`


## Usage
1. Go to your project's directory: `cd ~/path/to/your/project`
2. To push your changes: `mwg <commit message>`
3. To tag and push the commit: `mwg <commit message> <tag name>`
4. For help and more options: `mwg -h` or `mwg --help`

For the base case of committing and pushing changes, you don't have to use any options. This is made in purpose for the most common use case. Just type `mwg` and the commit message. 

The script will automatically:
- Add all the files to the Git index.
- Commit them.
- Push them to the remote repository. 

This is the same as running `git add . && git commit -m "commit message" && git push`.

## More Options
- **Commit** changes with a message and **pull changes** from the remote before committing: `mwg -p "Fix bug in navigation bar"`
- **Commit** changes with a message, **rebase the current branch**, and **create a tag**: `mwg -r "Add new feature" "v1.0"`
- **Commit** changes with a message, **amend the previous commit**, and **force the creation of a tag**: `mwg -a -f "Fix typo in README" "v1.0.1"`
- **Commit** changes with a message, **display a summary** of the changes before committing, and **confirm before pushing**: `mwg -c "Update homepage" -s`
- **Commit** changes with a message and **add only specific files to the Git index**: `mwg "Update CSS and JS files" -l styles.css scripts.js`

Note that in all of these examples, you can add more than one option at a time by using multiple flags, such as `-pr` to **pull changes** and **rebase** the branch before committing.

If found a bug or have a suggestion, please open an issue or a pull request. I'll be happy to help!
