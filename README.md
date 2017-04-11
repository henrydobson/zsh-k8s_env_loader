# K8s Environment Loader for ZSH

## With Prezto

```bash
mkdir -p ~/.zfunc
git clone git@github.com:henrydobson/zsh-k8s_env_loader.git ~/.zfunc/k8s
cat << EOF >> ~/.zpreztorc
# Custom scripts

autoload -U compinit && compinit

if [ -d $HOME/.zfunc ]; then
        fpath=($HOME/.zfunc "${fpath[@]}")
        if [ -d $HOME/.zfunc/k8s ]; then
                fpath=($HOME/.zfunc/k8s "${fpath[@]}")
                autoload k8s_set_env _profile_completion
                compdef _profile_completion k8s_set_env
        fi
fi
EOF
```

## Configuration and usage

```bash
mkdir -p ~/.kube
touch ~/.kube/config
# add your k8s config
```
