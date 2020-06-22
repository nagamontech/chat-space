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
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

#### Association
- has_many: groups, through: groups_users
has_many: posts, through: users_posts

### postsテーブル

|Column|Type|Options|
|------|----|-------|
|message|text|null: false|
|image|text|null: false|


#### Association
- belongs_to :group
has_many: users, through: users_posts


### users_postsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|foreign_key: true|
|post_id|integer|foreign_key: true|

#### Association
- belongs_to :user
- belongs_to :post

### groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

#### Association
- has_many: users, through: groups_users

### groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|foreign_key: true|
|user_id|integer|foreign_key: true|

#### Association
- belongs_to :group
- belongs_to :user
