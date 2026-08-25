# Hi there, I'm Yoshitsugu Seki (関 良嗣) 👋

<p align="center">
  <a href="https://www.threenext.com/"><img src="https://img.shields.io/badge/Company-Three%20Next%20Co.,%20Ltd.-blue?style=for-the-badge&logo=building" alt="Company"></a>
  <a href="https://x.com/yoshis2"><img src="https://img.shields.io/badge/X-@yoshis2-black?style=for-the-badge&logo=x" alt="X"></a>
  <a href="https://lit.link/yoshis2"><img src="https://img.shields.io/badge/Lit.link-yoshis2-2b3a4a?style=for-the-badge&logo=link" alt="Lit.link"></a>
</p>

---

## 🚀 About Me

株式会社スリーネクスト（Three Next Co., Ltd.）代表取締役 兼 フルスタックエンジニアの **関 良嗣（Yoshitsugu Seki）** です。

20年以上にわたり、Webシステムのバックエンド開発、フロントエンド構築、データベース設計、インフラ・セキュリティ運用の現場第一線でコードを書き続けてきました。

現在は、Web3 / Fintech領域における現場のリアルな課題を解決するため、**ステーブルコイン請求書自動消込SaaS「LedgerRoute（レジャールート）」** を自社開発・運営しています。企画・設計・実装からクラウド/エッジインフラの構築まで、すべての工程を自ら牽引しています。

---

## 💡 What I'm Working On

### 1. 🚀 ステーブルコイン請求書自動消込SaaS「LedgerRoute」
企業間取引におけるステーブルコイン（USDT, USDC, DAI等）決済と、オンチェーンデータ・請求書の自動消込処理をシームレスにつなぐBtoB SaaSプロダクト。

* **課題**: ブロックチェーン上の送金データと会計・請求データの消込手作業によるコストとミスの発生
* **ソリューション**: オンチェーンイベントの自動検知、スマートコントラクト連携、請求データとの突き合わせ・会計システム連携の自動化

### 2. 🛡️ IT/DXコンサルティング & システム受託開発
長年培ったアーキテクチャ設計・パフォーマンス最適化・セキュリティの知見を活かし、企業のWeb3実装やDX支援、技術顧問を行っています。

---

## 🏗️ LedgerRoute System Architecture

`LedgerRoute`のアーキテクチャおよび決済・消込処理フローの概要図です。

```mermaid
graph TD
    subgraph Client Layer
        User[ユーザー / 企業経理担当]
        Customer[顧客 / 支払人]
    end

    subgraph Edge & Frontend Layer
        CF[Cloudflare Workers / CDN / WAF]
        NextJS[Next.js App Router / React]
    end

    subgraph Backend API Services
        GoAPI[Go / Golang Backend API Engine]
        PHPService[PHP / Batch Processing & Integration]
    end

    subgraph Data Store & Cache
        PostgreSQL[(PostgreSQL / Relational Data)]
        MySQL[(MySQL / Transaction Logs)]
        NoSQL[(Redis / Cache & Queue)]
    end

    subgraph Blockchain & Web3 Networks
        USDT[USDT Smart Contract]
        USDC[USDC Smart Contract]
        Indexer[On-Chain Data Indexer / Event Listener]
    end

    %% Flow Connections
    User -->|Dashboard Access| CF
    Customer -->|Pay Stablecoin| USDT
    Customer -->|Pay Stablecoin| USDC

    CF --> NextJS
    NextJS --> GoAPI

    GoAPI --> PostgreSQL
    GoAPI --> NoSQL
    PHPService --> MySQL

    USDT --> Indexer
    USDC --> Indexer
    Indexer -->|Event Webhook| GoAPI
    GoAPI -->|Auto Reconciliation| PostgreSQL

```

---

## 📈 My 20+ Years Tech Journey

これまでのエンジニアとしてのキャリアと技術スタックの変遷です。

```mermaid
timeline
    title 20+ Years Engineering Roadmap & Experience
    section 2000s Foundation
        2000s : PHP / Perl / C / MySQL
              : Webアプリケーション受託開発
              : データベース設計・大規模アクセス耐性構築
    section 2010s Fullstack & Cloud
        2010s : Modern PHP (Laravel) / JS / React / Vue / Nuxt
              : PostgreSQL / NoSQL (Redis, MongoDB)
              : AWS / GCP インフラ設計・DevOps推進
    section 2020s Web3 & Fintech
        2020s : Golang (Go) / Next.js / TypeScript
              : Cloudflare Workers / Edge / Security (WAF)
              : Blockchain / Smart Contracts / Stablecoin Protocols
    section 2026 Entrepreneurship
        2026  : 株式会社スリーネクスト 設立
              : ステーブルコイン請求書自動消込SaaS「LedgerRoute」開発・運営

```

---

## 🛠️ Tech Stack & Core Competencies

エンジニアとして20年間磨き上げてきた、実務で深く使いこなせる主要技術スタックです。

### 💻 Languages & Frameworks

* **Backend**: Golang (Go), PHP (Laravel / Native)
* **Frontend**: TypeScript, JavaScript, Next.js, React, Vue.js, Nuxt.js
* **Markup & Style**: HTML5, CSS3, Tailwind CSS, Sass

### 🗄️ Databases & Caching

* **Relational DB**: MySQL, PostgreSQL
* **NoSQL / In-Memory**: Redis, MongoDB, DynamoDB
* **NewSQL**:  

### ☁️ Cloud, Edge & Infrastructure

* **Cloud Providers**: AWS (EC2, S3, RDS, Lambda, ECS, CloudFront), GCP (Compute Engine, Cloud Run, BigQuery)
* **Edge & CDN**: Cloudflare (Workers, Pages, DNS, WAF, Turnstile, SSL/TLS)
* **DevOps & Containers**: Docker, CI/CD (GitHub Actions), Nginx, Linux Server Administration

### 🔗 Web3 & Security

* **Web3 / Fintech**: Ethereum / EVM Compatible Chains, Smart Contracts, ERC-20 (USDT/USDC/DAI), Web3.js / Ethers.js / Viem
* **Security & Network**: SSL/TLS Certificate Hardening (A+ Grade), DNSSEC, Core Web Vitals Optimization

---

## ⚡ Development & Architecture Philosophy

自社プロダクトおよび受託開発において徹底している3つの開発思想です。

```mermaid
flowchart LR
    A[超高速表示<br/>Performance First] --> B[堅牢な防衛<br/>Security & SSL A+]
    B --> C[現場主導<br/>BtoB UX Optimization]
    C --> D[確かな価値提供<br/>LedgerRoute]

```

1. **Performance First**: モバイル・デスクトップ問わず、表示速度・レスポンス速度を極限まで最適化
2. **Security & Reliability**: SSL/TLS A+ 評価、WAF、DNSSECの徹底によるゼロトラストに近い堅牢性確保
3. **BtoB UX Optimization**: 複雑なWeb3のデータ処理を、経理・財務現場が迷わず使えるシンプルなUIへ昇華

---

## 📫 Connect with Me

* **Corporate Site**: [https://www.threenext.com/](https://www.threenext.com/)
* **X (Twitter)**: [@yoshis2](https://www.google.com/url?sa=E&source=gmail&q=https://x.com/yoshis2)
* **LinkedIn**: [Yoshitsugu Seki](https://www.linkedin.com/)
* **Lit.link**: [lit.link/yoshis2](https://www.google.com/url?sa=E&source=gmail&q=https://lit.link/yoshis2)
* **Company**: 株式会社スリーネクスト（東京都港区六本木3-16-12 六本木KSビル5F）

---