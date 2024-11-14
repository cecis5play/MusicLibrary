# Music Library 🎧

The Music Library app is a Single Page Application (SPA) that enables users to build, browse, and manage an album catalog. 🎸🎼 This program offers a simple and effective way to work with music album data, regardless of whether you're a curator overseeing a collection or a music enthusiast looking to explore records.

💻 About the App<br/>
This app provides a streamlined platform for managing a music album catalog. It allows users to browse albums, and authenticated users can add, update, or remove album entries.<br/>
<br/>

  💡 Features <br/>
      Browse Albums: A rich catalog of music albums, with details including artist, album title, record label, and sales data. <br/>
      Manage Albums: Authenticated users can add new albums, edit existing ones, or delete albums from the catalog.<br/>
      Dynamic Catalog: Easily browse and explore the album collection.<br/>
      Create New Albums: Add fresh albums to the catalog with detailed information about the artist, album title, record label, and sales figures.<br/>
      Edit Album Details: Update the artist name, album title, label, and sales data for existing albums.<br/>
      Delete Albums: Remove albums from the library when no longer needed.<br/>
      <br/>
    
  ⚠️ Error Handling<br/>
  The app’s backend uses standard HTTP status codes to indicate the result of each request:<br/>
      🟢 200 OK: The operation was successful.<br/>
      🔴 400 Bad Request: The request is missing required or contains invalid data.<br/>
      🔴 404 Not Found: The requested album could not be found.<br/>
      🔴 500 Internal Server Error: Something went wrong on the server side.<br/>
  Each error response includes a message explaining the issue.<br/>
  🔚 Endpoints Overview<br/>
    GET /data/albums/{id}<br/>
      Purpose: Retrieve details for an album by its ID.<br/>
    Parameter:<br/>
      id (string, required): The unique ID of the album.<br/>
    Responses:<br/>
      🟢 200 OK: Successfully retrieved album details.<br/>
      🔴 404 Not Found: No album was found with the provided ID.<br/>
    POST /data/albums<br/>
      Purpose: Add a new album to the catalog.<br/>
    Request Body:<br/>
      album (object, required): Album details including:<br/>
      singer (string): The artist’s name.<br/>
      album (string): The album title.<br/>
      label (string): The record label.<br/>
      sales (string): Sales data (e.g., number of copies sold).<br/>
    Responses:<br/>
    🟢 200 OK: The album was successfully added.<br/>
    🔴 400 Bad Request: The provided data is invalid or incomplete.<br/>
    PUT /data/albums/{id}<br/>
    Purpose: <br/>
      Update an existing album's details.<br/>
    Parameters:<br/>
      id (string, required): The ID of the album to update.<br/>
    Request Body:<br/>
      album (object, required): Updated album information, including:<br/>
      singer (string): Updated artist name.<br/>
      album (string): Updated album title.<br/>
      label (string): Updated record label.<br/>
      sales (string): Updated sales information.<br/>
    Responses:<br/>
      🟢 200 OK: Successfully updated the album.<br/>
      🔴 404 Not Found: No album was found with the provided ID.<br/>
      🔴 400 Bad Request: The provided data is invalid.<br/>
    DELETE /data/albums/{id}<br/>
    Purpose: <br/>
      Remove an album from the catalog.<br/>
    Parameter:<br/>
      id (string, required): The ID of the album to delete.<br/>
    Responses:<br/>
      🟢 200 OK: The album was successfully deleted.<br/>
      🔴 404 Not Found: No album was found with the provided ID.<br/>
    🔒 Authentication<br/>
      Some actions, such as adding, updating, or deleting albums, require an authentication token. The token must be included in the request header as follows:<br/>
      <br/>

Authorization: Bearer <your_token_here><br/>
Without a valid token, these actions will be restricted.<br/>



