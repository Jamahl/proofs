# Home Depot Shopware POC

This project sets up a Shopware 6 instance using Dockware for a proof of concept (POC) tailored to Home Depot's branding and product structure.

## Requirements

- **Docker**: Ensure Docker is installed and running on your machine.
- **Docker Compose**: Required to manage the multi-container Docker applications.

## Setup Instructions

### 1. Start Docker Daemon

Ensure that the Docker daemon is running. You can verify this by executing:

```sh
docker ps
```

### 2. Create Docker Compose Configuration

A `docker-compose.yml` file is used to configure the Shopware instance. The configuration includes the necessary services, ports, and volumes.

### 3. Start Shopware Instance

Run the following command to start the Shopware container:

```sh
docker-compose up -d
```

This command will pull the necessary Docker images and start the Shopware service.

### 4. Verify Shopware Accessibility

Once the container is running, verify that Shopware is accessible by navigating to `http://localhost:80` in your web browser or using:

```sh
curl -I http://localhost:80
```

You should receive a `200 OK` response indicating that the server is running.

## Configuration Details

- **Ports**: The Shopware instance is accessible on port 80.
- **Volumes**: Data is persisted using Docker volumes `db_volume` and `shop_volume`.
- **Environment Variables**: XDEBUG is enabled for development purposes.

## Restarting the Shopware Instance

To restart the Shopware instance, use the following command:

```sh
docker-compose restart
```

This will restart the services defined in the `docker-compose.yml` file without rebuilding the images.

## Additional Information

- **Docker Logs**: To view the logs of the running Shopware container, use:

  ```sh
  docker logs shopware
  ```

- **Stopping the Instance**: To stop the Shopware instance, execute:

  ```sh
  docker-compose down
  ```

This will stop and remove the containers, networks, and volumes defined in the `docker-compose.yml` file.
