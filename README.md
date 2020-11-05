# furima-31149のER図

## usersテーブル

| Column             | Type     | Option      |
| ------------------ | -------- | ----------- |
| nick_name          | string   | null: false |
| encrypted_password | string   | null: false |
| first_name         | string   | null: false |
| family_name        | string   | null: false |
| first_name_kana    | string   | null: false |
| family_name_kana   | string   | null: false |
| birthday           | datetime | null: false |
has_many :item
has_many :buy_information

### Association

## itemsテーブル

| Column          | Type       | Option                         |
| --------------- | ---------- | ------------------------------ |
| name            | string     | null: false                    |
| items_details   | text       | null: false                    |
| category        | integer    | null: false                    |
| item_status     | integer    | null: false                    |
| shipping_burden | integer    | null: false                    |
| source_area     | integer    | null: false                    |
| days_to_ship    | integer    | null: false                    |
| price           | integer    | null: false                    |
| user            | references | null: false, foreign_key: true |

### Association
belongs_to :user
has_one :buy_information

## buy_informationsテーブル

| Column          | Type       | Option                         |
| --------------- | ---------- | ------------------------------ |
| expiration_date | string     | null: false                    |
| security        | integer    | null: false                    |
| postal_code     | string     | null: false                    |
| prefectures     | integer    | null: false                    |
| municipality    | string     | null: false                    |
| address         | string     | null: false                    |
| building_name   | string     |                                |
| phone_number    | string     | null: false                    |
| user            | references | null: false, foreign_key: true |
| item            | references | null: false, foreign_key: true |

### Association
belongs_to :user
belongs_to :item