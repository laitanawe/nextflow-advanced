---
layout: page
title: Setup for DSL1
root: .
---

## Download files
For the Nextflow course demo, you need to download some files to follow the lesson. You don’t need to redo these steps if you already downloaded the demo files.
1. Make a directory called "nfdemo" on the Desktop  and cd into the nfdemo directory.
(To create the demo directory in your Desktop, you can use: `mkdir -pv ~/Desktop/nfdemo`)
(To cd into the demo directory in your Desktop, you can use: `cd ~/Desktop/nfdemo`)
2. To ensure that your present working directory is `~/Desktop/nfdemo`, you can use: `cd ~/Desktop/nfdemo`, then download <a href="https://laitanawe.github.io/nextflow-advanced/data/nextflow-adv-lesson.tar.gz">nextflow-adv-lesson.adv.gz</a>
(If wget is installed in your environment, use: `wget https://laitanawe.github.io/nextflow-advanced/data/nextflow-adv-lesson.tar.gz`)
3. Unzip/extract `nextflow-adv-lesson.tar.gz` by typing `tar -xzvf nextflow-adv-lesson.tar.gz`
You should end up certain files within the folder **`nfdemo/data/ggal`** on your Desktop.

**Let your instructor know if you need help with this step**.

## For DSL1, install Java (version 10 or lower) in your $HOME directory (e.g Java1)
`mkdir -pv ~/opt/java1`

`cd ~/opt/java1`

`base_url=https://enos.itcollege.ee/~jpoial/allalaadimised/jdk8`

`wget --continue --no-check-certificate $base_url/jdk-8u341-linux-x64.tar.gz`

## Unpack and put links to the executables in a common directory in your $PATH::
`tar -xzf jdk-8u341-linux-x64.tar.gz`

`rm -v jdk-8u341-linux-x64.tar.gz*`

`mv -fv jdk1.8.0_341/* .`

`rmdir jdk1.8.0_341`

`mkdir -pv ~/bin`

`ln -sfv ~/opt/java1/bin/* ~/bin/`

## If not in $PATH, add this to bottom of ~/.bashrc, then exit and reload your $PATH:
`echo export PATH=$HOME/bin:$PATH >> ~/.bashrc`

`source ~/.bashrc`

`java -version`

## Install Nextflow on Linux
`mkdir -pv ~/opt/nextflow`

`rm -rfv ~/opt/nextflow/*`

`cd ~/opt/nextflow`

`export NXF_VER=20.04.1`

`curl -fsSL get.nextflow.io | bash`

`mkdir -pv ~/bin`

`ln -sv "$PWD/nextflow" ~/bin/nextflow`

`~/opt/nextflow/nextflow info`



`~/opt/nextflow/nextflow -v`

`export PATH="$HOME/opt/nextflow:$PATH"`

Next time you login, you will find $HOME/opt/nextflow in your $PATH. If you want this to be the default, you can do this:

## Reload your path for Nextflow
`echo export PATH="$HOME/opt/nextflow:$PATH" >> ~/.bashrc`

`source ~/.bashrc`

`nextflow -v`

## Install software
For a Windows computer, download and install <a href="https://mobaxterm.mobatek.net/download.html">MobaXterm</a>.

For a Mac computer running macOS, the default Unix Shell is Bash.

For a Linux computer, the default Unix Shell is usually Bash.

If you do not already have the shell software installed or do not use any of the operating
systems above, you may need to download and install it.

## Open a new shell
After installing the software
1. Open a terminal. If you're not sure how to open a terminal on your operating system,
see the instructions below.
2. In the terminal type `cd` then press the <kbd>Return</kbd> key.
   This step will make sure you start with your home folder as your working directory.

In the lesson, you will find out how to access the data files in this folder.

> ## Where to type commands: How to open a new shell
>
> The shell is a program that enables us to send commands to the computer and receive output.
> It is also referred to as the terminal or command line.
>
> Some computers include a default Unix Shell program.
> The steps below describe some methods for identifying and opening
> a Unix Shell program if you already have one installed.
> There are also options for identifying and downloading a Unix Shell program,
> a Linux/UNIX emulator, or a program to access a Unix Shell on a server.
>
> If none of the options below address your circumstances,
> try an online search for: Unix shell [your computer model] [your operating system].
{: .callout}

{::options parse_block_html="true" /}
<div>
<ul class="nav nav-tabs nav-justified" role="tablist">
<li role="presentation" class="active"><a data-os="windows" href="#windows" aria-controls="Windows"
role="tab" data-toggle="tab">Windows</a></li>
<li role="presentation"><a data-os="macos" href="#macos" aria-controls="macOS" role="tab"
data-toggle="tab">macOS</a></li>
<li role="presentation"><a data-os="linux" href="#linux" aria-controls="Linux" role="tab"
data-toggle="tab">Linux</a></li>
</ul>

<div class="tab-content">
<article role="tabpanel" class="tab-pane active" id="windows">
Computers with Windows operating systems do not automatically have a Unix Shell program
installed.
In this lesson, we encourage you to use an emulator included in [Git for Windows][install_shell],
which gives you access to both Bash shell commands and Git.

Once installed, you can open a terminal by running the program Git Bash from the Windows start
menu.

**For advanced users:**

As an alternative to Git for Windows you may wish to [Install the Windows Subsystem for Linux][wsl]
which gives access to a Bash shell command-line tool in Windows 10.

Please note that commands in the Windows Subsystem for Linux (WSL) may differ slightly
from those shown in the lesson or presented in the workshop.
</article>

<article role="tabpanel" class="tab-pane" id="macos">
For a Mac computer running macOS Mojave or earlier releases, the default Unix Shell is Bash.
For a Mac computer running macOS Catalina or later releases, the default Unix Shell is Zsh.
Your default shell is available via the Terminal program within your Utilities folder.

To open Terminal, try one or both of the following:
* In Finder, select the Go menu, then select Utilities.
  Locate Terminal in the Utilities folder and open it.
* Use the Mac 'Spotlight' computer search function.
  Search for: `Terminal` and press <kbd>Return</kbd>.

To check if your machine is set up to use something other than Bash,
type `echo $SHELL` in your terminal window.

If your machine is set up to use something other than Bash,
you can run it by opening a terminal and typing `bash`.

[How to Use Terminal on a Mac][mac-terminal]
</article>

<article role="tabpanel" class="tab-pane" id="linux">
The default Unix Shell for Linux operating systems is usually Bash.
On most versions of Linux, it is accessible by running the
[Gnome Terminal][gnome-terminal] or [KDE Konsole][kde-konsole] or [xterm][xterm],
which can be found via the applications menu or the search bar.
If your machine is set up to use something other than Bash,
you can run it by opening a terminal and typing `bash`.
</article>
</div>
</div>

[zip-file]: {{ page.root }}/data/shell-lesson-data.zip
[wsl]: https://docs.microsoft.com/en-us/windows/wsl/install-win10
[mac-terminal]: http://www.macworld.co.uk/feature/mac-software/how-use-terminal-on-mac-3608274/
[gnome-terminal]: https://help.gnome.org/users/gnome-terminal/stable/
[kde-konsole]: https://konsole.kde.org/
[xterm]: https://en.wikipedia.org/wiki/Xterm
[install_shell]: https://carpentries.github.io/workshop-template/#shell



{% include links.md %}
