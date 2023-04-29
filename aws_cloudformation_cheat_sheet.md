## 1.Command Cheat Sheet
|function|description|required|example|
|:--|:--|:--|:--|
|Description|作成するテンプレートの説明を記載|||
|Resource|作成するリソースの詳細を記載|必須||

## 2.Command Cheat Sheet
|function|description|required|example|
|:--|:--|:--|:--|
|Description|作成するテンプレートの説明を記載|||
|Resource|作成するリソースの詳細を記載|必須||
|Outputs|# eksctl get cluster|||
|Metadata|テンプレートに対する追加情報を記載|||
|Parameters|実行時にユーザ入力を求める|||
|Mappings|キーと値をマッピング|||
|Conditions|条件名と条件判断内容を記載|||
|Transform|サーバレスアプリケーションの場合に必要|||

## 3.built-in function
### ※Used resource, outputs, metadata and updatepolciy.
|function|example|description|
|:--|:--|:--|
|Fn::Sub (!Sub)|!Sub arn:aws:iam::${AWS::AccountId}:role/myAmazonEKSClusterRole|特定した値の入力文字列にある変数の代わりに使う|
|Fn::Ref (!Ref)|!Ref [ResourceName]|特定した値の入力文字列にある変数の代わりに使う|
|Fn::GetAtt (!GetAtt)|!GetAtt [ResoruceName].[ResourceID]|テンプレートのリソースから属性値を返す|
|Fn::GetAZs||指定されたリージョンのアベイラビリティーゾーンを含んだ配列を返す|
|Fn::FindInMap||Mappiengsセクションでせんげんされた２つのレベルのマッピングのキーに対応する値を返す|
|Fn::Join (!Join)|!Join [ , ]|2つの値を結合する|
|Fn::Equals||2つの値が等しいかどうかを判定|
|Fn::If||指定された条件からtrueかfalseを返す|
|Fn::Not||falseと評価された条件に対しtrueで返す|
|Fn::And|||
|Fn::Or|||
|Fn::ImportValue|||
|Fn::Select|||
|Fn::Split||文字列をリストに分割|
|Fn::Transform||スタックテンプレートの一部に対してカスタム処理を実行するためのマクロを指定する|
|Fn::Base64||UserDataを介してEC2インスタンスにデータを渡すために使用|

## 4.built-in function
```
Parameters:
  VpcBlock:
    Type: String
    Default: 192.168.0.0/16
    Description: The CIDR range for the VPC. This should be a valid private (RFC 1918) CIDR range.
```