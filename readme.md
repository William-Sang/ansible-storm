# 自动化部署storm

本脚本针对AWS一键搭建storm测试环境

## 使用配置过程
1. 新建AWS虚拟机时，为方便设置，针对内网开放所有端口（仅供测试）,对外开放8080
2. 修改hosts中的IP为AWS对应外网IP,并设置zookeeper_id(0-255)
3. 修改group_vars 中配置
    * SSH KEY 在本机的位置: ansible_ssh_private_key_file
    * ssh 连接的用户: ansible_ssh_user
    * storm 的下载连接: storm_download_url
    * storm 手动解压后的文件名: storm_dir
4. 在本机执行 ansible-playbook -i hosts site.yml

## 注意
* 由于使用的hostname 为aws内置的，所以不需要额外设置IP和hostname的映射关系
* OS为 Ubuntu 14.04 x64

## todo
* 针对虚拟机进行配置
* 添加vagrant支持
