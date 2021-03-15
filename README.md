# テーブル設計

## userテーブル

| Columns    | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :comments
- has_many :prototypes

## commentsテーブル

| Columns   | Type       | Options     |
| --------- | ---------- | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |
 
### Association

- belongs_to :user
- belongs_to :comment

## prototypesテーブル

| Columns    | Type       | Options     |
| ---------- | ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| image      |            |             |
| user       | references |             |

### Association

- belongs_to :user
- has_many :comments

