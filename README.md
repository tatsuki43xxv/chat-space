# README

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, add_index|
|menbers_id|integer|null: false, foreign_key: true|


### Association
-has_many :groups
-has_many :messages

## userテーブル

|Column|Type|Options|
|------|----|-------|
|user_name|string|null: false,add_index|
|email|string|null: false|
|password|string|null: false|
|menbers_id|integer|null: false, foreign_key: true|


### Association
-has_many :groups
-has_many :messages

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false,add_index|
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user


This README would normally document whatever steps are necessary to get the
application up and running.