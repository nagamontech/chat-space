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
### usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|email|string|null: false, foreign_key: true|
|password|string|null: false|
|group_id|integer|

#### Association
- has_many: groups, through: groups_users
- has_many: posts

### postsテーブル

|Column|Type|Options|
|------|----|-------|
|message|text|null: false|
|user_id|integer|

#### Association
- belongs_to :groups
- belongs_to :users

### groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|email|string|null: false, foreign_key: true|
|password|string|null: false|
|user_id|integer|

#### Association
- has_many: users, through: groups_users

### groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|
|user_id|integer|

#### Association
- belongs_to :groups
- belongs_to :users
