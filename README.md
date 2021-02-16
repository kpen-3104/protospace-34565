

# テーブルの設計


## usersテーブル
| Column     | type   | Option      |
| -----------|--------|-------------|
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |


### Association

- has_many :prototypes
- has_many :comments

## prototypesテーブル
| Column       | type         | Option                      |
| -------------|--------------|-----------------------------|
| title        | string       | null: false                 |
| catch_copy   | text         | null: false                 |
| concept      | text         | null: false                 |
| user         | references   | foreign_key: true           |

### Association
- belongs_to :user
- has_many   :comments



## commentsテーブル
| Column           | type         | Option           |
| -----------------|--------------|------------------|
| text             | text         | null: false      |
| user             | references   | foreign_key: true|
| prototype        | references   | foreign_key: true|


### Association
- belongs_to :user
- belongs_to :prototype




