# README

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|content|text|------|
|user_id|integer|null: false, foreign_key: true|
|prototype_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :prototype


## imageテーブル
|Column|Type|Options|
|------|----|-------|
|prototype_id|integer|null: false, foreign_key: true|
|content|string|null:false|

### Association
- belongs_to :prototype


## prototypeテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|title|string|null: false|
|catchcopy|text|---------|
|concept|text|-----------|

### Association
- belongs_to :user
- has_many :comments
- has_many :images
- has_many :likes


## likeテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|prototype_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :prototype


##userテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true, index: true|
|email|string|null: false, unique: true, index: true|
|password|string|null: false|
|memberof|string|-----------|
|profile|text|--------------|
|works|string|--------------|

### Association
- has_many :comments
- has_many :prototypes
- has_many :likes
