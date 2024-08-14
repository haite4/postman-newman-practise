# Postman + newman + github actions 

## Introduction
This project focuses on testing a local server API using Postman and Newman. It is integrated with GitHub Actions to automate the execution of API tests, and the test results are published to GitHub Pages.

## Steps to Install
1. Install Nodejs:

    [Nodejs](https://nodejs.org/en/download/package-manager)

2. Clone the repository:
    ```sh
    git clone https://github.com/haite4/postman-newman-task
    ```
3. Navigate to the project directory:
    ```sh 
    cd postman-newman-task
    ```

4. Install dependencies:
    ```sh
    npm install 
    ``` 

## Steps to Launch

1. **Run the local server**:
    ```sh
    npm run tern-on-api
    ```
   
   
## Overview of API Endpoints

This section provides an overview of the available API endpoints for interacting with the local server. The server supports routes for managing `products`, `orders`, and `users`. The table below details the operations for the `products` resource, which are similarly available for `orders` and `users`.

| VERB     |Route          | Input      | Output             |
|----------|---------------|------------|--------------------|
| GET      | /products     | *None*     | **Array**          |
| GET      | /products/:id |  **e.g 3** | **Object**         |
| POST     | /products     | **object** | **Created object** |
| PUT      | /products     | **object** | **Updated object** |
| DELETE   | /products/:id | **e.g 3**  | **Deleted object** |

## Testing with Postman

1. **Open Postman**: Launch the Postman application on your computer.

2. **Import Collection**: Import the `store.collection.json` file into Postman. This file contains the API requests and tests.

3. **Run Tests**:
   - **Single Test**: To run a specific test, select the request from the collection and click "Send" to execute it.
   - **All Tests**: 
     - Right-click on the collection name in the sidebar.
     - Select "Run Collection" from the context menu.
     - The Collection Runner will open. In the Runner, click the "Run <collection name>" button to start executing all tests. 

## Running Tests Locally with Newman

Newman is a command-line utility that enables you to run Postman collections directly from your terminal. Follow these steps to execute your tests locally and view the results:

1. **Install Newman**:
   - To add Newman as a local development tool, run the following command:
     ```sh
     npm install newman --save-dev
     ```

2. **Execute the Tests and Create a Report**:
   - Run your Postman collection and generate a test report by executing:
     ```sh
     npm run test:api
     ```

3. **View the Report**:
   - **For macOS Users**: Open the report file in your default web browser by using:
     ```sh
     open  testResults/index.html
     ```
   - **For Windows Users**: Launch the report file in your default web browser with:
     ```sh
     start testResults/index.html
     ```

    - **For Linux Users**: Open the report file in your default web browser with:
     ```sh
        xdg-open testResults/index.html
     ```


## GitHub Actions Integration

We have set up a GitHub Actions workflow to automatically run the `petstore.collection.json` Postman collection. The workflow executes the API tests and publishes the results to GitHub Pages. You can review the test results at the following link:

[View Test Results](https://haite4.github.io/postman-newman-task/)

### Summary
- **GitHub Actions Workflow**: The workflow is configured to run the Postman collection and generate test reports.
- **Result Publication**: Test results are automatically published to GitHub Pages, providing a convenient way to access and review the results online.