# DRF JWT Authentication API

This is a Django REST Framework (DRF) project implementing JWT authentication using `APIView`. It provides user registration, login, and a protected API endpoint.

## 🚀 Features
- User Registration API
- User Login API (JWT Token Generation)
- Protected API (Requires JWT Authentication)

## 📌 Installation

### 1. Clone the Repository
```sh
git clone https://github.com/your-repo/drf-jwt-auth.git
cd drf-jwt-auth
```

### 2. Create a Virtual Environment
```sh
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### 3. Install Dependencies
```sh
pip install -r requirements.txt
```

### 4. Apply Migrations
```sh
python manage.py makemigrations
python manage.py migrate
```

### 5. Run the Development Server
```sh
python manage.py runserver
```

## 🛠 API Endpoints

### 1. **User Registration**
- **Endpoint:** `/api/register/`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
      "username": "testuser",
      "email": "test@example.com",
      "password": "testpass123"
  }
  ```
- **Response:**
  ```json
  {
      "message": "User registered successfully"
  }
  ```

### 2. **User Login (JWT Token Generation)**
- **Endpoint:** `/api/login/`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
      "username": "testuser",
      "password": "testpass123"
  }
  ```
- **Response:**
  ```json
  {
      "refresh": "your_refresh_token_here",
      "access": "your_access_token_here"
  }
  ```

### 3. **Protected API (Requires Authentication)**
- **Endpoint:** `/api/protected/`
- **Method:** `GET`
- **Headers:**
  ```json
  {
      "Authorization": "Bearer your_access_token_here"
  }
  ```
- **Response:**
  ```json
  {
      "message": "This is a protected view, you are authenticated!"
  }
  ```

## 📦 Project Structure
```
 drf_jwt_project/
 ├── drf_jwt_project/
 │   ├── __init__.py
 │   ├── settings.py
 │   ├── urls.py
 │   ├── wsgi.py
 ├── users/
 │   ├── __init__.py
 │   ├── models.py
 │   ├── views.py
 │   ├── serializers.py
 │   ├── urls.py
 ├── manage.py
 ├── requirements.txt
```

## 🔑 Authentication:
- Uses `JWT` authentication via `djangorestframework-simplejwt`
- `access` token expires in 30 minutes
- `refresh` token expires in 1 day

## 📜 License
This project is licensed under the MIT License.

## 🙌 Contributing
Pull requests are welcome! Feel free to contribute and improve the project.

## 📞 Contact
For questions or suggestions, contact me at [smitpanchal42@gmail.com](mailto:smitpanchal42@gmail.com).
