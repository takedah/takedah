# takeda_h

とある地方自治体の情報システム部門で働いている職員です。
ネットワーク技術、セキュリティ、AWS を中心に、地方自治や行政とデジタル技術の関わりに興味があります。

自治体情報システムの標準化に伴うガバメントクラウド（AWS）への移行に携わりました。移行後も、複数のベンダーと調整しながら、閉域ネットワークやマルチアカウント環境、コスト管理などに取り組んでいます。

業務で接する技術の仕組みを自分でも理解し、構成や運用について根拠を持って相談・判断できるようになりたいと考えています。自宅の検証ネットワークや個人の AWS アカウントで手を動かし、ドキュメントだけではつかみにくい通信の流れや設定の関係を確かめています。

検証で分かったことや試行錯誤したことは、Qiita の記事や勉強会での発表にまとめています。同じような課題に取り組む自治体職員や、自治体システムに関わる方の参考になればと思っています。

## 実務経験と担当範囲

情報システム部門で通算 10 年以上、庁内ネットワークや情報システムに関する業務に携わっています。

ガバメントクラウド（AWS）への移行では、自治体側の担当として、主に次の業務を行いました。

- ガバメントクラウドへの閉域接続に必要な、庁内側のネットワーク機器と DNS サーバーを設計・設定
- 複数のベンダーが利用する AWS アカウント間の接続とアクセス制御を調整（Transit Gateway のアタッチメント、ルーティング、名前解決、S3 のクロスアカウントアクセスなど）
- 共同利用方式を含む構成について、ベンダーとの役割分担や責任分界を調整
- リザーブドインスタンスや Savings Plans の購入を含む、クラウド利用料の管理

現在も、AWS 環境を含むネットワークやアクセス権限に関するトラブルシューティングを行い、各ベンダーからの技術的な相談にも対応しています。

### 手がけた課題の例

移行時に取り組んだ課題の例を紹介します。

- 共同利用方式の各環境に対し、庁内のオンプレミス環境から名前解決できるよう、DNS クエリの転送先を設計しました。（庁内 DNS の条件付きフォワーダー、Route 53 Resolver のインバウンドエンドポイント、プライベートホストゾーン）
- AWS 外の環境と S3 バケットの間でデータを連携するため、アクセス制御と接続・転送方式を設計・調整しました。連携方式に応じて、バケットポリシー、KMS キーポリシー、VPC エンドポイント、AWS Transfer Family による SFTP を扱いました。

## 興味のあること

- **ネットワーク**
  - オンプレミスと AWS をつなぐ閉域のハイブリッドネットワーク
  - Transit Gateway、VPN、Route 53 Resolver による接続・名前解決
  - 自治体の三層分離とクラウド利用の関係
- **セキュリティ**
  - IAM Identity Center などを使った認証・認可
  - マルチアカウント環境でのアクセス制御や暗号化
  - 閉域環境でのサービス利用と、生成 AI における機密情報の扱い
- **AWS の運用と活用**
  - Organizations、SCP を使ったマルチアカウント管理
  - Savings Plans、リザーブドインスタンスなどによるコスト最適化
  - Amazon Bedrock / AgentCore などを使った生成 AI の検証
- **行政とデジタル技術**
  - ガバメントクラウドと自治体情報システムの標準化
  - 自治体がクラウドを利用する際の技術・運用・費用の課題
  - ガバメント AI「源内」など、行政での生成 AI 活用の可能性

## 検証・発信していること

### 閉域ネットワークと AWS

インターネット接続を前提とした構成とは異なる、閉域環境ならではの接続や名前解決を検証しています。オンプレミスと AWS の接続、複数アカウント間の通信、VPC エンドポイント経由でのサービス利用などを、実際に構築して確かめています。

### 自治体職員の視点からのガバメントクラウド

自治体が AWS を利用する際に理解しておきたい仕組みや、関係者との調整が必要になる点を整理しています。ネットワーク、権限管理、コストなどについて、技術と自治体での運用を結び付けながら発信しています。

### 行政での生成 AI 活用

ガバメント AI「源内」や Amazon Bedrock などを題材に、閉域環境で生成 AI を利用するための構成を試しています。生成 AI を動かすための技術とともに、自治体で活用する際の課題や可能性についても考えています。

## アウトプット

検証の手順や技術的な気づきは Qiita に、勉強会で発表した資料は Speaker Deck に公開しています。

