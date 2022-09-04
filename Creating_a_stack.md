# AWS CloudFormation コンソールでのスタックの作成

https://github.com/emi-ki/Cloud-WAN-Handson で

1. AWS CloudFormation コンソール (https://console.aws.amazon.com/cloudformation) を開きます。

2. 次のオプションのうち 1 つを使用して新しいスタックを作成します。

[Create Stack] を選択します。現在実行中のスタックがある場合は、これが唯一のオプションです。

[Stacks] (スタック) ページで [Create Stack] (スタックの作成) を選択します。このオプションは、実行中のスタックがない場合にのみ表示されます。








※ 作成したスタックが「CREATE_COMPLETE」になった後、セッションマネージャーで EC2 インスタンスに接続できるまで約 5 分程度時間がかかる場合があります。これは SSM Agent が起動するまでに少し時間がかかるためです。


# 参考
[【AWS CloudFormation ユーザーガイド】AWS CloudFormation コンソールでのスタックの作成](https://docs.aws.amazon.com/ja_jp/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html)
