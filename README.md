# chat-space
 ## usersテーブル

|Column|Type|Options|
|------|----|-------|
|password|string|null: false|
|email|string|null: false|
|username|string|null: false|
### Association
- has_many :messages
- has_many :groups_users

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :groups
- belongs_to :users

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :groups
- belongs_to :users