# テーブル設計

## users テーブル

| Column     | Type   | Option   |
| ---------- | ------ | -------- |
| email      | string | not null |
| password   | string | not null |
| name       | string | not null |
| profile    | text   | not null |
| occupation | text   | not null |
| position   | text   | not null |

### Association

- has_many :prototypes
- has_many :comments

## prototypes　テーブル

| Column     | Type       | Options  |
| ---------- | ---------- | -------- |
| title      | string     | not null |
| catch_copy | text       | not null |
| concept    | text       | not null |
| image      | null       | null     |
| user       | references | null     |

### Association

- belongs_to :users
- has_many :comments

## comments　テーブル

| Column    | Type       | Options  |
| --------- | ---------- | -------- |
| text      | text       | not null |
| user      | references | null     |
| prototype | references | null     |

### Association

- belongs_to :users
- belongs_to :prototypes