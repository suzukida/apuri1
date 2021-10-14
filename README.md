# テーブル設計

## users テーブル　（ユーザー）

| Column             | Type          | Options                        |
| ------------------ | ------------- | ------------------------------ |
| name               | string        | null: false                    |  名前
| email              | string        | unique: true  null: false      |  アドレス
| encrypted_password | string        | null: false                    |  パスワード
| last_name          | string        | null: false                    |  苗字（全角）
| last_kana          | string        | null: false                    |  フリガナ（苗字）
| first_name         | string        | null: false                    |  名前（全角）
| first_kana         | string        | null: false                    |  フリガナ（名前）
| birthday           | date          | null: false                    |  生年月日

- has_many :cats

## cats テーブル　（商品　詳細）

| Column             | Type          | Options                        |
| ------------------ | ------------- | ------------------------------ |
| cat_name           | string        | null: false                    |  商品名
| explanation        | text          | null: false                    |  商品説明
| kinds              | integer       | null: false                    |  種類
| cat_price          | integer       | null: false                    |  価格
| user               | references    | null: false, foreign_key: true |

- belongs_to :user
