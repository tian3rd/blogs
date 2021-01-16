### Setting up a consistent environment across your devices

> Recently, I have re-learned a serious of tool tricks to betterment my workflow as a CS major student, thanks to the fantastic lectures from MIT call the [missing semester](https://missing.csail.mit.edu). This article is about how I set up my terminal environment for consistent performance across my differernt computers.

I used to spend so much time figuring out the config files for different projects. It's not only time consuming, but also causing a lot of inconsitencies if files are not managed properly. Right now, I have an iMac at home, a MBP to carry to school, just imagine if I have to use more multiple virtual environments or remote desktops for various projects!

#### Terminal Multiplexer - tmux

To use the terminal for efficiency, tmux is the one for this job because it provides us with multiple screens and windows for multitasking.

```terminal
brew install tmux
brew install tldr
tldr tmux
```

Here's my screenshot with tmux
![screenshot tmux](https://cdn-std.droplr.net/files/acc_498334/kvZYGJ "tmux")

The `tldr` is a user-friendly version of `man` page for typical commands.

#### Dotfiles to configure your programs

Normally, we have to modify `.bashrc` or `.zshrc` or `.gitconfig` manually to load settings for these programs. Luckily, we can leave the tedious setup to the computers if we already know and set up our environment on one device. The magic behind the scene is the dotfiles. As the name implies, dotfiles is a place to store all dot files for easy management. After setting up the dot files in dotfiles, the files are _symlinked_ to the right place in our system directory. I use [Prof Anish's dotfiles](https://github.com/anishathalye/dotfiles) for most of the settings. The process of updating dotfiles is seamless.

However, beware of the conflicts of just cloning these dotfiles to your own directories since everyone's original env is more or less different. For my iMac, I have to change the alias `ll='ls -a --color=auto'` to `ll='ls -a -G'` to resovlve one of the conficts. Also, I assume it's good to create a repo just for the dotfiles in your GitHub. I just forked one from Anish's dotfiles and starting from there, I need to manage my personal settings to cater to my own needs.

#### Next step: SSH and remote host

I have to dive into this section when I have the chance.
For future update.

#### Shells for easy use

Use [fish](https://fishshell.com) for exciting features of _smarter autocompletion_ and _command syntax highlighting_. I have set fish to be my default shell. It feels amazing.

##### Reference

[Command-line Environment](https://missing.csail.mit.edu/2020/command-line/)
