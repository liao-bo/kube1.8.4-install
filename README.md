### 环境变量:dev/group_vars/all
### 主机列表:dev/hosts
### 目前支持安装的版本有【1.7.4；1.8.4】
### 安装:
         ansible-playbook -i dev/hosts k8s-install.yml \
             --extra-vars "install_or_uninstall=install kubernetes_version=1.8.4" \
             --private-key=/home/admin/.ssh/id_rsa 
### 卸载:
         ansible-playbook -i dev/hosts k8s-uninstall.yml \
             --extra-vars install_or_uninstall=uninstall \

### 安装helm:
         ansible-playbook -i dev/hosts helm.yml \
             --extra-vars "install_or_uninstall=install kubernetes_version=1.8.4" \
             --private-key=/home/admin/.ssh/id_rsa         
