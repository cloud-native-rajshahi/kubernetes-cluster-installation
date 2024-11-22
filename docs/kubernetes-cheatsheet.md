**Table of Content:**
- [1. Kubernetes Cheat Sheet](#1-kubernetes-cheat-sheet)
  - [1.1. Vim profile setup](#11-vim-profile-setup)
  - [1.2. Kubectl autocomplete](#12-kubectl-autocomplete)
  - [1.3. Environment variable setup](#13-environment-variable-setup)
  - [1.4. Check Events](#14-check-events)
- [2. References](#2-references)



# 1. Kubernetes Cheat Sheet


## 1.1. Vim profile setup

```bash
cat <<EOF>~/.vimrc
set ts=2 sw=2 sts=2 et ai number colorcolumn=3,5,7,9
syntax on
colorscheme ron
EOF
# other options - paste, nopaste
# visual line(shift+v) / visual block(ctl+v) mode will help a lot to edit yaml config comfortably
```

## 1.2. Kubectl autocomplete

```bash
# ~/.bashrc # add autocomplete permanently to your bash shell.
source <(kubectl completion bash)
complete -F __start_kubectl k
EOF
```

## 1.3. Environment variable setup

```bash
cat <<EOF>kalias.sh
alias k="kubectl"
alias kgn="kubectl get node" 
alias aa='kubectl get all,sa,ep,sc,pv,pvc,cm,netpol'
alias kcc='kubectl config get-contexts'

# short alias to set/show context/namespace (only works for bash and bash-compatible shells, current context to be set before using kn to set namespace)
alias kx='f() { [ "$1" ] && kubectl config use-context $1 || kubectl config current-context ; } ; f'
alias kn='f() { [ "$1" ] && kubectl config set-context --current --namespace $1 || kubectl config view --minify | grep namespace | cut -d" " -f6 ; } ; f'

export do="--dry-run=client -o yaml"

source kalias.sh
```

## 1.4. Check Events 

```bash
k get ev -w

# get event by timestamp
k -n ns get events --sort-by='{.metadata.creationTimestamp}'
```







# 2. References
- https://kubernetes.io/docs/reference/kubectl/quick-reference/
- https://github.com/arif332/kubernetes-tutorial/blob/main/k8s-cli.md