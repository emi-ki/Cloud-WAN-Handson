# Cloud-WAN-Handson
## はじめに
以下のイベントで AWS Cloud WAN の簡易ハンズオンを実施するために本コンテンツを用意しています。

AWS エバンジェリストシリーズ　AWSの基礎を学ぼう　特別編 Cloud WAN  
https://awsbasics.connpass.com/event/256839/  

元になる手順は私が会社の技術ブログとして執筆した以下ブログです。  
[AWS Cloud WAN を使ってマルチリージョンの VPC 間で疎通確認する手順](https://blog.serverworks.co.jp/cloud-wan-vpc)  

## AWS Cloud WAN 概要
上記ブログの冒頭を見ながら概要を確認します。
[AWS Cloud WAN 概要](https://blog.serverworks.co.jp/cloud-wan-vpc#AWS-Cloud-WAN-%E6%A6%82%E8%A6%81)

## 最終構成図
ハンズオン終了時点で以下のような構成になります。
![image](https://user-images.githubusercontent.com/86865300/187497711-64797d41-1ce3-4c03-81bd-ad1e15e07924.png)

本番環境 Prod セグメントネットワークに所属する VPC 間の疎通確認と、開発環境 Dev セグメントネットワークに所属する VPC 間の疎通確認ができることをゴールとします。
![image](https://user-images.githubusercontent.com/86865300/187498113-afdfa1c2-a876-4af4-b23c-7e61bd68dbbe.png)


## 事前準備

事前に用意しておくリソースを、以下の CloudFormationテンプレートで作成します。
- 東京リージョンで展開
   - Cloud-WAN-handson-Tokyo.yml
- バージニア北部リージョンで展開
   - Cloud-WAN-handson-Virg.yml

以下のリソースが作成されます。

![image](https://user-images.githubusercontent.com/86865300/187493238-db8b0de4-3750-49c1-b1fd-d4aa952cc50a.png)

## 注意
- 各リージョンに VPC が 2 つ作成されます
   - 上記 CloudFormation テンプレートを展開すると、東京リージョンに 2 つ、バージニア北部リージョンに 2 つ VPC が作成されます。
   - 各リージョンに作成できる VPC の数は、上限緩和申請をしていなければデフォルトで 5 つまでです。
   - 既にご自身の AWS アカウントの東京リージョン、バージニア北部リージョンに 4 つ以上 VPC が存在する場合、 CloudFormation スタックの展開でエラーになります。
- 同名の IAM ロールが存在する
   - ※検証中
