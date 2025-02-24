# CMS Template

## UID

Services will run with the following UIDs:

| Service  | Process | UID  |
| :------- | :------ | :--- |
| Proxy    | Master  | 101  |
|          | Workers | 101  |
| Frontend | Node    | 1000 |
| Backend  | Node    | 1000 |

## Storage

Docker volumes are used to persist data. They are created by the Docker Daemon on the host, and have root:root
ownership.

- Set APPLICATION_LOGS_PATH, application logs will be written here
- Set BACKEND_DATABASE_PATH environment variable in compose, database files will be persisted here.
- Set BACKEND_UPLOADS_PATH environment variable in compose, file uploads will be saved here.

