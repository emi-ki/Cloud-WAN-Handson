# 「セッションが次の理由で終了されました。 NotFoundException: Key 'arn:aws:kms:region:account-id:key/xxxx' does not exist」

EC2 インスタンスにセッションマネージャーで接続する際、SSM のセッションマネージャー側の設定で KMS encryption が Enabled かつ KMS キーが無効化されていると、次のようなエラーが出る場合があります。

![image](https://user-images.githubusercontent.com/86865300/189295204-c42819d1-226d-4687-8f53-a5d2b88031cb.png)

デフォルトだと KMS encryption は Disabled なのですが、[AWS エバンジェリストシリーズ　AWSの基礎を学ぼう の 特別編 Systems Managerその１](https://awsbasics.connpass.com/event/253403/) に参加された方はこのエラーが出る可能性が高いです。

# 対処法
AWS コンソールで Systems Manaager コンソールに移動します。  
画面左のナビゲーションペインから [セッションマネージャー] - [設定]タブ を開くと、KMS encryption が Enabled になっています。  
[編集]  をクリックします。
![image](https://user-images.githubusercontent.com/86865300/189297253-52f8654a-11f2-4126-a681-37a4ac143878.png)

Enable KMS encryption のチェックを外します。

![image](https://user-images.githubusercontent.com/86865300/189297944-688efa13-42fc-41a3-8fb5-0da1e78be3f2.png)
![image](https://user-images.githubusercontent.com/86865300/189298110-acac8552-b136-4e5a-be8d-d2038672a5a5.png)
![image](https://user-images.githubusercontent.com/86865300/189298285-f6acff1a-41ce-4cdf-8a67-900f61f824d7.png)

画面をスクロールし、[保存] をクリックします。
緑のバーに「設定が正常に更新されました。」と表示され、 KMS encryption が Disabled になっていれば OK です。

![image](https://user-images.githubusercontent.com/86865300/189298470-a402ec94-c4f7-4303-a767-fdf24041512a.png)

再度、セッションマネージャーで EC2 インスタンスに接続してみてください。
