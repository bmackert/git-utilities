This GitHub repository contains files used by and explained in Wilson Mar's
Git and GitHub course.

There are two editions of scripts in this repo:

* File names ending in <strong>.sh</strong> are <strong>Bash shell scripts</strong> 
that normally run on Mac,
and now also on Windows machines installed with <a target="_blank" href="https://wilsonmar.github.io/bash-windows/">Microsoft's WSL (Windows Subystem for Linux)</a>.

* File names ending in <strong>.ps1</strong> are <strong>PowerShell scripts</strong> 
that run on Windows,
but now also Mac and Linux machines after installing <a target="_blank" href="https://wilsonmar.github.io/powershell-on-mac/">Microsoft's PowerShell on OSX</a>.

* File names ending in <strong>.py</strong> are <strong>Python</strong> scripts that normally run on Mac,
and now also on Windows machines installed with <a target="_blank" href="https://wilsonmar.github.io/bash-windows/">Microsoft's WSL (Windows Subystem for Linux)</a>.

Such scripts are being phased out in favor of cross-platform Python script for use on all platforms. However, Python first needs to be installed.

<hr />

<a name="mac-git-install.sh">
<strong>mac-git-install.sh</strong> automatically installs and configures all you need to work with git and GitHub professionally. It downloads and installs Apple's Xcode, Homebrew, Bash code completion, GPG to enable code signing. Text editors Sublime Text, MacVim, and Microsoft's Code are installed. Git clients GitHub Desktop, GitKraken, or SmartGit are installed. These are installed based a setting in file <a target="_blank" href="https://github.com/wilsonmar/git-utilities/blob/master/.secrets.sh">.secrets.sh</a>.

Begin by changing that file with your own information. That data is used to create SSH keys and config files. The script stops if the secrets file still contain default account info. The .gitignore file keeps local customizations (password) from being uploaded to GitHub.

If a component has already been installed, the "UPGRADE" parameter added when executing the script results in an upgrade to the latest version of each component.

The script also configures .bash_profile by adding in contents of the <tt>mac-bash-profile.txt</tt> file containing keyboard aliases. It configures your .gitconfig with color.ui and code signing after it generates GPG and SSH keys for pasting into GitHub or other repositories.
Version numbers are output for each utility installed.
If something is already installed, that is skipped. So this script can be run again.

<a name="git-hooks-install.ps1">
<strong>git-hooks-install.ps1</strong> should be run after cloning locally
to install scripts that Git invokes automatically based on events.
A git clone is necessary to re-build the database.

<a name="git-sisters-update.ps1">
<strong>git-sisters-update.ps1</strong> is a PowerShell script that
clones a sample sample repository you forked on GitHub.
It calls a script that sets git configurations for a project (or globally)<br />
<strong>git_client-config.ps1</strong>

<a name="git-sample-repo-create.ps1">
<strong>git-sample-repo-create.ps1</strong> is a PowerShell script that
creates a repository on your local clones your fork of a sample sample repository.

TODO: A script that provides a summary report of where there are un-pushed files lingering among a set of  repo folders locally (folders with a .git folder).

<hr />

All these scripts create a folder, but that folder is deleted at the beginning of each run
to make them "idempotent" in that each run of the script ends up in the same condition,
whether run the first time or subsequent times.

The scripts contain an <strong>exit</strong> after each set of steps
so you can examine the impact of the whole sequence of commands.

Additionally, diagrams (animated step-by-step in PowerPoint) have been prepared to illustrate the flow and sequence of commands.

Enjoy!

(Changed for class)
