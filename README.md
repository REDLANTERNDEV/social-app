# Social App

This project is a social media application similar to X and Bluesky.

## Environment Variables

Before running the application, create a `.env` file in the project root and add the following environment variables:

```env
CLERK_SECRET_KEY=your_clerk_secret_key
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
DATABASE_URL=postgres://social:mypassword@localhost:5432/socialdb?schema=public
```

Replace `your_clerk_secret_key` and `your_clerk_publishable_key` with your actual Clerk keys.

Now your project should be fully set up with Prisma.

## Setting Up the Database

Follow these steps to set up the PostgreSQL database:

1. Open your PostgreSQL client (psql).
2. Run the following commands:

```sql
CREATE USER social WITH PASSWORD 'mypassword';
CREATE DATABASE socialdb;
GRANT ALL PRIVILEGES ON DATABASE socialdb TO social;
```

3. Push your schema to the database:

```bash
npx prisma db push
```

These commands will create a new user and database, and assign all privileges to the user.

## Running the Project

1. Ensure your PostgreSQL server is running.
2. Install project dependencies:

   ```bash
   npm install
   ```

3. Start the application:

   ```bash
   npm run dev
   ```

Now your project should be up and running.
