
Edit .tmux.conf file (taken from https://gist.github.com/andreyvit/2921703 )

    # remap prefix to Control + a
    set -g prefix C-a
    # bind 'C-a C-a' to type 'C-a'
    bind C-a send-prefix
    unbind C-b
