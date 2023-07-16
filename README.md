# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |

### Association
- has_many : tweets


## tweets テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |
| text   | string | null: false |
| image  | text   | null: false |

### Association
- has_many : comments
- belongs_to : user


## comments テーブル

| Column    | Type       | Options                        |
| ------    | ---------- | ------------------------------ |
| user      | references | null: false, foreign_key: true |
| comment   | text       | null: false,                   |

### Association
- belongs_to : user
- belongs_to : tweet