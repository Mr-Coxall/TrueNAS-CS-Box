# Gitea

## Setup Instructions

- select "Datasets", "Add Dataset", "Name" -> "gitea"
- goto "System, "Shell"
  - goto "/mnt/storage" and take ownership of directory as "truenas_admin"
    - sudo chown -R 950:950 /mnt/storage/gitea
    - go into ./gitea directory
- use the provided `docker-compose.yml` file to run Gitea with PostgreSQL
  - sudo nano docker-compose.yml
- DO NOT try to setup email, since you need 2FA on Gmail to use it
- the app.ini file for Gitea will be in directory something like:
  - /data/compose/3/gitea/gitea/conf
  ```bash
  [repository]
  ROOT = /data/git/repositories
  DEFAULT_PRIVATE = true
  FORCE_PRIVATE = true
  DISABLE_PUBLIC_REPO = true

  [oauth2]
  ENABLED = true
  ```

![alt Gitea admin login](./gitea_loggins.png)

