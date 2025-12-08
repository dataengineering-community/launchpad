## Containerizing MindFuel’s Quote Delivery System
You have just completed building the backend service for MindFuel, a growing mental-wellness startup that delivers daily motivational quotes to users.

**The Python service currently:**
- Fetches quotes from ZenQuotes API
- Reads subscribers from a database
- Sends personalized motivational emails daily at 7 AM
- Logs all events for monitoring

During the initial pilot, **MindFuel** ran the service on a few different machines but managing environments manually became painful. Different machines required different Python versions, dependency conflicts occurred frequently etc.

**MindFuel** has now decided to fully containerize their system using Docker, so it can be reliably deployed anywhere.

As the engineer in charge, your job is to containerize the application and run it using production-like containers.

### Task 1: Containerize the Python Email Delivery Service
Package the Python quote-delivery service into a portable, reproducible Docker image and publish it to a container registry.

**Requirements:**

1. Write a Dockerfile that:
    - Uses a lightweight base image
    - Installs all Python dependencies
    - Sets environment variables using .env
    - Copies application code into the image
    - Uses a clear entrypoint or command to start the application

2. Build the Docker image locally.
3. Test the container by running it and verifying:
    - It fetches quotes
    - It connects to the database
    - It sends emails

4. Publish the image to Docker Hub or another registry of your choice.

5. Submit:
    - Dockerfile.
    - Image URL on registry.
    - instructions for pulling and running the image.
