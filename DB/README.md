## DBの設計  
### User
- id: int、bigIncrement、primary key
- name: string、unique(認証に使う)
- point: int __(追加機能)

### Emotion
- id: int、bigIncrement、primary key
- emotion: int(frontendで番号に対応した数字を)
- point: int __(追加機能)

### Comment
- id: int、bigIncrement、primary key
- user_id: foreign key
- emotion_id: foreign key
- prefecture: string
- latitude: double(緯度)
- longtitude: double(経度)
- comment: text
- dateTime: dateTime

### Response
- id: int、bigIncrement、primary key
- user_id: foreign key
- comment_id: foreign key
- comment: text
- dateTime: dateTime

### 関係性
- User Comment: 一対多
- User Response: 一対多
- Comment Response: 一対多
- Comment Emotion: 一対一