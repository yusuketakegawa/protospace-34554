#テーブル設計

## users テーブル

| Colum     |  Type     | Option     |
|---------- |-----------| ---------- | 
| email     |  string   | null: false|
| password  |  string   | null: false|
| name      |  string   | null: false|
| profile   |  text     | null: false|
| occupation|  text     | null: false|
| position  |  text     | null: false|

### Association
-has many :prototypes
-has many :comments

## prototypes テーブル

| Colum     |  Type      | Option                         |
|---------- |------------| ------------------------------ | 
| title     |  string    | null: false                    |
| catch_copy|  text      | null: false                    |
| concept   |  text      | null: false                    |
| user      |  references| null: false, foreign_key: true |

-has many :comments
-belongs_to :user

## comments テーブル

| Colum     |  Type     | Option                          |
|---------- |--------------| -----------------------------| 
| text      |  text        | null: false                  |
| user      |  references  | ull: false, foreign_key: true|
| prototype |  references  | ull: false, foreign_key: true|

belongs_to :user
belongs_to :prototypes
