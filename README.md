# AdGuard DNS Divert

AdGuard DNS Divert 项目为 [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) 用户提供的一套**基于域名分类分流国内外 DNS**的轻量级方案，提升访问速度、保护隐私，并优化解析体验。

The AdGuard DNS Divert project provides a lightweight solution for [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) users to **automatically route DNS queries based on domain categorization (domestic/foreign)**, improving speed, privacy, and DNS resolution efficiency.

---

## 功能特性 | Features

- 📦 **零部署**：无需本地运行环境，直接 Fork 后在线配置。
- 🔄 **自动更新**：通过 GitHub Actions 定时拉取最新域名列表并生成规则。
- 🔧 **高度自定义**：可灵活指定国内外 DNS 服务器、自定义域名走向。
- 🛡 **智能分流**：自动区分国内外域名，实现最佳 DNS 解析路径。
- 📝 **两种分流模式**：支持黑名单模式与白名单模式灵活切换。

- 📦 **Zero Deployment**: Configure directly after forking, no local environment needed.
- 🔄 **Automatic Updates**: Regularly fetches the latest domain lists via GitHub Actions.
- 🔧 **Highly Customizable**: Freely specify domestic and foreign DNS servers and domain routing.
- 🛡 **Smart Diversion**: Automatically distinguishes domestic and foreign domains for optimal DNS resolution.
- 📝 **Two Diversion Modes**: Supports flexible switching between blacklist mode and whitelist mode.

---

## 快速开始 | Quick Start

### 1. Fork 仓库 | Fork the Repository

点击右上角的 **Fork** 按钮，将本项目复制到你的 GitHub 账户。  
Click the **Fork** button at the top right to copy this repository to your GitHub account.

### 2. 修改配置文件 | Edit Configuration Files

在你的 Fork 仓库中，按需编辑 `config/` 目录下的以下文件：

Edit the following files under the `config/` directory in your forked repository:

| 文件 | File | 描述 | Description |
|:---|:---|:---|:---|
| [`config.json`](config/config.json) | [`config.json`](config/config.json) | 主配置文件，设置行为和生成参数 | Main config file: control behaviors and output settings |
| [`cn_dns.txt`](config/cn_dns.txt) | [`cn_dns.txt`](config/cn_dns.txt) | 国内 DNS 服务器列表 | List of domestic (CN) DNS servers |
| [`foreign_dns.txt`](config/foreign_dns.txt) | [`foreign_dns.txt`](config/foreign_dns.txt) | 国外 DNS 服务器列表 | List of foreign DNS servers |
| [`custom_cn_domains.txt`](config/custom_cn_domains.txt) | [`custom_cn_domains.txt`](config/custom_cn_domains.txt) | 自定义始终走国内 DNS 的域名列表 | Custom list of domains always resolved via domestic DNS |
| [`custom_foreign_domains.txt`](config/custom_foreign_domains.txt) | [`custom_foreign_domains.txt`](config/custom_foreign_domains.txt) | 自定义始终走国外 DNS 的域名列表 | Custom list of domains always resolved via foreign DNS |

可以直接在 GitHub 上在线编辑并保存。  
Edit and save them directly through GitHub's web interface.

---

## 分流模式说明 | Diversion Modes

项目生成两种分流规则文件，可根据需求选择：

This project generates two types of diversion rules; you can choose based on your needs:

| 文件 | File | 描述 | Description |
|:---|:---|:---|:---|
| `blacklist_mode.txt` | `blacklist_mode.txt` | **命中列表中域名的请求走国外 DNS。** | **Domains matching the list will be resolved via foreign DNS.** |
| `whitelist_mode.txt` | `whitelist_mode.txt` | **命中列表中域名的请求走国内 DNS。** | **Domains matching the list will be resolved via domestic DNS.** |

**根据不同需求选择合适的模式。**  
**Choose the appropriate mode based on your needs.**

---

## 触发规则生成 | Trigger Rule Generation

- GitHub Actions 将每天定时（UTC 0 点）自动执行更新；
- 也可以手动进入 **Actions** → 找到 **Update Rules** → 点击 **Run workflow** 手动触发。

- GitHub Actions automatically runs daily (at UTC 00:00);
- You can also manually trigger it by going to **Actions** → selecting **Update Rules** → clicking **Run workflow**.

---

## 集成到 AdGuard Home | Integrate into AdGuard Home

将生成的分流规则导入 AdGuard Home，自定义 DNS 服务器设置，实现智能分流解析。  
Import the generated diversion rules into AdGuard Home, customize DNS server settings, and achieve intelligent resolution.

---

## 上游规则来源 | Upstream Rule Sources

本项目基于以下规则源生成国内外域名分类：

This project generates domain categorizations based on the following upstream sources:

- [ACL4SSR/ChinaDomain](https://github.com/ACL4SSR/ACL4SSR)  
- [ACL4SSR/ChinaMedia](https://github.com/ACL4SSR/ACL4SSR)
- [blackmatrix7/ChinaMax_Domain](https://github.com/blackmatrix7/ios_rule_script)
- [felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)
- [blackmatrix7/Proxy_Domain](https://github.com/blackmatrix7/ios_rule_script)
- [ACL4SSR/ProxyGFWlist](https://github.com/ACL4SSR/ACL4SSR)
- [ACL4SSR/ProxyMedia](https://github.com/ACL4SSR/ACL4SSR)
- [gfwlist/gfwlist](https://github.com/gfwlist/gfwlist)

感谢以上项目提供的开放规则资源！  
Thanks to all these projects for providing open rule resources!

---

## 致谢 | Acknowledgments

特别感谢以下项目及其开发者：

Special thanks to the following projects and developers:

- [ACL4SSR](https://github.com/ACL4SSR/ACL4SSR)
- [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script)
- [felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)
- [gfwlist](https://github.com/gfwlist/gfwlist)

以及所有为互联网自由与开源生态贡献力量的人们。  
And to everyone contributing to Internet freedom and the open-source ecosystem!

---

## 许可证 | License

本项目基于 [GPL v3 License](LICENSE)。  
This project is licensed under the [GPL v3 License](LICENSE).
