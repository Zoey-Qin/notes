# 1. Ansible 的目录结构

列出 ansible 所有文件存放目录

```
rpm -ql ansible
```

![img](assets/epub_845384_25.jpeg)

​	

- 配置文件目录：/etc/ansible
  - 主要功能为：Inventory 主机信息配置、Ansible 工具功能配置等
  - 所有 ansible 的配置均放在该目录下
- 执行文件目录：/usr/bin
  - 主要功能为：ansible 系列命令默认存放目录
  - ansible 所有的可执行文件放在该目录下



# 2. 配置文件解析

- inventory 用于定义 ansible 的主机列表配置
- ansible 自身的配置文件只有一个，即 ansible.cfg，ansible 安装好后它默认存放于 /etc/ansible 目录下
  ansible.cfg 可以存在于多个地方，ansible 读取配置文件的顺序依次是执行目录 --> 用户家目录下的 --> /etc/ansible.cfg，先找到哪个就用哪个配置
  ansible.cfg 配置中的所有内容均可在命令行通过参数的形式传递或定义在 playbooks 中
