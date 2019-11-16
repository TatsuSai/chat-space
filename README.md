# README

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belomgs_to :user


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique:true, index|

### Association
- has_many :messages
- has_many :group_uses
- has_many :users through::group_users


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique_true|
|email|string|null: false, unique_true|

### Association
- has_many :messages
- has_many :group_users
- has_many :users through::group_users
