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
|name|string|null: false|


### Association
- has_many :users, through: :members
- has_many :members
- has_many :messages

## userテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false,add_index|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :groups, through: :members
- has_many :members
- has_many :messages

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user


This README would normally document whatever steps are necessary to get the
application up and running.