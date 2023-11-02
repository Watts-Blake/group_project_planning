# API-Routes

This web app uses the following API routes to dynamically update the page to create a single-page-app-like feel for the user for specific features.

## FauxComments

- A logged in user may delete one of their own FauxComments, removing it from the list of visible FauxComments without causing a refresh/redirect.

### `DELETE /api/fauxComments/:id`

- Require Authentication: true
- Request

  - Method: DELETE
  - URL: /api/fauxcomments/:id
  - Body: none

- Successful Response

  - Status Code: 202
  - Body:

    ```json
    {
      "message": "comment successfully deleted",
      "id": 1,
      "statusCode": 202
    }
    ```

## FauxLikes

- A logged in user can create a Faux Tweet.

  ### `POST /api/fauxtweets`

  - Require Authentication: true

* Request

  - Method: POST
  - URL: /api/fauxtweets
  - Body:
    ```json
    {
      "userId": 1,
      "content": "example content of tweet"
    }
    ```

* Successful Response

  - Status Code: 201
  - Body:

    ```json
    {
      "id": 1,
      "content": "example content",
      "user": {
        "userId": 1,
        "username": "example",
        "profilePic": "example url for pfp"
      },
      "statusCode": 201
    }
    ```
