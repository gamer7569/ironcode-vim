Iron Code Vim Configuration
===========================

A Vim Configuration focused on WordPress development and predominantly used on a Mac with [MacVim](https://code.google.com/p/macvim/)

This project is a fork of [Curtis McHale](https://github.com/curtismchale)'s excellent [WPTT Vim Config](https://github.com/curtismchale/WPTT-Vim-Config)

Lazy Installation
-----------------
From the command line run `(echo set -- -r; curl "https://raw.githubusercontent.com/salcode/ironcode-vim/master/install-ironcode-vim.sh") | bash`

Updating Plugins
----------------
From within Vim type `:BundleInstall!`

Detailed Installation
---------------------
Run the following steps
```
git clone https://github.com/salcode/ironcode-vim.git
~/ironcode-vim/install.sh
```
This will
- copy your current Vim configuration to `.gvimrc.bkup`, `.vimrc.bkup`, and `.vim-bkup/`
- create symbolic links to the `/ironcode-vim` configuration files
- clone the vundle package manager via git
- run vim and trigger an install of all plugins defined for vundle

Recommended Utilities
---------------------
There are a few recommended utilities that don't come with this
repository.  This configuration works fine without these but they are nice.
I recommend both of them and my preferred installation method is
[homebrew](http://brew.sh/).

#### Once homebrew is installed
1. [Exuberant CTags](http://ctags.sourceforge.net/): `brew install ctags`
2. [Ag](http://geoff.greer.fm/ag/): `brew install the_silver_searcher`

### Problems with Git Commit Messages
On a Mac, if you're getting the message
```
error: There was a problem with the editor 'vi'.
Please supply the message using either -m or -F option.
```
when you try to create a Git commit message with Vim, the issue is an [incorrect error code being returned](http://tooky.co.uk/there-was-a-problem-with-the-editor-vi-git-on-mac-os-x/).

You can fix this problem by running
`git config --global core.editor /usr/bin/vim`


## Shortcuts
`:WSUDO` write with sudo, useful when editing a file that was opened without sudo but needs it

`:WS` write with spaces, useful when saving a file but you do NOT want to remove trailing spaces

`,ev` edit .vimrc

`,sv` source .vimrc

`,ts2`  `,ts4` `,tt2` `,tt4` set tabs to spaces size 2, spaces size 4, tabs size 2, and tabs size 4 respectively

`,=` adjust all viewports to be the same size

`Ctrl+h` `Ctrl+j` `Ctrl+k` `Ctrl+l` switch viewports (left, down, up, or right)

`Ctrl+Tab` `Ctrl+Shift+Tab` Next or Previous Buffer

`,bd` close current buffer but keep viewport open

`<F5>` open buffer list, ready to accept a buffer number to switch to

`,el` in PHP, take the current variable and create an error_log() statement for it using print_r()

## Plugins

### [Vundle](https://github.com/gmarik/Vundle.vim)

Sane package management for Vim.

### [ack.vim](https://github.com/mileszs/ack.vim)
Run Ack (or Ag) from Vim and see results in a split window

Example `:Ack 'neeedle'` will search your project for __needle__.
#### Modified to use Ag in .vimrc

### [buffkill.vim](https://github.com/mattdbridges/bufkill.vim)
`:BD` deletes a buffer but allows the window/viewport to stay open

### [Dash](https://github.com/rizzatti/dash.vim)
Requires the [Dash app](http://kapeli.com/dash) for documentation lookup.  
Example usage `:Dash register_post_type`

### [EditorConfig](https://github.com/editorconfig/editorconfig-vim)
Adds support for an .editorconfig file, which allows an editor configuration to be shared across a project even when users are using different editors.  Read more about the [EditorConfig Project](http://editorconfig.org/)

### [Git Gutter](https://github.com/airblade/vim-gitgutter)
Shows a git diff in left column gutter

### [CTRLP](https://github.com/kien/ctrlp.vim)
`Ctrl+p` in normal mode brings up realtime project searching of filenames.

#### Modified with custom ignore pattern in .virmc

### [EasyAlign](https://github.com/junegunn/vim-easy-align)
Use visual mode to highlight the lines to be aligned (e.g. the middle two lines below)

```php
$args = array(
	'post_type' => 'portfolio',
	'posts_per_page' => -1,
);
```

Then type `:A =>` to align based on __=>__.  
Alternatively, <Enter> will put you in EasyAlign interactive mode.

```php
$args = array(
	'post_type'      => 'portfolio',
	'posts_per_page' => -1,
);
```

This will also work with other symbols like `=`.

#### Modified to use :A "symbol" or "Enter" in visual mode in .vimrc

### [PHP Complete](https://github.com/shawncplus/phpcomplete.vim)
PHP omnicomplete with extra support

### [PHP Syntax](https://github.com/StanAngeloff/php.vim)
5.3–5.6 support of PHP syntax

### [Vinegar](https://github.com/tpope/vim-vinegar)
Extension to netrw.

`-` turns your current window into a file browser.  
 Hitting `-` again will move you one directory up in the file tree.
<Enter> will open the file.

### [Syntastic](https://github.com/scrooloose/syntastic)
Shows PHP errors with `>>` in the left side of your editor.

### [Vim Abolish](https://github.com/tpope/vim-abolish)
Installed specifically for format coercion (fooBar)
- `cr_` or `crs` (coerce to snake_case) e.g. "foo_bar"
- `crm` (coerce to MixedCase) e.g. FooBar
- `crc` (coerce to camelCase) e.g. fooBar
- `cru` (coerce to UPPER_CASE) e.g. FOO_BAR
- `cr-` or `crk` (coerce to dash-case (kebab case)) e.g. foo-bar

### [Vim Airline](https://github.com/bling/vim-airline)
Light weight status line for Vim.

### [Vim Colors Solarized](https://github.com/altercation/vim-colors-solarized)

Solarized Color Scheme

### [Vim Commentary](https://github.com/tpope/vim-commentary)

- `gcc` will toggle comment the current line in normal mode
- `gc` will toggle comment the current selection in visual mode

### [Vim Markdown](https://github.com/plasticboy/vim-markdown)

Markdown highlighting for Vim

### [Vim Fugitive](https://github.com/tpope/vim-fugitive)
Git integration into Vim.

### [Vim  Repeat](https://github.com/tpope/vim-repeat)
Extends repeat functionality to plugins, particuarly __Vim Surround__, __Vim Abolish__, and __Vim Commentary__.

### [Vim  Surround](https://github.com/tpope/vim-surround)
Adding and manipulating surround delimiters.

#### Examples
- __abc zyx jjj__ `ysiw{` surround word cursor is on with braces __abc { zyx } jjj__
- __"abc zyx jjj"__ `cs"'` change surround from " to ' __'abc zyx jjj'__
- __abc zyx jjj__ `ys3w<p class="intro">` surround 3 words with HTML paragraph tag
```
<p class="intro">abc zyx jjj</p>
```
- __abc zyx jjj__ `yS3w<p class="intro">` surround 3 words with HTML paragraph tag (capital S causes tags on own lines)
```
<p class="intro">
    abc zyx jjj
</p>
```

Ctags
-----
Ctags are an index of your project.

### Generating Ctags
- From the command line navigate to root of your project/git repo
- Run `ctags --tag-relative -Rf.git/tags --exclude=node_modules --exclude=.git --languages=-javascript,sql` this will create a file called __tags__ in your `/.git/` directory
- You can re-run this command to generate new Ctags at any time (see below for details on automating this)

### Using Ctags
- In Vim, when your cursor is over a function or method hit `Ctrl+]` to jump to where it is defined.
- `Ctrl+t` will jump back to where you started your tag lookup

### Automate Ctag Generation
You can automate the generation of Ctags. Tim Pope discusses generating Ctags based on Git hooks in his post [Effortless Ctags with Git](http://tbaggery.com/2011/08/08/effortless-ctags-with-git.html).  This behavior is integrated in another project of mine, [Iron Code Studio Git Enhancements](https://github.com/ironcodestudio/ironcode-git-enhancements).

Credits
-------
[@salcode](https://github.com/salcode), [@curtismchale](https://github.com/curtismchale/)
