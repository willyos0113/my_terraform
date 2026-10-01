# Terraform AWS GitLab Server

本專案使用 Terraform 在 AWS 上自動部署 GitLab 伺服器。

## 📋 專案結構

```
my_terraform/
└── stage/
    ├── main.tf          # 主要基礎設施定義
    ├── variables.tf     # 變數定義
    ├── outputs.tf       # 輸出值
    └── .terraform.lock.hcl   # 依賴版本鎖定
```

## 🏗️ 部署的資源

- **VPC & Subnets**: 使用預設 VPC 和其子網
- **Security Group**: GitLab 伺服器的安全設定
  - SSH (22)、HTTP (80)、HTTPS (443)
- **EC2 Instance**: Ubuntu 20.04 t3.micro
- **Key Pair**: SSH 連接用的金鑰對
- **EBS Volume**: 30GB gp3 加密磁碟

## 📦 前置要求

- Terraform >= 1.0
- AWS CLI 已配置（profile: `course`）
- AWS 認證資訊設定完成

## 🚀 使用方式

### 初始化
```bash
cd stage
terraform init
```

### 預覽變更
```bash
terraform plan
```

### 部署基礎設施
```bash
terraform apply
```

### 清理資源
```bash
terraform destroy
```

## 🔒 安全注意事項

- `.gitignore` 已配置以排除敏感檔案
- SSH 私鑰會存儲在本地（不要提交到版本控制）
- terraform.tfstate 包含敏感信息（不要上傳到 Git）

## 📝 變數配置

修改 `stage/variables.tf` 中的預設值：
- `default_vpc_id`: AWS 帳戶的預設 VPC ID

## 📧 聯絡資訊

專案維護者：[你的名字]
