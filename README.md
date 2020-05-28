## usersテーブル

|Column|type|Option|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|

### Association 
- has_many :messages
- has_many :users_groups
- has_many :groups through: : users_groups

## groupsテーブル

|Column|type|Option|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :users_groups
- has_many :users through: : users_groups

## users_groupsテーブル

|Column|type|Option|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messageテーブル

|Column|type|Option|
|------|----|-------|
|body|text|
|image|string|
|group|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|

### Association
- belong_to :group
- belong_to :user


