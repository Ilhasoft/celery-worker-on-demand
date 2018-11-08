# Test with Docker containers

Up Celery worker in Docker container on demand.

**Description:**

In this test there is a Celery application with two tasks, add and diff, each running in a dedicated queue.

## Required Tools

- Docker
- Docker Compose

## Run Test

### Step 1

Build Docker image `docker-test-app:latest` running follow command:

```bash
docker-compose build
```

### Step 2

Start agent service:

```bash
docker-compose up agent
```

### Step 3

Run a task:

```bash
# task add
docker-compose run docker-test-app test.run_task_add

# task diff
docker-compose run docker-test-app test.run_task_diff
```