## usersテーブル ##

| Column             | Type      | Option                           |
| ------------------ | --------- | -------------------------------- |
| email              | string    | null: false, ユニーク制約         |
| encrypted_password | string    | nul: false                       |
| name               | string    | null: false                      |
| profile            | text      | null: false                      |
| occupation         | text      | null: false                      |
| position           | text      | null: false                      |

### Association ###
- has_many :prototypes
- has_many :comments
- belongs_to :


## prototypesテーブル ##

| Column     | Type      | Option                         |
| ---------- | --------- | ------------------------------ |
| title      | string    | null: false                    |
| catch_copy | text      | null: false                    |
| concept    | text      | null: false                    |
| user       | reference | null: false, foreign_key: true |

### Association ###
- belongs_to :user
- has_many :comments


## commentsテーブル ##
| Column    | Type      | Option                             |
| --------- | --------- | ---------------------------------- |
| content   | text      | null: false                        |
| prototype | reference | null: false, foreign_key: true     |
| user      | reference | null: false, foreign_key: true     |

### Association ###
- belongs_to :user
- belongs_to :prototype