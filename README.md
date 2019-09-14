# README

## users
|Column|Type|Option|
|------|----|------|
|name|string|index: true, null: false, unique: true|
|mail|string|null: false|

### Association
- has_many :groups, through: members
- has_many :messages
- has_many :members

## groups
|Column|Type|Option|
|------|----|------|
|name|string|null: false|

### Association
- has_many :users, through: members
- has_many :members
- has_many :messages

## members
|Column|Type|Option|
|------|----|------|
|user_id|references|foreign_key: true, null: false|
|group_id|references|foreign_key: true, null: false|

### Association
- belongs_to :user
- belongs_to :group

## messages
|Column|Type|Option|
|------|----|------|
|text|text|index: true, null: false|
|image|string||
|user_id|references|foreign_key: true, null: false|
|group_id|references|foreign_key: true, null: false|

### Association
- belongs_to :user
- belongs_to :group