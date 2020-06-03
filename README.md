## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, and_index: true|
|email|string|null: false, unique: true|
|password|string|null: false|
|password confirmation|string|null: false|
### Association
- has_many :groups_users
- has_many :groups,trough: groups_users
- has_many :messages

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false,foreign_key: true|
### Association
belongs_to :group
belongs_to :user

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, unique: true|

## Association
- has_many :groups_users
- has_many :users,trough: groups_users
- has_many :messages

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false,foreign_key: true|
### Association
belongs_to :group
belongs_to :user

second