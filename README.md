# 8-0-2-assignment

In this assignment, you will use Express as a Middleman for API requests.

Open your Giphy Search React assignment (`7-0-2`). It should, at minimum, be able to fetch and render the top three trending gifs.

* In the root directory, create a `server` folder and `cd` into it
  * Run `npm i express dotenv`
  * Add a `.gitignore` file with

    ```
    node_modules/
    .env
    ```

* Create a `.env` file and store your Giphy API key inside

    ```
    API_KEY="paste-api-key-here"
    ```

* Create an `index.js` file and create a simple Express server application. It should:
  * Import environment variables from `.env` using `dotenv`
  * Serve static assets from the `giphy-search/dist` folder
  * Have an `/api/gifs` endpoint that can fetch from the Giphy API using your API key
* Update the frontend React application such that it sends requests to the server using the same origin instead of directly to the Giphy API
  * Update the `vite.config.js` file to enable proxy requests.
* Add a search endpoint to your server, letting the frontend send search GET requests to the backend using query parameters.
  * When the user submits the search form with the term `"fox"`, the frontend should send a request to `/api/gifs?search=fox`.
  * When the server receives this request, it should look at the `req.query` object to find the `search` value and then make a request to the Giphy API's search endpoint.
