# README
# プロジェクト名
ProtoSpace
## ER図

### テーブル一覧

#### 1. usersテーブル
| カラム名           | 型         | 制約             | 説明              |
|-------------------|------------|------------------|------------------|
| email             | string     | not null, unique | メールアドレス    |
| encrypted_password| string     | not null         | パスワード        |
| name              | string     | not null         | ユーザー名        |
| profile           | text       | not null         | プロフィール      |
| occupation        | text       | not null         | 所属             |
| position          | text       | not null         | 役職             |

#### 2. prototypesテーブル
| カラム名    | 型         | 制約         | 説明               |
|------------|------------|--------------|-------------------|
| title      | string     | not null     | プロトタイプの名称  |
| catch_copy | text       | not null     | キャッチコピー     |
| concept    | text       | not null     | コンセプト         |
| user       | references | 外部キー      | ユーザー参照       |

#### 3. commentsテーブル
| カラム名   | 型         | 制約             | 説明             |
|-----------|------------|------------------|-----------------|
| content   | text       | not null         |                 |
| prototype | references | not null 外部キー |                 |
| user      | references | not null 外部キー |                 |

---

### テーブル間の関係
- **users** 1:N **prototypes**  
- **users** 1:N **comments**  
- **prototypes** 1:N **comments**