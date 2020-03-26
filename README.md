# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body  |text|null:fals|
|image |string|null:fals|
|user_id|integer|null:fals|
|group_id|integer|null:fals|

Association
belongs_to: group
belongs_to: user


userテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null:fals|
|email|string|null:fals, unique:true|
|password|string|null:fals, unique:true|

Association
has_many: messages
has_many: groups
has_many: groups_users


groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groups_name|integer|null:false, unique:true|

Association
has_many: messages
has_many: users
has_many: groups_users


groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false|
|groups_id|integer|null:false|

Association
belongs_to: group
belongs_to: user