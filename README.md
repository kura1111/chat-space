## usersテーブル

|Column|type|Option|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|

### Association 
- has_many :message

## groupsテーブル

|Column|type|Option|
|------|----|-------|
|name|string|null: false|
|user_id|integer|null: false, foreign_key: true|

## users_groupsテーブル

|Column|type|Option|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messageテーブル

|Column|type|Option|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false,
foreign_key: true|

### Association
- belong_to :user


