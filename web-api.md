# web-api
所有的 web-api 返回 json ，所有的 web-api POST 的 body 是 json 。

## misc
### 检查服务器连通性
GET /api/misc/ping

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |

## user-services
### 列出所有歌曲的信息
GET /api/user-services-services/music/list

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| Authorization | header | string | 是 | Bearer |
| keywords | query | string | 否 | 搜索的关键词 |
| page | query | int | 否 | 页码 |
| per_page | query | int | 否 | 每页数量 |
| scope | query | int | 否 | 查询范围， Flag 枚举，范围：标题，专辑，艺术家 |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |
| data | object | 是 |  |
| data > music_info | object[] | 是 | 歌曲消息列表 |
| music_info > id | int | 是 | id |
| music_info > title | string | 是 | 标题 |
| music_info > album | string | 是 | 专辑名称 |
| music_info > artist | string | 是 | 艺术家 |
| music_info > track_number​​ | int | 是 | 歌曲在专辑中的序号 |

### 列出特定歌曲的信息
GET /api/user-services/music/get

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| Authorization | header | string | 是 | Bearer |
| id | query | int | 是 | id |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |
| data | object | 是 |  |
| data > id | int | 是 | id |
| data > title | string | 是 | 标题 |
| data > album | string | 是 | 专辑名称 |
| data > artist | string | 是 | 艺术家 |
| data > track_number​​ | int | 是 | 歌曲在专辑中的序号 |

### 列出所有艺术家的信息
GET /api/user-services/artist/list

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| Authorization | header | string | 是 | Bearer |
| keywords | query | string | 否 | 搜索的关键词 |
| page | query | int | 否 | 页码 |
| per_page | query | int | 否 | 每页数量 |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |
| data | object | 是 |  |
| data > artists | object[] | 是 | 艺术家列表 |
| artists > id | int | 是 | id |
| artists > name | string | 是 | 姓名 |

### 列出特定艺术家的信息及其作品
GET /api/user-services/artist/get

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| Authorization | header | string | 是 | Bearer |
| id | query | int | 是 | id |
| page | query | int | 否 | 页码 |
| per_page | query | int | 否 | 每页数量 |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |
| data | object | 是 |  |
| data > artist | object | 是 | 艺术家 |
| artist > id | int | 是 | id |
| artist > name | string | 是 | 姓名 |
| data > music_info | object[] | 是 | 歌曲消息列表 |
| music_info > id | int | 是 | id |
| music_info > title | string | 是 | 标题 |
| music_info > album | string | 是 | 专辑名称 |
| music_info > artist | string | 是 | 艺术家 |
| music_info > track_number​​ | int | 是 | 歌曲在专辑中的序号 |

### 列出所有专辑的信息
GET /api/user-services/album/list

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| Authorization | header | string | 是 | Bearer |
| keywords | query | string | 否 | 搜索的关键词 |
| page | query | int | 否 | 页码 |
| per_page | query | int | 否 | 每页数量 |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |
| data | object | 是 |  |
| data > albums | object[] | 是 | 专辑列表 |
| albums > id | int | 是 | id |
| albums > name | string | 是 | 专辑名称 |

### 列出特定专辑的信息及其歌曲信息
GET /api/user-services/album/get

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| Authorization | header | string | 是 | Bearer |
| id | query | int | 是 | id |
| page | query | int | 否 | 页码 |
| per_page | query | int | 否 | 每页数量 |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |
| data | object | 是 |  |
| data > album | object | 是 | 专辑 |
| album > id | int | 是 | id |
| album > name | string | 是 | 专辑名称 |
| data > music_info | object[] | 是 | 歌曲消息列表 |
| music_info > id | int | 是 | id |
| music_info > title | string | 是 | 标题 |
| music_info > album | string | 是 | 专辑名称 |
| music_info > artist | string | 是 | 艺术家 |
| music_info > track_number​​ | int | 是 | 歌曲在专辑中的序号 |

## raw
### 获取指定音乐的文件流
GET /api/raw/

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| Authorization | header | string | 是 | Bearer |
| id | query | int | 是 | id |

#### 返回数据结构
二进制文件流。

## auth
### 注册
POST /api/auth/register

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| username | body | string | 是 |  |
| password | body | string | 是 |  |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |

### 登录
POST /api/auth/login

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| username | body | string | 是 |  |
| password | body | string | 是 |  |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |
| token | string | 是 | JWT |

### 登出
POST /api/auth/logout

#### 请求参数
| 名称 | 位置 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: | :--: |
| Authorization | header | string | 是 | Bearer |

#### 返回数据结构
| 名称 | 类型 | 必选 | 说明 |
| :--: | :--: | :--: | :--: |
| code | int | 是 | 状态码 |
| message | string | 是 | 消息 |

## admin
### 列出所有用户
