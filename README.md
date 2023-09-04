                                    Project Explanation

This document provides an overview of the code in the `views.py` file of our Django project. The code in this file is responsible for handling various API endpoints related to user registration, login, product management, and pagination.

 User Registration register

 Endpoint: register

- This view allows new users to register by providing their first name, last name, username, and password.
- The provided information is validated, and a new user is created using Djangos built-in `User` model.
- Successful registration results in a JSON response with a success message.

 User Login user_login

 Endpoint: login

- Users can log in by providing their username and password.
- The provided credentials are authenticated using Django's authenticate method.
- If authentication is successful, the user is logged in, and a success message is returned in the response.
- In case of failed authentication, an error message is returned with a status code.

 CSV File Upload upload_product_csv

 Endpoint: upload_product_csv

- Admin users can upload CSV files containing product data.
- The uploaded CSV file is processed using the `pandas` library to read and handle the data.
- The code expects the CSV file to be submitted as a part of the POST request.
- If the user is not an admin or if no CSV file is provided, appropriate error messages are returned.
- Successful processing of the CSV file results in a success message.

 Product Review Submission add_product_review

 Endpoint: add_product_review

- Users can submit product reviews along with ratings.
- The review data, including the product ID, review text, and rating, is expected in a POST request.
- The code handles validation, associates the review with the relevant product and user, and returns a success message upon successful submission.

 Product Pagination and Sorting paginate_products

 Endpoint: paginate_products

- This view provides product pagination and sorting based on reviews.
- Users can specify the page number and sorting criteria (default is by rating) in the GET request parameters.
- The code fetches products from the database, applies to sort, and paginates the results using Djangos `Paginator`.
- The paginated products are serialized and returned in a JSON response, along with information about the total number of pages and the current page number.

This document serves as a high-level explanation of the functionality implemented in the `views.py` file. It is essential to refer to this documentation when working with the API endpoints provided by this Django project.

Endpoints
1. User Registration
URL: /api/register/
Method: POST
Parameters: First name, last name, username, password
Description: Allows new users to register by providing their information.
2. User Login
URL: /api/login/
Method: POST
Parameters: Username, password
Description: Allows users to log in.
3. Upload CSV of Products
URL: /api/upload_product_csv/
Method: POST
Parameters: CSV file containing product data
Description: Allows admin users to upload product data from a CSV file.
4. Add Product Review
URL: /api/add_product_review/
Method: POST
Parameters: Product ID, review text, rating
Description: Allows users to add reviews and ratings for products.
5. Paginate and Sort Products
URL: /api/paginate_products/
Method: GET
Parameters: Page number, sorting criteria
Description: Retrieves and paginates product data, with optional sorting based on reviews.
Built With
Django - The web framework used
Pandas - Used for CSV file processing
Authors
Your Name - https://github.com/DINESHPANDIAN-J
