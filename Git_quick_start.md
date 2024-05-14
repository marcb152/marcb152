# Notes 🗒️

This markdown is a personal reminder to help me remember how to correctly setup my git repositeries using command line and SSH connection/signing.
This is not a full step by step guide designed for everyone, as it assumes you have already generated and added your SSH key to your GitHub account.
I will keep this guide up to date.

# Initializing repo 🚀

1. Open git bach and locate your project directory `cd PATH/TO/YOUR/PROJECT`
2. Init your git project `git init`
3. Add your .gitignore template to your project, you can find good ones [here](https://github.com/github/gitignore)
4. Configure Git to use SSH to sign commits and tags `git config --global gpg.format ssh`
5. Set up the SSH key you would like to use `git config --global user.signingkey /PATH/TO/.SSH/KEY.PUB`
6. Configure commit signature `git config commit.gpgsign true`
> [!TIP]
> You can enable commit signature system-wide using `git config --global commit.gpgsign true`
6. Add all untracked files `git add ./`
7. Initial commit `git commit -a -m "Initial commit"`

# Setting up remote 🌍

1. Create a new empty repo on [GitHub.com](https://github.com/new)
    - **DO NOT add a licence, or readme or whatever**, we will do it afterwards, no need to create merge conflicts now.
2. Set up remote `git remote add origin ssh://git@ssh.github.com/USERNAME/PROJECT_NAME.git`
3. `git branch -M main`
4. `git push -u origin main`
5. You can now check if your commit was verified correctly on GitHub!
> [!IMPORTANT]
> You encountered an error? Go check out [GitHub Troubleshooting SSH guide](https://docs.github.com/en/authentication/troubleshooting-ssh)

# Adding README and licence files

## Licence 📜

1. Visit https://choosealicense.com
2. [Add it to your existing repo](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/adding-a-license-to-a-repository#including-an-open-source-license-in-your-repository)

## README 📑

1. Read https://www.makeareadme.com
2. Create your readme easily on https://readme.so/editor
3. Import it to your project, then commit & push

*I am not a readme expert.*

## Other files 📝

- A changelog is a great way to track updates of various releases https://keepachangelog.com
- CONTRIBUTING.md is essential for open-source projects, [see GitHub docs](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors)
- You can also add :
  - [An Issue template](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/manually-creating-a-single-issue-template-for-your-repository)
  - [A Pull Request template](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository)

# Useful links 🔗

> [!TIP]
> You can check whether your SSH GitHub connexion works using `ssh -T git@github.com`.
> It should greet you with `Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.`

- [How to tell git about your signing key - GitHub docs](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key#telling-git-about-your-ssh-key)
- [Signing commits - GitHub docs](https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits)
