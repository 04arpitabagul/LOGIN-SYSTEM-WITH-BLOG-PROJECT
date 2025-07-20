<a href="https://drive.google.com/file/d/1YgiiFkU2zuxONP0a4yHMF4pDB3H9AzXh/view?usp=sharing">OUTPUT VISUALS</a>

# LOGIN SYSTEM WITH BLOG PROJECT

### **Objective**

Develop a full-stack web application titled **"Blog Management System"** using **React.js** for the frontend and **Node.js, Express, and MongoDB** for the backend. The application should support **CRUD operations** on blog posts with **authentication and role-based access** for **admin** and **user** roles. Key features include **JWT-based authentication**, **bcrypt for password encryption**, and **cookie-based session management**.

### **Requirements**

1. **Frontend (React.js)**:
    - **User Interface**:
        - **Sign Up & Login**: Pages for user registration and login, storing JWT tokens in cookies for authentication.
        - **User Roles**:
            - **Admin**: Can create, update, delete, and view all posts.
            - **User**: Can view all posts and create, update, and delete their own posts only.
        - **Post Management**:
            - **Create a New Blog Post**: Form for adding new posts.
            - **View All Blog Posts**: Display a list of posts with details like title, author, content, and tags.
            - **Update a Blog Post**: Form to update an existing post.
            - **Delete a Blog Post**: Button to delete a post (role-restricted).
    - **Styling**: The frontend should be responsive and styled with **CSS** or **Bootstrap**.
2. **Backend (Node.js, Express, MongoDB)**:
    - **Authentication**:
        - **Sign Up**: Store hashed passwords using bcrypt.
        - **Login**: Generate a JWT token upon successful login.
        - **Role-Based Access**: Implement middleware to verify JWT and check user roles (admin or user).
    - **CRUD API for Posts**:
        - **GET /posts**: Allow all users to fetch posts.
        - **POST /posts**: Allow authenticated users to add posts.
        - **PUT /posts/**: Allow users to update their own posts, admins can update any post.
        - **DELETE /posts/**: Allow users to delete their own posts, admins can delete any post.
    - **Security**:
        - Use JWT tokens stored in **HTTP-only cookies** for security.
        - **Mongoose** to define the blog post and user schemas.
        - Passwords hashed using **bcrypt**.
3. **MongoDB**:
    - **BlogPost Model**:
        - Title (String)
        - Author (String, references User)
        - Content (String)
        - Tags (Array of Strings)
        - Published Date (Date)
    - **User Model**:
        - Username (String)
        - Email (String, unique)
        - Password (String, hashed)
        - Role (String, enum: [‘admin’, ‘user’])
    - Store blog post and user details in MongoDB.
4. **Routing & Communication**:
    - **Axios** or **Fetch API** to handle API calls between frontend and backend.
    - **JWT** tokens stored in HTTP-only cookies for session management.
    - Frontend handles server responses (e.g., displaying success/error messages).

### **Instructions**

1. **Backend Setup (Node.js, Express, MongoDB)**:
    - Initialize a Node.js project, install necessary dependencies (express, mongoose, bcrypt, jsonwebtoken, cors, dotenv, cookie-parser, etc.).
    - Set up:
        - **Authentication Routes** for sign-up and login.
        - **Middleware for JWT verification and role-based access**.
        - **Routes and Controllers for CRUD operations on blog posts**.
    - Connect to MongoDB using **Mongoose**.
2. **Frontend Setup (React.js)**:
    - Initialize a React app and install Axios or use Fetch API for HTTP requests.
    - **Components**:
        - **Auth Components**: SignUp.js, Login.js, and Logout functionality.
        - **Blog Components**:
            - **BlogList**: Displays all posts.
            - **BlogForm**: For adding and updating posts.
            - **BlogDetails**: Shows detailed information about a single post.
    - Implement **React Router** for navigation.
    - Store JWT tokens in cookies and set up protected routes for role-based access.

### **Folder Structure**

- **Backend**:
    
    ```bash
    bash
    Copy code
    backend/
    ├── controllers/
    │   ├── authController.js
    │   └── blogController.js
    ├── models/
    │   ├── blog.js
    │   └── user.js
    ├── routes/
    │   ├── authRoutes.js
    │   └── blogRoutes.js
    ├── middleware/
    │   ├── authMiddleware.js
    │   └── roleMiddleware.js
    ├── app.js
    └── .env
    
    ```
    
- **Frontend (React)**:
    
    ```java
    java
    Copy code
    frontend/
    ├── src/
    │   ├── components/
    │   │   ├── Auth/
    │   │   │   ├── Login.js
    │   │   │   └── SignUp.js
    │   │   ├── Blog/
    │   │   │   ├── BlogList.js
    │   │   │   ├── BlogForm.js
    │   │   │   └── BlogDetails.js
    │   ├── App.js
    │   ├── index.js
    ├── public/
    └── package.json
    
    ```
    

### **Submission**

- Upload the project to GitHub (both frontend and backend).
- Include a README file with setup instructions and .env variable specifications.

### **Evaluation Criteria**

1. **Functionality (30%)**: Complete CRUD and authentication functionality with role-based access.
2. **Code Structure (25%)**: Well-organized project structure with clean and maintainable code.
3. **UI/UX (20%)**: Responsive, user-friendly frontend with clear role-based interface differences.
4. **Security & Database Integration (25%)**: Secure JWT, bcrypt, and MongoDB integration using Mongoose.
