# 音乐管理系统后端 ER 图
```mermaid
erDiagram
    music_info {
        int id PK
        varchar(100) title
        varchar(100) ​​track_number​​
        int album_id FK
        varchar(100) raw_file_path
        int quality
    }
    artist {
        int id PK
        varchar(100) name
    }
    music_info_artist {
        int music_info_id PK, FK
        int artist_id PK, FK
    }
    album {
        int id PK
        varchar(100) name
    }
    user {
        int id PK
        varchar(50) name
    }
    song_list {
        int id PK
        int user_id FK
    }
    music_info_song_list {
        int song_list_id PK, FK
        int music_info_id PK, FK
    }

    artist ||--o{ music_info_artist : artist_id
    music_info ||--o{ music_info_artist : music_info_id
    album ||--o{ music_info : album_id
    music_info ||--o{ music_info_song_list : music_info_id
    song_list ||--o{ music_info_song_list : song_list_id
    user ||--o{ song_list : user_id
```