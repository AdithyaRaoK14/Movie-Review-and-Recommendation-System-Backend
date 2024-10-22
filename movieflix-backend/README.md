# MovieFlix API

This API provides endpoints to manage movie ratings, comments, and watchlists. It allows users to rate movies, leave comments, and add movies to their watchlists.
![image](https://github.com/zorgonide/movieflix-node/assets/48021258/a0103202-31b7-4511-88c2-fa33e3a9d85a)

### [Postman Documentation](https://documenter.getpostman.com/view/11815460/2s93zH2K7A)

## Installation

1. Clone the repository: `git clone <repository_url>`
2. Install dependencies: `npm install`

## Prerequisites

- Node.js
- PostgreSQL or any other supported database (configured in the Prisma schema).
- There should be a `.env` file in the project root folder, with `DATABASE_URL` and `JWT_SECRET` defined. I used [render](https://render.com/) to set up a free PostgreSQL db.

## Configuration

1. Update the `.env` file with your database connection details and other environment variables.
2.  ```
     DATABASE_URL="postgres://xxxxxxxxx"  
     JWT_SECRET = "2RXuR@xxxxxxxx"
    ```

## Database Setup

1. Run database migrations: `npx prisma migrate dev`

## Usage

Start the server: `npm run dev`

The server will be running on `http://localhost:3000`.

## Endpoints

### User

- `POST /signin`: Sign in to the application.
- `POST /user`: Create a new user.
- `PUT /user`: Update user information.
- `GET /user`: Get user details.

### Movie

- `POST /movie/:id`: Add a new movie.
- `GET /movie/:id`: Get movie details.

### Comment

- `GET /comment/:movieId`: Get comments for a movie.
- `POST /comment`: Create a new comment.
- `PUT /comment/:movieId`: Update a comment.
- `DELETE /comment/:id`: Delete a comment.

### Rating

- `GET /rating/:movieId`: Get ratings for a movie (Returns the average rating for a movie across all users).
- `PUT /rating`: Update a rating.
- `POST /rating/:movieId`: Create a new rating (Modifies an existing rating if the user resubmits the rating).

### Watchlist

- `GET /watchlist`: Get the user's watchlist.
- `DELETE /watchlist/:movieId`: Remove a movie from the watchlist.
- `POST /watchlist/:movieId`: Add a movie to the watchlist.

## Error Handling

If any error occurs during the API request handling, a 500 status code will be returned along with an error message in the response body.

## Contributing

Contributions are welcome! If you find any issues or want to enhance the API, feel free to open a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- [Prisma](https://www.prisma.io/): Used as the database ORM.
- [Express](https://expressjs.com/): Used as the web framework.
- [bcrypt](https://www.npmjs.com/package/bcrypt): Used for password hashing.
- [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken): Used for authentication and authorization.
- [dotenv](https://www.npmjs.com/package/dotenv): Used for environment variable management.

Feel free to modify the readme file to suit your specific requirements and add any additional information or instructions that might be relevant to your project.
