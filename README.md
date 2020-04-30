# README
<!-- messagesテーブル
・文字
・画像
・投稿者名
・グループ名 -->
## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association

- belongs_to :group
- belongs_to :user

<!-- userテーブル
・名前
・登録アドレス -->
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, add_index: true|
|email|string|null: false, unique: true|
|password|string|null: false|
|password confirmation|string|null: false|

### Association

- has_many :group_users
- has_many :groups, thruogh: groups_users
- has_many :messages

<!-- groupsテーブル
・グループ名 -->
## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true

### Association

- has_many :group_users
- has_many :users, through: groups_users
- has_many :messages

<!-- groups_usersテーブル（中間テーブル）
・ユーザーID
・グループID -->
## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association

- belongs_to :group
- belongs_to :user




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
