# K8s Desktop Setup

- Install Rancher Desktop
    - https://docs.rancherdesktop.io/getting-started/installation/#linux

- Install Homebrew package manager
    - https://brew.sh/

- Install kubectl and K9s
    ```bash
    brew install kubectl k9s
    ```

- Install tmux and Vim
    ```
    sudo apt install tmux vim

    ```

- Add config in `~/.bashrc` file for kubectl alias and auto complete
    ```
    # kubectl
    alias k='kubectl'

    source /etc/bash_completion
    source <(kubectl completion bash)
    complete -o default -F __start_kubectl k
    ```
    
    **IMPORTANT**: add it after line eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv bash)" - to avoid kubectl not found error on terminal startup and to also fix auto complete not working

- Create `~/.vimrc` file for making easier to work with yaml files with Vim
    ```

    " Ensure Vim uses filetype plugins
    filetype plugin on

    " Enable indentation
    filetype indent on

    " Set the default indentation to 2 spaces for all files
    set tabstop=2
    set softtabstop=2
    set shiftwidth=2
    set expandtab

    " Highlight trailing whitespace in all files
    autocmd BufRead,BufNewFile * match Error /\s\+$/

    " Enable auto-indentation
    set autoindent

    " Turn on syntax highlighting
    syntax on

    " Set backspace so it acts more intuitively
    set backspace=indent,eol,start
    ```