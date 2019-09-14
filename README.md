# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

## users table
|Column|Type|Option|
|------|----|------|
|name|string|index: true, null: false, unique: true|
|mail|string|null: false|

### Association
- has_many :groups, through: members
- has_many :messages
- has_many :members

## groups table
|Column|Type|Option|
|------|----|------|
|name|string|index: true, null: false, unique: true|

### Association
- has_many :uers
- has_many :members

## members table
|Column|Type|Option|
|------|----|------|
|user_name|string|index: true, null: false, unique: true|
|group_name|string|index: true, null: false, unique: true|

### Association
- belongs_to :users
- belongs_to :groups

## messages table
|Column|Type|Option|
|------|----|------|
|text|text|ndex: true, null: false|
|image|string|index: true|

### Association
- belongs_to :users

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
