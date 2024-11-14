# Music Library 🎧

The Music Library app is a Single Page Application (SPA) that enables users to build, browse, and manage an album catalog. 🎸🎼 This program offers a simple and effective way to work with music album data, regardless of whether you're a curator overseeing a collection or a music enthusiast looking to explore records.

💻 About the App
This app provides a streamlined platform for managing a music album catalog. It allows users to browse albums, and authenticated users can add, update, or remove album entries.

&emsp;  💡 Features <br/>
&emsp;        Browse Albums: A rich catalog of music albums, with details including artist, album title, record label, and sales data. <br/>
&emsp;&emsp;    Manage Albums: Authenticated users can add new albums, edit existing ones, or delete albums from the catalog.
&emsp;&emsp;    Dynamic Catalog: Easily browse and explore the album collection.
&emsp;&emsp;    Create New Albums: Add fresh albums to the catalog with detailed information about the artist, album title, record label, and sales figures.
&emsp;&emsp;    Edit Album Details: Update the artist name, album title, label, and sales data for existing albums.
&emsp;&emsp;    Delete Albums: Remove albums from the library when no longer needed.
    
  ⚠️ Error Handling
  The app’s backend uses standard HTTP status codes to indicate the result of each request:
      🟢 200 OK: The operation was successful.
      🔴 400 Bad Request: The request is missing required or contains invalid data.
      🔴 404 Not Found: The requested album could not be found.
      🔴 500 Internal Server Error: Something went wrong on the server side.
  Each error response includes a message explaining the issue.
  🔚 Endpoints Overview
    GET /data/albums/{id}
      Purpose: Retrieve details for an album by its ID.
    Parameter:
      id (string, required): The unique ID of the album.
    Responses:
      🟢 200 OK: Successfully retrieved album details.
      🔴 404 Not Found: No album was found with the provided ID.
    POST /data/albums
      Purpose: Add a new album to the catalog.
    Request Body:
      album (object, required): Album details including:
      singer (string): The artist’s name.
      album (string): The album title.
      label (string): The record label.
      sales (string): Sales data (e.g., number of copies sold).
    Responses:
    🟢 200 OK: The album was successfully added.
    🔴 400 Bad Request: The provided data is invalid or incomplete.
    PUT /data/albums/{id}
    Purpose: 
      Update an existing album's details.
    Parameters:
      id (string, required): The ID of the album to update.
    Request Body:
      album (object, required): Updated album information, including:
      singer (string): Updated artist name.
      album (string): Updated album title.
      label (string): Updated record label.
      sales (string): Updated sales information.
    Responses:
      🟢 200 OK: Successfully updated the album.
      🔴 404 Not Found: No album was found with the provided ID.
      🔴 400 Bad Request: The provided data is invalid.
    DELETE /data/albums/{id}
    Purpose: 
      Remove an album from the catalog.
    Parameter:
      id (string, required): The ID of the album to delete.
    Responses:
      🟢 200 OK: The album was successfully deleted.
      🔴 404 Not Found: No album was found with the provided ID.
    🔒 Authentication
      Some actions, such as adding, updating, or deleting albums, require an authentication token. The token must be included in the request header as follows:

Authorization: Bearer <your_token_here>
Without a valid token, these actions will be restricted.



