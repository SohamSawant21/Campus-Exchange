# Database Design
### Entities
#####  Users

| Field         | Type    |
| ------------- | ------- |
| id            | bigint  |
| name          | varchar |
| email         | varchar |
| password      | varchar |
| profile_image | varchar |

***

##### Categories
| Field | Type |
| ----- | ----- |
| id    | int |
| name  | varchar |

Examples:

- Books
- Electronics
- Lab Equipment
- Components

***
##### Listings
| Field       |
| ----------- |
| id          |
| user_id     |
| category_id |
| title       |
| description |
| price       |
| image       |
| status      |
***
##### Messages
| Field       |
| ----------- |
| id          |
| sender_id   |
| receiver_id |
| listing_id  |
| message     |
***
##### Reports
| Field      |
| ---------- |
| id         |
| user_id    |
| listing_id |
| reason     |

***
### Database Relationships

> 
> User
>  ├── hasMany Listings
>  ├── hasMany Messages
>  └── hasMany Reports
> 
> Category
>  └── hasMany Listings
> 
> Listing
>  ├── belongsTo User
>  ├── belongsTo Category
>  └── hasMany Messages
