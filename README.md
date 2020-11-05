# furima-31149のER図

## usersテーブル

| Column    | Type    | Option      |
| --------- | ------- | ----------- |
| nick_name | string  | null: false |
| password  | string  | null: false |
| name      | string  | null: false |
| ruby      | string  | null: false |
| birthday  | integer | null: false |

## itemsテーブル

| Column          | Type       | Option                         |
| --------------- | ---------- | ------------------------------ |
| image           |            | null: false                    |
| name            | string     | null: false                    |
| items_details   | text       | null: false                    |
| category        | string     | null: false                    |
| item_status     | string     | null: false                    |
| shipping_burden | string     | null: false                    |
| source_area     | string     | null: false                    |
| days_to_ship    | integer    | null: false                    |
| price           | integer    | null: false                    |
| user            | references | null: false, foreign_key: true |

## buy_informationsテーブル

| Column          | Type       | Option                         |
| --------------- | ---------- | ------------------------------ |
| card_number     | integer    | null: false                    |
| expiration_date | string     | null: false                    |
| security        | integer    | null: false                    |
| postal_code     | integer    | null: false                    |
| prefectures     | string     | null: false                    |
| municipality    | string     | null: false                    |
| address         | string     | null: false                    |
| building_name   | string     |                                |
| phone_number    | integer    | null: false                    |
| user            | references | null: false, foreign_key: true |
| item            | references | null: false, foreign_key: true |