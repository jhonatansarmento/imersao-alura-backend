# Imersão Alura Backend

## Description
Imersão Alura Backend is a backend application built with Node.js and Express, designed to handle blog post management, including creating, updating, and listing posts. The application also supports image uploads and utilizes MongoDB for data storage.

## Features and Functionality
- **Post Management**: Create, update, and retrieve posts.
- **Image Uploads**: Upload images associated with posts.
- **MongoDB Integration**: Stores posts in a MongoDB database.
- **Generative AI Description**: Generates image descriptions using Google's Gemini AI.

## Technology Stack
- **Node.js**: JavaScript runtime for building the server.
- **Express**: Web framework for Node.js.
- **MongoDB**: NoSQL database for data storage.
- **Multer**: Middleware for handling file uploads.
- **CORS**: Middleware to enable Cross-Origin Resource Sharing.
- **dotenv**: Module to load environment variables.
- **Google Generative AI**: API for generating image descriptions.

## Prerequisites
- Node.js (version 14 or later)
- MongoDB Atlas account (for cloud database)
- Environment variables for database connection and Gemini API key

## Installation Instructions
1. **Clone the repository**:
   ```bash
   git clone https://github.com/jhonatansarmento/imersao-alura-backend.git
   cd imersao-alura-backend
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Set up environment variables**:
   Create a `.env` file in the root directory and add the following:
   ```plaintext
   STRING_CONNECTION=your_mongodb_connection_string
   GEMINI_API_KEY=your_gemini_api_key
   ```

4. **Create the uploads directory** (if not already present):
   ```bash
   mkdir uploads
   ```

## Usage Guide
1. **Start the server**:
   ```bash
   node server.js
   ```
   The server will start on port `3000` and will log "Servidor escutando..." in the console.

2. **API Endpoints**:
   - **List Posts**: 
     - **GET** `/posts` - Retrieves all posts.
   - **Create Post**: 
     - **POST** `/posts` - Creates a new post. Send a JSON body.
   - **Upload Image**: 
     - **POST** `/upload` - Uploads an image. Use `multipart/form-data` with the key as "imagem".
   - **Update Post**: 
     - **PUT** `/upload/:id` - Updates an existing post by ID. Send a JSON body.

## API Documentation
- **List all posts**
  - **URL**: `/posts`
  - **Method**: `GET`
  - **Response**: JSON array of post objects.

- **Create a new post**
  - **URL**: `/posts`
  - **Method**: `POST`
  - **Body** (JSON):
    ```json
    {
      "descricao": "Your post description",
      "imgUrl": "optional_image_url",
      "alt": "optional_alt_text"
    }
    ```
  - **Response**: JSON object of the created post.

- **Upload an image**
  - **URL**: `/upload`
  - **Method**: `POST`
  - **Form Data**: 
    - Key: `imagem`, Value: [file]
  - **Response**: JSON object of the created post.

- **Update a post**
  - **URL**: `/upload/:id`
  - **Method**: `PUT`
  - **Body** (JSON):
    ```json
    {
      "alt": "new_alt_text"
    }
    ```
  - **Response**: JSON object of the updated post.

## Contributing Guidelines
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/YourFeature
   ```
3. Make your changes and commit them:
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to the branch:
   ```bash
   git push origin feature/YourFeature
   ```
5. Create a pull request.

## License Information
No license has been specified for this project. Please check the repository for any updates regarding licensing.

## Contact/Support Information
For support, please open an issue in the GitHub repository or contact the repository owner via GitHub.
