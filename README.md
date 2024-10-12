# Medusa.JS & Next.JS Starter for Building E-commerce Websites for the West Africa Ecosystem

Welcome to the Medusa.JS & Next.JS starter template, specifically designed for building e-commerce websites tailored to the West African market!

This project offers a strong foundation for creating modern, scalable, and customizable e-commerce stores.
By combining the power of **Medusa.JS** for the backend and **Next.JS** for the frontend, you can build online stores that meet the unique needs of your customers in West Africa.

## Repository Structure

The repository is structured into two main directories:

- `store`: Contains the Medusa backend.
- `storefront`: Contains the Next.js client app (frontend).

## Getting Started

### Prerequisites

- **Node.js**: Medusa relies on a Node.js server.
- **PostgreSQL**: For the database.
- **Redis**: (Optional) For caching and performance optimization.

A `docker-compose.yml` file is provided in the `store` folder to easily set up **Postgres** and **Redis** services.

### Installation Steps

1. **Install dependencies for both the backend and frontend:**
   Navigate to the `store` and `storefront` folders and run:

   ```bash
   yarn install
   ```

2. **Set up the Medusa environment:**
   In the `store` folder, create a `.env` file by copying the contents of `.env.example`. You can keep the default values if you plan to use Docker Compose to manage the database and Redis.

   ```bash
   cp .env.example .env
   ```

3. **Start PostgreSQL and Redis services:**
   Navigate to the `store` folder and run the following command to spin up Postgres and Redis:

   ```bash
   docker-compose up -d
   ```

4. **Run Medusa migrations:**
   After setting up your services, run the database migrations to prepare your schema:

   ```bash
   yarn medusa migrations run
   ```

5. **Seed the database with default data:**
   Populate your database with sample data for testing by running:

   ```bash
   yarn seed
   ```

   You can find the data that will be added in this location `store/data/seed.json`.

6. **Start the Medusa backend:**
   Once the migrations and seed are applied, start the Medusa backend:

   ```bash
   yarn dev
   ```

7. **Start the Next.js frontend:**
   Navigate to the `storefront` folder and run:

   ```bash
   yarn dev
   ```

   The frontend will be accessible at `http://localhost:8000`, the Medusa API will be available at `http://localhost:9000` and the medusa admin at `http://localhost:7001`.

   If you used the `yarn seed` command, you can login with these credentials : 
   username : `admin@medusa-test.com`
   password: `supersecret`

   These credentials are defined in the `store/data/seed.json` file.

## Docker Configuration

If you prefer using Docker for the development environment, the provided `docker-compose.yml` simplifies the setup of PostgreSQL and Redis. You can modify the `docker-compose` file to suit your environment.

## Contributing

Feel free to contribute to this project by submitting issues or pull requests. Contributions are always welcome!
