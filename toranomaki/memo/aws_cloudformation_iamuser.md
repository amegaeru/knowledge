```
{
    "AWSTemplateFormatVersion": "2010-09-09",
    "Description": "Template for creating Initial IAM",
    "Resources": {
        "IAMGrouopInitialAdmin": {
            "Type": "AWS::IAM::Group",
            "DeletionPolicy": "Retain",
            "Properties":{
                "GroupName":{"Fn::Join" : [
                        "",
                        ["demo-admin-group-", {"Ref": "AWS::AccountId"}]
                    ]},
                "ManagedPolicyArns": [
                    "arn:aws:iam::aws:policy/AdministratorAccess"
                ]
            }
        },
        "IAMUserInitialAdmin": {
            "Type": "AWS::IAM::User",
            "DeletionPolicy": "Retain",
            "Properties":{
                "UserName": {"Fn::Join" : [
                    "",
                    ["demo-iniadmin-user-",{"Ref": "AWS::AccountId"}]
                    ]},
                "Groups":[{"Fn::Join" : [
                    "",
                    ["demo-admin-group-",{"Ref": "AWS::AccountId"}]
                    ]}
                ]
            }
        }
    },
    "Outputs": {
        "UserName": {
            "Description": "Information about User name",
            "Value": { "Ref" : "IAMUserInitialAdmin" }
        },
        "PasswordSettingURL": {
            "Description": "Please create a password at the URL",
            "Value": {"Fn::Join": [
                "",
                ["https://","console.aws.amazon.com/iam/home?region=",{ "Ref": "AWS::Region" },"#/users/", {"Ref": "IAMUserInitialAdmin"},"?section=security_credentials"]
                ]}
        },
        "LoginURL": {
            "Description": "Information about console login URL",
            "Value": {"Fn::Join" : [
                "",
                ["https://",{"Ref": "AWS::AccountId"},".signin.aws.amazon.com/console"]
                ]}
        }
    }
}
```
