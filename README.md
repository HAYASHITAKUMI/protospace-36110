# README


## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| password           | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |

### Association
- has_many :contents
- has_many :prototypes


## contents テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references |                                |
| prototype | references |                                |

### Association
- belongs_to :users
- belongs_to :prototypes



## prototypes テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| image      |            | ActiveStorage                  |
| user       | references |                                |

### Association
- has_many :users
- has_many :contents


ユーザー登録に必要な情報	条件	必須か否か
メールアドレス	string型、カラム名はemail。Deviseのデフォルトの記述を使用	必須
パスワード	string型、カラム名はencrypted_password。Deviseのデフォルトの記述を使用	必須
ユーザー名	string型、カラム名はname	必須
プロフィール	text型、カラム名はprofile	必須
所属	text型、カラム名はoccupation	必須
役職	text型、カラム名はposition	必須