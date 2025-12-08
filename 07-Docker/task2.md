## Task 2: Multi-Container Setup With Docker Compose
Design a multi-container application that includes:
- Your Python application container
- A PostgreSQL (or MySQL) database container

**Requirements:**

1. Create a `compose.yml` file that:
    - Defines multiple services:
        - App
        - Db
    - Maps ports for external access.
    - Mounts volumes for persistence of database data.
    - Passes environment variables securely (via .env or env_file)
    - Defines service dependencies using depends_on

2. Ensure the app container:
    - Automatically connects to the database container at startup
    - Can be rebuilt with minimal friction (docker compose up --build)

3. Ensure the DB container:
    - Uses a persistent Docker volume
    - Initializes correctly

4. Verify:
    - Running docker compose up starts the entire stack
    - Your application runs without errors
    - Quotes are fetched and emails delivered successfully

**Submit:**
- Compose.yml file
- Folder structure
- Commands used
- Screenshots/logs of successful multi-service startup
