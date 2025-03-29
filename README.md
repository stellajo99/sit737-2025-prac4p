# Calculator Microservice (with Logging)

## Overview
This is a simple calculator microservice built using Node.js and Express.  
It supports basic arithmetic operations including addition, subtraction, multiplication, and division via HTTP GET requests.  
The application also includes request and error logging using the Winston logging library.

## Installation

1. Clone the repository or copy the project files to your local machine.
2. Navigate to the project directory and install dependencies:
   ```sh
   npm install express winston
   ```
3. Create a directory for logs:
   ```sh
   mkdir logs
   ```
4. Start the server with:
   ```sh
   node calculator-microservice.js
   ```

## API Endpoints

### 1. Addition
- **Endpoint:** `/add`
- **Method:** `GET`
- **Query Parameters:**
  - `num1` (number) - First number
  - `num2` (number) - Second number
- **Example Request:**
  ```sh
  http://localhost:3000/add?num1=5&num2=3
  ```
- **Example Response:**
  ```json
  {
    "result": 8
  }
  ```

### 2. Subtraction
- **Endpoint:** `/subtract`
- **Method:** `GET`
- **Query Parameters:**
  - `num1` (number) - First number
  - `num2` (number) - Second number
- **Example Request:**
  ```sh
  http://localhost:3000/subtract?num1=10&num2=4
  ```
- **Example Response:**
  ```json
  {
    "result": 6
  }
  ```

### 3. Multiplication
- **Endpoint:** `/multiply`
- **Method:** `GET`
- **Query Parameters:**
  - `num1` (number) - First number
  - `num2` (number) - Second number
- **Example Request:**
  ```sh
  http://localhost:3000/multiply?num1=6&num2=7
  ```
- **Example Response:**
  ```json
  {
    "result": 42
  }
  ```

### 4. Division
- **Endpoint:** `/divide`
- **Method:** `GET`
- **Query Parameters:**
  - `num1` (number) - Numerator
  - `num2` (number) - Denominator (must not be 0)
- **Example Request:**
  ```sh
  http://localhost:3000/divide?num1=20&num2=4
  ```
- **Example Response:**
  ```json
  {
    "result": 5
  }
  ```

## Error Handling
The API returns a `400` status code with a descriptive error message if:
- `num1` or `num2` is missing or empty
- A non-numeric value is provided
- Division by zero is attempted

## Logging
- Logging is implemented using the `winston` library.
- Logs are output to both the console and files under the `logs/` directory:
  - `logs/combined.log` — All logs
  - `logs/error.log` — Error messages only
- Each request logs the operation type and input values.

To monitor logs in real-time:
```sh
tail -f logs/combined.log
```

## Running the Server
- The application runs on **port 3000** by default.
- You can access it at: `http://localhost:3000`
