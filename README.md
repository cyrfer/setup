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
    - [ ] [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
    - [ ] [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
    - [ ] [Conventional Commits](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits)
    - [ ] [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
    - [ ] [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)
    - [ ] [AWS CLI Configure](https://marketplace.visualstudio.com/items?itemName=mark-tucker.aws-cli-configure)
    - [ ] [Expo Tools](https://marketplace.visualstudio.com/items?itemName=byCedric.vscode-expo)
    - [ ] [glTF Tools](https://marketplace.visualstudio.com/items?itemName=cesium.gltf-vscode)

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

# 5: Setup Nodejs
- [ ] [Download](https://github.com/nvm-sh/nvm#install--update-script) and install nvm
- [ ] Comment out code added to the bottom of [.zshrc](~/.zshrc)
    ```bash
    # commented to allow zsh plugins to manage
    # export NVM_DIR="$HOME/.nvm"
    # [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    # [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
    ```
- [ ] add [nvm](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/nvm) to oh-my-zsh plugins
    * `plugins=(git nvm)`
- [ ] make sure to enable lazy load for better shell startup time (near top of ~/.zshrc).
    * `export NVM_LAZY=1`
- [ ] install a Nodejs version
    * `nvm install --lts`
- [ ] upgrade npm version (if desired)
    * `npm install -g npm@latest`

# 6: Setup brew
- [ ] [Download](https://brew.sh/) and run Brew installer.
- [ ] follow prompts
    ```bash
    ==> Next steps:
    - Run these two commands in your terminal to add Homebrew to your PATH:
        echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/johngrant/.zprofile
        eval "$(/opt/homebrew/bin/brew shellenv)"
    ```

# 7: Setup git
- [ ] make sure Mac Command Line Tools are installed by running `git --version`
  - [ ] if CLT not installed, install them.
- [ ] make sure `git` is listed as one of the plugins in [.zshrc](~/.zshrc)
    * `plugins=(git ...)`
- [ ] use brew to update git
   ```
   git --version
   which git
   brew install git
   which git
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
- [ ] [Download](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) and run installer for AWS CLI
    ```
    # all system users
    curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
    sudo installer -pkg AWSCLIV2.pkg -target /
    ```
- [ ] add [aws](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/aws) to oh-my-zsh plugins
    * `plugins=(git nvm aws)`
- [ ] [Download](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html) and run installers for SAM CLI, or simply:
    ```
    brew tap aws/tap
    brew install aws-sam-cli
    sam --version
    ```
- [ ] Obtain your employer's AWS SSO URL.
- [ ] Follow [instructions](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-sso.html#sso-configure-profile-auto) to configure profile credentials.
    * `aws configure sso`

# 9: Setup jq
- [ ] `brew install jq`

# 10: Setup Hashicorp's tools
- [ ] run [install](https://www.terraform.io/downloads) command
    ```bash
    brew tap hashicorp/tap
    brew install hashicorp/tap/terraform
    npm install --global cdktf-cli@latest
    ```

# 11: Setup Docker
- [ ] [Download](https://www.docker.com/get-started/) and run installer.

