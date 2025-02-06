# Costco POC with Shopware

This project sets up a proof of concept (POC) for Costco using Shopware as the e-commerce platform. The setup involves initializing a new Shopware instance, customizing it to match Costco's branding, and populating it with sample product categories and products.

## Requirements

- **Docker**: Ensure Docker is installed and running on your system.
- **Docker Compose**: Required to manage the multi-container Docker applications.

## Getting Started

### 1. Start Docker Daemon

Ensure that the Docker daemon is running. You can start it using the following command:

```sh
sudo dockerd
```

Verify Docker is running by listing containers:

```sh
docker ps
```

### 2. Create Docker Compose Configuration

A `docker-compose.yml` file is used to configure the Shopware setup. The configuration includes the Dockware image, ports, volumes, and environment variables.

### 3. Start Shopware Container

Use Docker Compose to start the Shopware container:

```sh
docker-compose up -d
```

This command will pull the necessary Docker images and start the Shopware container in detached mode.

### 4. Verify Shopware Accessibility

Once the container is running, verify that Shopware is accessible by navigating to `http://localhost:80` in your web browser. You should see the Shopware welcome page.

## Configuration Details

- **Ports**: The Shopware instance is accessible on port 80.
- **Volumes**: Two volumes are created for persistent storage: `db_volume` for MySQL data and `shop_volume` for Shopware files.
- **Environment Variables**: XDEBUG is enabled by default for development purposes.

## Restarting the Shopware Instance

To restart the Shopware instance, you can use the following command:

```sh
docker-compose restart
```

This will restart the Shopware container without needing to pull the images again.

## Additional Information

- **Base URL**: The base URL for this server is `https://b9m0igumfnnu7acuho5q.proofs.build`.
- **Docker Logs**: To view the logs of the running Shopware container, use:

```sh
docker logs shopware
```

This setup provides a clean slate for further customization and content addition to align with Costco's branding and product organization needs.
