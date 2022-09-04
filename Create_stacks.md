# 事前準備 CloudFormation スタックの展開
事前に用意しておくリソースを、CloudFormationテンプレートで作成します。

## YAML ファイルのダウンロード
https://github.com/emi-ki/Cloud-WAN-Handson で YAML ファイルをダウンロードしてください。
![image](https://user-images.githubusercontent.com/86865300/188312958-20bae3e1-9a42-417c-8ba4-51b70024f209.png)

以下 2 つの YAML ファイルが含まれていることを確認してください。
- Cloud-WAN-handson-Tokyo.yml
- Cloud-WAN-handson-Virg.yml

## AWS CloudFormation コンソールでのスタックの作成
AWSマネジメントコンソールにログインしてください。

### 東京リージョンでの CloudFormation スタックの作成

東京リージョンで CloudFormation コンソール (https://console.aws.amazon.com/cloudformation) を開きます。

[スタックの作成] を選択します。  

- ステップ 1 テンプレートの指定
   - テンプレートの準備
      - テンプレートの準備完了
   - テンプレートの指定
      - テンプレートファイルのアップロード
      - ファイルの選択をクリックし、ダウンロードした **Cloud-WAN-handson-Tokyo.yml** を選択、[次へ]

- ステップ 2 スタックの詳細を指定
   - スタックの名前 
      -  **Cloud-WAN-handson-Tokyo**
   - パラメータ
      - 何も変更せず、[次へ]
- ステップ 3 スタックオプションの設定
   - 何も変更せず、[次へ]
- ステップ 4 レビュー
   - 画面最下部「AWS CloudFormation によって IAM リソースがカスタム名で作成される場合があることを承認します。」にチェックを入れ、[スタックの作成] 

作成したスタックが「CREATE_COMPLETE」になるまで 5 分ほど待ちます。完了を待たずに、バージニア北部リージョンでの CloudFormation スタックの作成に進んで構いません。
作成したスタックが「CREATE_COMPLETE」になれば、東京リージョンでの CloudFormation スタックの作成は完了です。

### バージニア北部リージョンでの CloudFormation スタックの作成

バージニア北部リージョンで CloudFormation コンソール (https://console.aws.amazon.com/cloudformation) を開きます。

[スタックの作成] を選択します。  

- ステップ 1 テンプレートの指定
   - テンプレートの準備
      - テンプレートの準備完了
   - テンプレートの指定
      - テンプレートファイルのアップロード
      - ファイルの選択をクリックし、ダウンロードした **Cloud-WAN-handson-Virg.yml** を選択、[次へ]

- ステップ 2 スタックの詳細を指定
   - スタックの名前 
      -  **Cloud-WAN-handson-Virg**
   - パラメータ
      - 何も変更せず、[次へ]
- ステップ 3 スタックオプションの設定
   - 何も変更せず、[次へ]
- ステップ 4 レビュー
   - 画面最下部「AWS CloudFormation によって IAM リソースがカスタム名で作成される場合があることを承認します。」にチェックを入れ、[スタックの作成] 

作成したスタックが「CREATE_COMPLETE」になるまで 5 分ほど待ちます。
作成したスタックが「CREATE_COMPLETE」になれば、バージニア北部リージョンでの CloudFormation スタックの作成は完了です。


※ 作成したスタックが「CREATE_COMPLETE」になった後、セッションマネージャーで EC2 インスタンスに接続できるまで約 5 分程度時間がかかる場合があります。これは SSM Agent が起動するまでに少し時間がかかるためです。

# 参考
[【AWS CloudFormation ユーザーガイド】AWS CloudFormation コンソールでのスタックの作成](https://docs.aws.amazon.com/ja_jp/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html)
