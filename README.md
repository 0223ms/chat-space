## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|

### Association
- has_many :groups_users
- belongs_to :user, through: :groups_users

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|
|mail|string|
|password|string|

### Association
- has_many :groups_users
- has_many :groups, through: :groups_users

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|content|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- has_many :users
- has_many :groups
