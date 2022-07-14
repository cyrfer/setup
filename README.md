# setup
Things you do when you get a new computer.

# 1: Setup Chrome
1. [ ] [Download](https://www.google.com/chrome/downloads/) and run installer.
2. [ ] Create a profile with your company email address.

# 2: Setup VSCode
1. [ ] [Download](https://code.visualstudio.com/download) and run the installer.
2. [ ] CMD+Shift+P -> `Shell Command: Install 'code' command in PATH`
3. [ ] Enable `Auto Save` (File -> Auto Save)
4. Install extensions:
    1. [ ] [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
    2. [ ] [Conventional Commits](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits)
    3. [ ] [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
    4. [ ] [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)


# 3: Setup SSH access to Github
Follow [instructions](https://docs.github.com/en/authentication/connecting-to-github-with-ssh), making sure to:
1. [ ] generate the key files in the ~/.ssh folder, using the `-f github_{username}` flag.
2. [ ] use a passphrase when generating the key files.
    * you will need to type this again in a moment
3. [ ] setup keychain options in `code ~/.ssh/config`
4. [ ] save your passphrase in the keychain per the [instructions](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).
5. [ ] get invited to your employer's github org.

# 4: Setup oh-my-zsh
1. [ ] Follow [install instructions](https://ohmyz.sh/#install)
2. [ ] Pick a theme that shows your current git branch
    * default works `ZSH_THEME="robbyrussell"`
2. [ ] Make sure `git` plugin is listed
    * open via `code ~/.zshrc`
    * `plugins=(git)`

# 5: Setup Nodejs
1. [ ] add [nvm](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/nvm) to oh-my-zsh plugins
    * `plugins=(git nvm)`
2. [ ] make sure to enable lazy load for better shell startup time.
    * `export NVM_LAZY=1`

# 6: Setup brew
1. [ ] [Download](https://brew.sh/) and run installer.

# 7: Setup git
1. [ ] use brew to update git
   ```
   git --version
   brew install git
   git --version
   ```
2. [ ] configure global default profile
   ```
   git config --global user.name "Your Name"
   git config --global user.email "Your@email"
   ```
3. [ ] configure repo-specific profile (if desired)
   ```
   git config --local user.name "Your Name"
   git config --local user.email "Your@email"
   ```

# 8: Setup AWS CLI
1. [ ] add [aws](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/aws) to oh-my-zsh plugins
    * `plugins=(git nvm aws)`
2. [ ] [Download](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html) and run installers, or simply:
    ```
    brew tap aws/tap
    brew install aws-sam-cli
    sam --version
    ```
