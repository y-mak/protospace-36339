#テーブル設計

## users テーブル

|Column         |Type   |Options    |
|---------------|-------|-----------|
|email          |string |null:false |
|password       |string |null:false |
|name           |string |null:false |
|profile        |text   |null:false |
|occupation     |txet   |null:false |
|position       |text   |null:false |

### Association
- has_many :prototypes
- has_many :comments

## comments テーブル

|Column         |Type       |Options                      |
|---------------|-----------|-----------------------------|
|text           |text       |null:false                   |
|user           |references |null:false,foreign_key:true  |
|prototype      |references |null:false,foreign_key:true  |

### Association
- belongs_to :user
- belongs_to :prototype

## prototypes テーブル

|Column         |Type       |Options                      |
|---------------|-----------|-----------------------------|
|title          |text       |null:false                   |
|catch_copy     |text       |null:false                   |
|concept        |text       |null:false                   |
|user           |references |null:false,foreign_key:true  |

### Association
- belongs_to :user
- has_many :comments