## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|

### Association
- has_many :groups_users
- has_many :users, through: :groups_users
- has_many :messages

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|index: true|
|mail|string|
|password|string|

### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages
## messageテーブル

|Column|Type|Options|
|------|----|-------|
|image|string|
|content|string|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