- [Qiita](https://qiita.com/takeda_h)
- [Speaker Deck](https://speakerdeck.com/takeda_h)

### 主な記事

- [自治体職員がガバメントクラウドの AWS 環境を理解するのに助けになった知識 n 選（閉域マルチアカウントのネットワーク関連多め）](https://qiita.com/takeda_h/items/9f264464ea3cc3c55f11)
  - ガバメントクラウドの AWS 環境を理解するのに役立った知識を、ガバナンス、ネットワーク、コストの観点から自治体職員向けにまとめています。
- [閉域オンプレミスと AWS のハイブリッド構成における Route 53 アウトバウンド・インバウンドエンドポイントの名前解決パターンを構築してみる](https://qiita.com/takeda_h/items/bd7269a539079daeaa5d)
  - オンプレミスと AWS 間の DNS の動きを、検証環境を構築しながら整理しています。
- [ガバメント AI「源内」（genai-web）を閉域の AWS 環境へデプロイしてみた](https://qiita.com/takeda_h/items/47fce84d66bae672d744)
  - デジタル庁が公開した「源内」を、閉域の AWS 環境で動かせるように構成を変えてデプロイした記録です。

### 登壇

| 日付 | イベント | 発表資料 |
| --- | --- | --- |
| 2026-08-07 | [Gov-JAWS#8 JAWS-UG AI/ML支部コラボ：源内ハンズオン勉強会](https://gov-jaws.connpass.com/event/401100/) | [ガバメント AI 源内を地方自治体は活用できるのか 可能性と課題、期待について](https://speakerdeck.com/takeda_h/gabamento-ai-yuan-nei-wodi-fang-zi-zhi-ti-hahuo-yong-dekirunoka-ke-neng-xing-toke-ti-qi-dai-nituite) |
| 2026-05-25 | [第48回 JAWS-UG札幌支部 x 秋田支部 コラボ勉強会](https://jawsug-sapporo.connpass.com/event/390989/) | [自治体のガバメントクラウド AWS 移行で経験した大変だったことと今後の展望について](https://speakerdeck.com/takeda_h/zi-zhi-ti-nogabamentokuraudo-aws-yi-xing-de-jing-yan-sitada-bian-datutakototojin-hou-nozhan-wang-nituite) |
| 2026-03-17 | [Gov-JAWS#6](https://gov-jaws.connpass.com/event/385581/) | [ガバメントクラウドにおける AWS の長期継続割引について](https://speakerdeck.com/takeda_h/gabamentokuraudoniokeruawsnochang-qi-ji-sok-ge-yin-nituite) |
| 2025-08-20 | [Gov-JAWS#3](https://gov-jaws.connpass.com/event/363635/) | [自治体職員がガバクラの AWS 閉域ネットワークを理解するのにやって良かった個人検証環境](https://speakerdeck.com/takeda_h/zi-zhi-ti-zhi-yuan-gagabakurano-aws-bi-yu-netutowakuwoli-jie-surunoniyatuteliang-katutage-ren-jian-zheng-huan-jing) |
| 2024-12-18 | [第4回 自治体システム標準化・ガバメントクラウド勉強会](https://gov-cloud.connpass.com/event/339148/) | [発表資料（Route 53 による名前解決の集約）](https://speakerdeck.com/takeda_h/20241218-di-4hui-zi-zhi-ti-sisutemubiao-zhun-hua-gabamentokuraudomian-qiang-hui-fa-biao-zi-liao) |

## 資格

### 情報処理技術者試験など

- 情報処理安全確保支援士試験合格
- ネットワークスペシャリスト試験合格

### AWS 認定・AWS Skill Builder（取得日）

- AWS Certified Advanced Networking – Specialty（2024-06-08）
- AWS Certified Solutions Architect – Professional（2025-04-19）
- AWS Certified Solutions Architect – Associate（2023-09-09）
- AWS Application Networking Demonstrated（2026-04-24）
- AWS Incident Response Demonstrated（2026-05-01）
- AWS Serverless Demonstrated（2026-08-29）

<p>
  <a href="https://www.credly.com/org/amazon-web-services/badge/aws-certified-advanced-networking-specialty"><img src="https://images.credly.com/images/4d08274f-64c1-495e-986b-3143f51b1371/image.png" alt="AWS Certified Advanced Networking – Specialty" width="100"></a>
  <a href="https://www.credly.com/org/amazon-web-services/badge/aws-certified-solutions-architect-professional"><img src="https://images.credly.com/images/2d84e428-9078-49b6-a804-13c15383d0de/image.png" alt="AWS Certified Solutions Architect – Professional" width="100"></a>
  <a href="https://www.credly.com/org/amazon-web-services/badge/aws-certified-solutions-architect-associate"><img src="https://images.credly.com/images/0e284c3f-5164-4b21-8660-0d84737941bc/image.png" alt="AWS Certified Solutions Architect – Associate" width="100"></a>
  <a href="https://www.credly.com/org/amazon-web-services/badge/aws-application-networking-demonstrated"><img src="https://images.credly.com/images/ed8cf03b-6269-4265-a65b-68e67e49ce6b/blob" alt="AWS Application Networking Demonstrated" width="100"></a>
  <a href="https://www.credly.com/org/amazon-web-services/badge/aws-incident-response-demonstrated"><img src="https://images.credly.com/images/8dd6f516-0dd3-4b5e-aacf-8e86e737a95d/blob" alt="AWS Incident Response Demonstrated" width="100"></a>
  <a href="https://www.credly.com/org/amazon-web-services/badge/aws-serverless-demonstrated"><img src="https://images.credly.com/images/b3885091-25bc-42d0-8989-34cca82f3056/blob" alt="AWS Serverless Demonstrated" width="100"></a>
</p>

---

ここで発信している内容は個人の見解であり、所属組織の公式見解ではありません。
