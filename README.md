 # MoviesDatabase API Project

## API Overview
The MoviesDatabase API provides access to movie, series, and actor data. Users can retrieve information on trending titles, popular actors, and perform searches by title, genre, or release year. The API is ideal for building movie apps or dashboards.

## Version
v1.0 (confirm from documentation)

## Available Endpoints

- **GET /titles** – Retrieve a list of movies or TV titles.
- **GET /titles/search/title** – Search for titles by name.
- **GET /titles/{id}** – Get details about a specific movie/series.
- **GET /actors/{id}** – Retrieve details about a specific actor.
- **GET /genres** – Get all available genres.

## Request and Response Format

### Request
Most requests use `GET` and require headers for authentication:
```http
GET /titles
Headers:
  X-RapidAPI-Key: YOUR_API_KEY
  X-RapidAPI-Host: moviesdatabase.p.rapidapi.com


## Error Handling
When using the MoviesDatabase API, it’s important to anticipate and handle errors properly. This ensures your application can respond gracefully and provide a good user experience.

Common Error Codes and Their Meanings
Status Code  Meaning         How to Handle
400          Bad Request    Check your query parameters for missing or invalid values.
401          Unauthorized   Ensure your API key is present and correct in the request.
403          Forbidden      Your API key may not have access to this resource.
404          Not Found      The endpoint or resource (title/actor ID) may be incorrect.
429          Too Many Requests  You've hit the rate limit. Wait before sending more requests.
500+         Server Error   Issue on the server side. Consider retrying after a delay.

## Best Practices:
Use try/catch blocks when working with async requests to handle unexpected failures.

Always check the response status code before accessing the data.

Implement retry logic (especially for 429 or 5xx errors) where appropriate.

Show user-friendly error messages (e.g., "Title not found", "Please try again later").