# My docker Ansible runner
## How to
with this makefile and dockerfile i generate an docker image that I use as ansible package on my laptop and on other server


## Use it

Add the following codes in a bash alias file and then source it.

### ssh key usage 
in docker you can use your sshkey without copying it in the container (security feature)

To use your own sshkey and config file, be sure that you have 
- your ssh key loaded in ssh-agent 
- the agent socket declared in the $SSH_AUTH_SOCK environment variable 


## the bash aliases
''' bash
d-ans () 
{ 
    APP=ANSIBLE
    IMG=unclephil/ansible:latest
    del_stopped ${APP}
    echo "Launching ansible docker instance"
    docker pull ${IMG} >>/dev/null;
    if [[ $# -eq 0 ]]; then
        docker run --rm -it --name ${APP} -v ${PWD}:/ansible  -v $SSH_AUTH_SOCK:/tmp/ssh.sck -e SSH_AUTH_SOCK=/tmp/ssh.sck  ${IMG}
    fi;
    if [[ $# -gt 0 ]]; then
        ## docker run --rm --name ${APP} -v ${pwd}:/ansible/playbooks -v ${VSSH}:/root/.ssh ${IMG} $@;
        docker run --rm --name ${APP} -v ${PWD}:/ansible  -v $SSH_AUTH_SOCK:/tmp/ssh.sck -e SSH_AUTH_SOCK=/tmp/ssh.sck  ${IMG} $@
    fi
}
alias ansible='d-ans ansible $@'
alias ansible-config='d-ans ansible-config $@'
alias ansible-connection='d-ans ansible-connection $@'
alias ansible-console='d-ans ansible-console $@'
alias ansible-doc='d-ans ansible-doc $@'
alias ansible-galaxy='d-ans ansible-galaxy $@'
alias ansible-inventory='d-ans ansible-inventory $@'
alias ansible-lint='d-ans ansible-lint $@'
alias ansible-playbook='d-ans ansible-playbook $@'
alias ansible-pull='d-ans ansible-pull $@'
alias ansible-vault='d-ans ansible-vault $@'

'''
