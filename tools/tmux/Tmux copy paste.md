## How to copy and paste in tumx?

> The copy and paste functionalities are counterintuitive in tmux, because I can't use the default shortcuts as `cmd + c` to get the text to the clipboard.

### Copy in tmux

The first thing to configure your tmux is to set up the `.tmux.conf` file in your dotfiles folder or the home directory. I've recombined the `ctrl + b` to `ctrl + a` for better experience.

- In `.tmux.conf`:

  - First to recombine `ctrl + b` to `ctrl + a`
    - `unbind C+b`
    - `set -g prefix C+a`
  - Then to set tmux to behave like vim:
    - `bind T copy-mode-vi "v" send X begin-selection`

- To enter into the copy mode:

  - `ctrl + a` then `[`
  - `ctrl + space` then use arrow keys to go to the position where you want to start copying
  - `v` to enter the recombined visual mode (similar to vim) to select the highlighted text
  - `y` to copy/yank
  - This will bring you to the prompt line. `ctrl + a` then `]` to paste the text.

- Copy with mouse drag
  - In `.tmux.conf` set:
    - `set -g mouse on`
  - Then we can use mouse to select highlighted text, then hold the `shift` to copy
  - Then use `ctrl + a` and `]` to paste.

### How to copy the text into the system clipboard?

It's definitely a pain in the ass... The alternative way on Mac OS is to `brew install xclip` and then hold `fn` when selecting the text, then use the `cmd + C` as usual. But the thing is that in this way, it will copy across multiple panes which is not what we desire. However, it's an option if you layout the panes vertically.

I'll keep looking for a better solution to tweak this weird problem.

#### Ref

1. [Everything you need to know about Tmux copy paste](http://www.rushiagr.com/blog/2016/06/16/everything-you-need-to-know-about-tmux-copy-pasting-ubuntu/)
