---
title: Setup
---

## Setup

:::::::::::::::::::::::::::::::::::::::::  callout

## Install Git {#setup2}

Follow these installation instructions according to your Operating System (OS).


::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::: solution

### Windows {#windows1}

Please install **Git for Windows** using the instructions below.

- Download the Git for Windows <a href="https://gitforwindows.org/">installer</a>
installed.
- Run the installer and follow the steps below:
  - Click on "Next" four times (two times if you've previously installed Git).  You don't need to change anything in the Information, location, components, and start menu screens.
  - From the dropdown menu, "Choosing the default editor used by Git", select "Use the Nano editor by default" (NOTE: you will need to scroll <emph>up</emph> to find it) and click on "Next".
  - On the page that says "Adjusting the name of the initial branch in new repositories", ensure that "Let Git decide" is selected. This will ensure the highest level of compatibility for our lessons.
  - Ensure that "Git from the command line and also from 3rd-party software" is selected and click on "Next". (If you don't do this Git Bash will not work properly, requiring you to remove the Git Bash installation, re-run the installer and to select the "Git from the command line and also from 3rd-party software" option.)
  - Select "Use bundled OpenSSH".
  - Ensure that "Use the native Windows Secure Channel Library" is selected and click on "Next".
  - Ensure that "Checkout Windows-style, commit Unix-style line endings" is selected and click on "Next".
  - Ensure that "Use Windows' default console window" is selected and click on "Next".
  - Ensure that "Default (fast-forward or merge) is selected and click "Next"
  - Ensure that "Git Credential Manager" is selected and click on "Next".
  - Ensure that "Enable file system caching" is selected and click on "Next".
  - Click on "Install".
  - Click on "Finish" or "Next".
-  If your "HOME" environment variable is not set (or you don't know what this is):
  - Open command prompt (Open Start Menu then type <code>cmd</code> and press <kbd>Enter</kbd>)
  - Type the following line into the command prompt window exactly as shown: <p><code>setx HOME "%USERPROFILE%"</code></p>
  - Press <kbd>Enter</kbd>, you should see <code>SUCCESS: Specified value was saved.</code>
  - Quit command prompt by typing <code>exit</code> then pressing <kbd>Enter</kbd>

If you prefer, here is a video tutorial with the instructions: <a href="https://www.youtube.com/watch?v=339AEqk9c-8" target="_blank">https://www.youtube.com/watch?v=339AEqk9c-8</a>

::::::::::::

:::::::::::: solution

### MacOS {#macos1}

Please open the Terminal app. To open Terminal, try one or both of the following:

- In Finder, select the Go menu, then select Utilities.
  Locate Terminal in the Utilities folder and open it.
- Use the Mac 'Spotlight' computer search function.
  Search for: `Terminal` and press <kbd>Return</kbd>.

In Terminal, type <code>git --version</code> and press <kbd>Enter/Return</kbd>. If Git is installed, you should see a message similar to <code>git version X.XX.X</code>.

If it's not installed already, follow the instructions on the [official git website](https://git-scm.com/downloads/mac) to install Git.



::::::::::::

:::::::::::: solution

### Linux {#linux1}

If Git is not already available on your machine you can try to install it via your distro's package manager. For Debian/Ubuntu run <code>sudo apt-get install git</code> and for Fedora run <code>sudo dnf install git</code>.

::::::::::::

## Creating a GitHub Account

You will need an account for [GitHub](https://github.com) to follow episodes 7 & 8 in this lesson.

1. Go to <https://github.com> and follow the "Sign up" link at the top-right of the window.
2. Follow the instructions to create an account.
3. Verify your email address with GitHub.
4. Configure multifactor authentication (see below).

### Multi-factor Authentication

In 2023, GitHub introduced a requirement for 
all accounts to have 
[multi-factor authentication (2FA)](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/about-two-factor-authentication) 
configured for extra security.
Several options exist for setting up 2FA, which are summarised here:

1. If you already use an authenticator app, 
   like [Google Authenticator](https://support.google.com/accounts/answer/1066447?hl=en&co=GENIE.Platform%3DiOS&oco=0) 
   or [Duo Mobile](https://duo.com/product/multi-factor-authentication-mfa/duo-mobile-app) on your smartphone for example, 
   [add GitHub to that app](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication#configuring-two-factor-authentication-using-a-totp-mobile-app).
2. If you have access to a smartphone but do not already use an authenticator app, install one and 
   [add GitHub to the app](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication#configuring-two-factor-authentication-using-a-totp-mobile-app).
3. If you do not have access to a smartphone or do not want to install an authenticator app, you have two options:
    1. [set up 2FA via text message](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication#configuring-two-factor-authentication-using-text-messages) 
       ([list of countries where authentication by SMS is supported](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/countries-where-sms-authentication-is-supported)), or
    2. [use a hardware security key](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication#configuring-two-factor-authentication-using-a-security-key) 
       like [YubiKey](https://www.yubico.com/products/yubikey-5-overview/) 
       or the [Google Titan key](https://store.google.com/us/product/titan_security_key?hl=en-US&pli=1).

The GitHub documentation provides [more details about configuring 2FA](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication).

----------------

## Preparing Your Working Directory

We'll do our work in the `Desktop` folder so make sure you change your working directory to it with:

```bash
$ cd
$ cd Desktop
```

[workshop-setup]: https://carpentries.github.io/workshop-template/install_instructions/#git

