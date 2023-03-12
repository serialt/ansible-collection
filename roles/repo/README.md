# Ansible Role: Base Repository

CentOS Base yum源配置，支持的yum源有：
* 阿里镜像源：https://mirrors.aliyun.com
* 华为镜像源：https://repo.huaweicloud.com
* 清华源： https://mirrors.tuna.tsinghua.edu.cn
* 北外镜像源：https://mirrors.bfsu.edu.cn
* 腾讯镜像源: https://mirrors.cloud.tencent.com

## 要求

此角色仅在CentOS 7及其衍生产品上运行。

## 测试环境

ansible `2.9.10`
os `CentOS 7.7.1908 X64`

## 角色变量

角色默认变量都放在 `defaults/main.yml`文件中:
```
# 两种方法可以任选一种，互斥
base_repofile: /etc/yum.repos.d/CentOS-Base.repo

# 方法一：
base_source_url: https://mirrors.aliyun.com
change_base: True

# 方法二：使用已经存在的配置文件
# 支持的参数： tsinghu, aliyun, huaweicloud, bfsu, tencent
use_local_repo_file: False
local_repofile: tencent

```

## 依赖

没有

## github地址
https://github.com/lework/Ansible-roles/tree/master/repo-epel

## Example Playbook

    - hosts: servers
      roles:
        - repo-base
    - host： servers
      roles:
        - {role: repo-base, base_source_url: "https://mirrors.tuna.tsinghua.edu.cn" }
