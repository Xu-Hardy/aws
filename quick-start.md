# 快速开始

安装aws-cli

[北京区](https://console.amazonaws.cn/console/home?region=cn-north-1)

### 安装

> linux:
```bash
# x86
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# arm
curl "https://awscli.amazonaws.com/awscli-exe-linux-aarch64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

> MacOS

```
https://awscli.amazonaws.com/AWSCLIV2.pkg
```

### 配置


> 新建凭证
```bash
aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
Amazon Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: cn-north-1
Default output format [None]: json
```

> 复制现有凭证

～/.aws目录下有config和credentials文件，config保存的是region和output，credentials保存的是aws_access_key_id, aws_secret_access_key
```bash
(base) ➜  .aws cat config 
[default]
region = cn-north-1
output = json
(base) ➜  .aws cat credentials 
[default]
aws_access_key_id = 
aws_secret_access_key = 
```

> 通过CSV文件导入密钥对

```bash
aws configure import --csv file://credentials.csv
```

> 指定用户配置
```bash
aws s3 ls --profile produser
```

> 凭证优先顺序
1. 命令行选项 – 覆盖任何其他位置的设置。您可以在命令行上指定 --region、--output 和 --profile 作为参数。
2. 环境变量 – 您可以在系统的环境变量中存储值。
3. CLI 凭证文件和配置文件 – 在运行 credentials 命令时，将更新 config 和 aws configure 文件。
4. 容器凭证 – 您可以将 IAM 角色与每个 Amazon Elastic Container Service (Amazon ECS) 任务定义关联。
5. 实例配置文件凭证 – 您可以将 IAM 角色与每个 Amazon Elastic Compute Cloud (Amazon EC2) 实例关联。

```bash
# aws configure set
aws configure set region us-west-2
# aws configure get
aws configure get region

# 要列出所有配置数据，请使用 aws configure list 命令。此命令显示已配置的所有设置的 Amazon CLI 名称、它们的值以及已从中检索配置的位置。
aws configure list

# 要列出所有配置文件名称，请使用 aws configure list-profiles 命令。
aws configure list-profiles
```
