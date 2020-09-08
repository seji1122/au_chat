
# users テーブル
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |
| living_country | string | null: false |
# Association
has_many :room_users
has_many :rooms, through: room_users
has_many :messages

# rooms テーブル
| name   | string | null: false |
# Association
has_many :room_users
has_many :users, through: room_users
has_many :messages

# room_users テーブル
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |
# Association
belongs_to :room
belongs_to :user

# messages テーブル
| content | string     |                                |
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true |
# Association
belongs_to :room
belongs_to :user