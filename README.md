# setup
Things you do when you get a new computer.

# 1: Setup Chrome
- [ ] [Download](https://www.google.com/chrome/downloads/) and run installer.
- [ ] Create a profile with your company email address.

# 2: Setup VSCode
- [ ] [Download](https://code.visualstudio.com/download) and run the installer.
- [ ] CMD+Shift+P -> `Shell Command: Install 'code' command in PATH`
- [ ] Enable `Auto Save` (File -> Auto Save)
- Install extensions:
    - [ ] [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
    - [ ] [Conventional Commits](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits)
    - [ ] [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
    - [ ] [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)
    - [ ] [AWS CLI Configure](https://marketplace.visualstudio.com/items?itemName=mark-tucker.aws-cli-configure)

# 3: Setup SSH access to Github
Follow [instructions](https://docs.github.com/en/authentication/connecting-to-github-with-ssh), making sure to:
- [ ] generate the key files in the ~/.ssh folder, using the `-f github_{username}` flag.
- [ ] use a passphrase when generating the key files.
    * you will need to type this again in a moment
- [ ] setup keychain options in `code ~/.ssh/config`
- [ ] save your passphrase in the keychain per the [instructions](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).
- [ ] get invited to your employer's github org.

# 4: Setup oh-my-zsh
- [ ] Follow [install instructions](https://ohmyz.sh/#install)
- [ ] Pick a theme that shows your current git branch
    * default works `ZSH_THEME="robbyrussell"`
- [ ] Make sure `git` plugin is listed
    * open via `code ~/.zshrc`
    * `plugins=(git)`

# 5: Setup Nodejs
- [ ] add [nvm](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/nvm) to oh-my-zsh plugins
    * `plugins=(git nvm)`
- [ ] make sure to enable lazy load for better shell startup time (near top of ~/.zshrc).
    * `export NVM_LAZY=1`
- [ ] install a Nodejs version
    * `nvm install --lts`
- [ ] upgrade npm version (if desired)
    * `npm install -g npm@latest`

# 6: Setup brew
- [ ] [Download](https://brew.sh/) and run installer.

# 7: Setup git
- [ ] use brew to update git
   ```
   git --version
   brew install git
   git --version
   ```
- [ ] configure global default profile
   ```
   git config --global user.name "Your Name"
   git config --global user.email "Your@email"
   ```
- [ ] configure repo-specific profile (if desired)
   ```
   git config --local user.name "Your Name"
   git config --local user.email "Your@email"
   ```

# 8: Setup AWS CLI
- [ ] [Download](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) and run installer
    ```
    # all system users
    curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
    sudo installer -pkg AWSCLIV2.pkg -target /
    ```
- [ ] configure profile credentials
    * `aws configure --profile PROFILE_NAME`
- [ ] add [aws](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/aws) to oh-my-zsh plugins
    * `plugins=(git nvm aws)`
- [ ] [Download](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html) and run installers, or simply:
    ```
    brew tap aws/tap
    brew install aws-sam-cli
    sam --version
    ```

# 9: Setup jq
- [ ] `brew install jq`

# 10: Setup Pulumi
- [ ] run [install](https://www.pulumi.com/docs/get-started/aws/begin/) command
    * `brew install pulumi/tap/pulumi`
