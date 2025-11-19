if status is-interactive
    # Commands to run in interactive sessions can go here
end

function fish_prompt
    set -l pointer_color red
    #test $status = 0; and set pointer_color yellow
    test $status = 0; and set pointer_color purple

    set -q __fish_git_prompt_showupstream
    or set -g __fish_git_prompt_showupstream auto

    if not set -q VIRTUAL_ENV_DISABLE_PROMPT
        set -g VIRTUAL_ENV_DISABLE_PROMPT true
    end

    #set_color yellow
    set_color purple
    printf '['
    #printf '%s' $USER
    #printf '%s@%s' $USER $hostname
    printf '%s@wwt-mbp' $USER
    set_color normal
    printf ' in '

    set_color $fish_color_cwd
    printf '%s' (prompt_pwd --dir-length=0)
    printf ']'
    set_color normal

    # git
    set_color white -d
    set -l prompt_git (fish_git_prompt '%s')
    test -n "$prompt_git"
    and printf ' %s' $prompt_git
    set_color normal

    # Line 2
    echo
    set_color $pointer_color
    #printf '» '
    printf '$ '
    set_color normal
end
# Fish command history
function history
    builtin history --show-time='%F %T '
end

# Replace ls with eza
#alias ls 'eza -al --color=always --group-directories-first --icons' # preferred listing
alias ls 'eza -a --color=always --group-directories-first --icons ' # preferred listing
alias lsz 'eza -al --color=always --total-size --group-directories-first --icons' # include file size
alias la 'eza -a --color=always --group-directories-first --icons' # all files and dirs
#alias ll 'eza -l --color=always --group-directories-first --icons'  # long format
alias ll 'eza -al --color=always --group-directories-first --icons' # long format
alias lt 'eza -aT --color=always --group-directories-first --icons' # tree listing
alias l. 'eza -ald --color=always --group-directories-first --icons .*' # show only dotfiles
alias sshn 'ssh dennis@192.168.1.11'
alias cdb 'cd /Users/faucherd/Documents/Personal/MBP-Personal/Programming/bash'
alias g '/opt/homebrew/bin/gemini -p'
alias fbp '/Users/faucherd/Documents/Personal/MBP-Personal/Programming/bash/fix_logseg_bold_pages.sh'
alias fbj '/Users/faucherd/Documents/Personal/MBP-Personal/Programming/bash/fix_logseg_bold_journals.sh'
alias sla '/Users/faucherd/Documents/Personal/MBP-Personal/Programming/bash/search_logseq_admin.sh'
alias sl '/Users/faucherd/Documents/Personal/MBP-Personal/Programming/bash/search_logseq.sh'
alias lst '/Users/faucherd/Documents/Personal/MBP-Personal/Programming/bash/logseq_tasks.sh'
alias lstw '/Users/faucherd/Documents/Personal/MBP-Personal/Programming/bash/logseq_tasks_wwt.sh'
alias rtr /Users/faucherd/Documents/Personal/MBP-Personal/Programming/VibeCoding/Cursor/cursor-router/build/cursor-router

# Replace some more things with better alternatives
#alias cat 'bat --style header --style snip --style changes --style header'
#alias cat bat
alias less 'less -FRi'
#alias vi hx

# Colima Docker Replacement Aliases
#alias docker colima
# alias dps 'colima list'
set -x DOCKER_HOST unix:///$HOME/.colima/docker.sock

# Add pyenv executable to PATH by running
# the following interactively:

set -Ux PYENV_ROOT $HOME/.pyenv
set -U fish_user_paths $PYENV_ROOT/bin $fish_user_paths

# Load pyenv automatically by appending
# the following to ~/.config/fish/config.fish:

pyenv init - | source

# Added by LM Studio CLI (lms)
set -gx PATH $PATH /Users/faucherd/.lmstudio/bin
# End of LM Studio CLI section
# 
# DMF Added my own bin directory to the PATH
set -gx PATH $PATH /Users/faucherd/bin
set -gx PATH $PATH /Users/faucherd/.cargo/bin
set -gx PATH $PATH /Users/faucherd/.local/bin
# For MacPorts
set -gx PATH $PATH /opt/local/bin

# Added for glow
set -gx EDITOR /opt/homebrew/bin/vim
set -gx PATH "/opt/homebrew/opt/ruby/bin:$PATH"
set -gx PATH "/opt/homebrew/lib/ruby/gems/3.4.0/bin:$PATH"
set -gx PATH "/opt/homebrew/Cellar/openjdk@21/21.0.7/bin:$PATH"
set -gx PATH "/usr/local/share/dotnet/:$PATH"

#Added to use Homebrew binaries first
set -gx PATH "/opt/homebrew/opt/grep/libexec/gnubin:/opt/homebrew/bin/:$PATH"

#For aerc
export TMPDIR=/users/faucherd/Downloads/tmp
