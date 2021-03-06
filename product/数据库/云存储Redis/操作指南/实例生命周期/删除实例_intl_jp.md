﻿##　操作シナリオ
サービスの必要に応じて、従量課金や年払い（月払い）のインスタンスを手動で破棄することができます。
- 従量課金は後払いとも呼ばれます。つまり、予め必要に応じてリソースの使用を申請し、精算時には実際に使用したリソースの量に応じて料金を支払います。インスタンスを返却する必要がある有場合、そのインスタンスを破棄することができます。破棄した後、そのインスタンスに対してはいかなる料金も発生しません。
- 年払い（月払い）は先払い形式です。年払い（月払い）でデータベースを購入して、何らかの理由で満足できなかった場合、セルフサービスによる返品と返金に対応しています。
>!インスタンスを破棄すると全てのデータが消去され、復元することはできません。必ずデータをバックアップしてから破棄してください。


## 操作手順

### 従量課金の破棄
1. [Redis コンソール](https://console.cloud.tencent.com/redis)にログインします。
2. 【インスタンスリスト】で破棄するインスタンスを選択し、【操作】から【詳細】>【破棄】を選択します。
3. ポップアップされた破棄ページで【OK】をクリックします。
![](https://main.qcloudimg.com/raw/2d67cd624be0838d60a31ac2e6ad1a75.png)

### 年払い（月払い）の破棄
1. 【インスタンスリスト】で破棄するインスタンスを選択し、【操作】から【詳細】>【返品と返金】を選択します。
![](https://main.qcloudimg.com/raw/e695799495e7672fcd6de1ef046a8486.png)
>? 【返品と返金】ボタンが使用できない場合、そのアカウントは既に年払い（月払い）のセルフサービスによる返却の限度枠を使用済みであることを示しています。そのインスタンスは手動で破棄することはできず、期限を過ぎた後に自動で破棄されます。
2. ポップアップされた破棄ページで「確認の上同意する」にチェックを入れ、【OK】をクリックします。
>? 
>- 破棄を送信した後、インスタンスはごみ箱に7日間保存されるため、すぐにリサイクルすることができます。
>- リソースの破棄後、返金される金額は、購入時の支払いに使用した現金や現金ギフトの比率に応じて、ユーザーの Tencent Cloud アカウントに返還されます。
>- 購入時に割引またはクーポン券を使用した場合、割引やクーポン券は返還されません。

