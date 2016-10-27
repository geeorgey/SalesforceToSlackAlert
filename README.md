# SalesforceToSlackAlert
セールスフォースからSlackに通知を投げたい

# slackURLについて
こちらにはWebhookのURLをかいてください

# class Oppty内ついて
label=の部分に書く内容は任意です。プロセスビルダーで読み込まれます。

# slackに投げられるテキストの形式について
		msg.put('text',  + '商談所有者: * ' + o.OwnerLastName + ' ' + o.OwnerFirstName + '* \n完了予定日: *' + String.valueOf(o.closeDate) + '* \n金額: * ¥' + o.Amount.format() +  '* \nURL：https://ここは自分の設定で書き換える.my.salesforce.com/' + o.oppID + '\n 取引先名： *' + o.Account + '* \nフェーズ： *' + o.oppPhase +'* \n商談名： * ' + o.oppName + '* \n -----------------------')
こんな感じにしています。
attachmentsを使うともう少しきれいに出せるのですが、内容が長くなるとload moreとなって内容が畳まれてしまうためこんな形にしました。
attachmentsを使う場合はJSONをネストする必要があります。書き方についてはこちらを参照ください：https://foobarforce.com/2014/07/25/apex-method-of-the-day-json-serialize-object/

