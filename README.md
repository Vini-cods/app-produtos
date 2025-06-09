# 📱 Produtos App

A modern mobile application built with **React Native** (Expo) for product management through a **Node.js + Express** API connected to **MySQL**.

##  Features

- 📦 **Product listing** - View all products from the database
- 🔍 **Product details** - Fetch specific information by ID
- 🔗 **RESTful API** - Complete integration between frontend and backend
- 📱 **Responsive interface** - Optimized design for mobile devices
- ⚡ **Optimized performance** - Fast and efficient loading

## 🛠️ Tech Stack

### 📱 Mobile (Frontend)
- **[React Native](https://reactnative.dev/)** - Mobile development framework
- **[Expo](https://expo.dev/)** - Development and deployment platform
- **[Axios](https://axios-http.com/)** - HTTP client for API requests
- **JavaScript/JSX** - Programming language

### 🖥️ Backend (API)
- **[Node.js](https://nodejs.org/)** - JavaScript runtime on server
- **[Express](https://expressjs.com/)** - Minimalist web framework
- **[MySQL](https://www.mysql.com/)** - Database management system
- **[CORS](https://www.npmjs.com/package/cors)** - Cross-Origin Resource Sharing middleware

## 📁 Project Structure

```
produtos-app/
├── 📱 Frontend (React Native)
│   ├── 📄 App.js               # Main React Native component
│   ├── 📄 index.js             # Expo entry point
│   ├── 📄 app.json             # Expo project configuration
│   ├── 📄 package.json         # Frontend dependencies
│   └── 📁 assets/              # Images and resources
│
├── 🖥️ Backend (Node.js/Express)
│   ├── 📄 server.js            # Express server and MySQL API
│   ├── 📄 package.json         # Backend dependencies
│   └── 📁 config/              # Database configurations
│
└── 📄 README.md                # Project documentation
```

## 🚀 How to Run

### 📋 Prerequisites

- [Node.js](https://nodejs.org/) (version 14 or higher)
- [MySQL](https://www.mysql.com/) installed and running
- [Expo CLI](https://docs.expo.dev/get-started/installation/)
- A mobile device or emulator

### 🗄️ Database Setup

1. **Start MySQL** and create the database:
   ```sql
   CREATE DATABASE exemplo_app;
   USE exemplo_app;
   ```

2. **Create the products table:**
   ```sql
   CREATE TABLE produtos (
     id INT AUTO_INCREMENT PRIMARY KEY,
     nome VARCHAR(255) NOT NULL,
     preco DECIMAL(10,2) NOT NULL,
     descricao TEXT,
     categoria VARCHAR(100),
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

3. **Insert sample data:**
   ```sql
   INSERT INTO produtos (nome, preco, descricao, categoria) VALUES
   ('iPhone 14', 4999.99, 'Apple smartphone with 128GB', 'Electronics'),
   ('MacBook Pro', 12999.99, 'Apple M2 13-inch notebook', 'Computers'),
   ('AirPods Pro', 1899.99, 'Wireless earphones with noise cancellation', 'Accessories');
   ```

### 🖥️ Backend (API)

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/produtos-app.git
   cd produtos-app
   ```

2. **Install backend dependencies:**
   ```bash
   npm install express mysql2 cors dotenv
   ```

3. **Configure environment variables:**
   ```bash
   # Create a .env file in the project root
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=your_password
   DB_NAME=exemplo_app
   PORT=3000
   ```

4. **Start the server:**
   ```bash
   node server.js
   ```

5. **Test the API:**
   - 📍 API available at: `http://localhost:3000`
   - 📦 List products: `GET /api/produtos`
   - 🔍 Product by ID: `GET /api/produtos/:id`

### 📱 Frontend (React Native)

1. **Navigate to frontend folder:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Install Expo CLI (if not installed):**
   ```bash
   npm install -g expo-cli
   ```

4. **Start the application:**
   ```bash
   npx expo start
   ```

5. **Run on device:**
   - 📱 Use **Expo Go** app to scan the QR code
   - 🖥️ Use Android/iOS emulator
   - 🌐 Run in web browser

### ⚠️ Network Configuration

**For physical devices:**
- Replace `localhost` with your local IP in the frontend code
- Example: `http://192.168.1.100:3000/api/produtos`
- Use `ipconfig` (Windows) or `ifconfig` (Mac/Linux) to find your IP

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/api/produtos` | Get all products |
| GET    | `/api/produtos/:id` | Get product by ID |
| POST   | `/api/produtos` | Create new product |
| PUT    | `/api/produtos/:id` | Update product |
| DELETE | `/api/produtos/:id` | Delete product |

## 🧪 Testing the API

### Using cURL:

```bash
# Get all products
curl http://localhost:3000/api/produtos

# Get product by ID
curl http://localhost:3000/api/produtos/1

# Create new product
curl -X POST http://localhost:3000/api/produtos \
  -H "Content-Type: application/json" \
  -d '{"nome":"New Product","preco":99.99,"descricao":"Product description","categoria":"Category"}'
```

### Using Postman or Insomnia:
- Import the API endpoints
- Test all CRUD operations
- Verify response formats

## 🎨 UI/UX Features

- 📋 **Product List** - Clean FlatList with product cards
- 🔍 **Search & Filter** - Find products quickly
- 📱 **Responsive Design** - Works on all screen sizes
- 🎭 **Loading States** - Smooth loading animations
- ⚠️ **Error Handling** - User-friendly error messages

## 🔧 Useful Commands

```bash
# Backend
npm install express mysql2 cors dotenv    # Install backend dependencies
node server.js                           # Start the server
npm run dev                              # Start with nodemon (if configured)

# Frontend  
npx expo start                           # Start Expo development server
npx expo start --clear                   # Start with cache cleared
npx expo build:android                   # Build for Android
npx expo build:ios                       # Build for iOS
```


## 🚨 Security Considerations

- **Environment Variables** - Never commit `.env` files
- **Database Security** - Use strong passwords and proper user permissions
- **API Security** - Implement rate limiting and input validation
- **HTTPS** - Use HTTPS in production environments
- **Authentication** - Implement proper user authentication


## 📌 Notes

- This is a learning project meant for educational purposes and prototyping
- Backend uses basic MySQL configuration - secure it properly for production
- Remember to update API URLs when deploying to production
- Consider using environment-specific configurations for different stages

---
