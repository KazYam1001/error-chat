# README

## usersテーブル
|Column  |Type        |Options|
|------  |----        |-------|
|name    |varchar(15) |null: false, unique: true, index: true|
|email   |varchar(255)|null: false, unique: true             |
|password|varchar(255)|null: false, unique: true             |

### Association
- has_many :members
- has_many :messages

## membersテーブル
|Column  |Type   |Options|
|------  |----   |-------|
|user_id |integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル
|Column  |Type        |Options|
|------  |----        |-------|
|name    |varchar(255)|null: false|

### Association
- has_many :members
- has_many :messages

## messagesテーブル
|Column  |Type        |Options|
|------  |----        |-------|
|body    |text        |null: false                                |
|image   |varchar(255)|                                           |
|user_id |int         |null: false, foreign_key: true             |
|group_id|int         |null: false, foreign_key: true, index: true|

### Association
- belongs_to :user
- belongs_to :group
