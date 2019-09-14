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
|name|string|index: true, null: false, unique: true|

### Association
- has_many :users, through: members
- has_many :members

## members
|Column|Type|Option|
|------|----|------|
|user_id|string|index: true, null: false, unique: true|
|group_id|string|index: true, null: false, unique: true|

### Association
- belongs_to :user
- belongs_to :group

## messages
|Column|Type|Option|
|------|----|------|
|text|text|index: true, null: false|
|image|string|index: true|
|user_id|string|index: true, null: false, unique: true|
|group_id|string|index: true, null: false, unique: true|

### Association
- belongs_to :user
- belongs_to :group