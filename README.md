# FI_MONEY_assignment

An inventory management application built with Node.js, Express, and MongoDB.

## Screenshots

### User Interface
![Login](assets/login.jpeg)
*Login Page*

![Register](assets/register.jpeg)
*User Registration*

![Add Product](assets/addProduct.jpeg)
*Add Product Page*

![Products](assets/products.jpeg)
*Products Overview*

![Quantity Management](assets/quantity.jpeg)
*Quantity Management*



## Features

- User authentication with JWT tokens
- Secure password hashing with bcrypt
- MongoDB database integration
- RESTful API architecture
- Environment variable configuration

## Tech Stack

- **Backend**: Node.js with Express.js
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JSON Web Tokens (JWT)
- **Security**: bcryptjs for password hashing
- **Development**: Nodemon for auto-restart

## Prerequisites

Before running this application, make sure you have the following installed:

### Option 1: Local Development
- [Node.js](https://nodejs.org/) (version 14 or higher)
- [MongoDB](https://www.mongodb.com/) (local installation or MongoDB Atlas)
- [npm](https://www.npmjs.com/) (comes with Node.js)

### Option 2: Docker Development
- [Docker](https://www.docker.com/) (version 20.10 or higher)
- [Docker Compose](https://docs.docker.com/compose/) (usually comes with Docker Desktop)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd FI_MONEY_assignment
```

### Option 1: Local Development

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory and add your environment variables:
```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/fimoney
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development
```

### Option 2: Docker Development

2. No additional installation required! Docker will handle everything.

3. Create a `.env` file in the root directory (optional for Docker, as environment variables are configured in docker-compose.yml):
```env
PORT=5000
MONGO_URI=mongodb://admin:password123@localhost:27017/fimoney?authSource=admin
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development
```

## Environment Variables

Create a `.env` file with the following variables:

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| `PORT` | Server port number | No | 5000 |
| `MONGO_URI` | MongoDB connection string | Yes | - |
| `JWT_SECRET` | Secret key for JWT token generation | Yes | - |
| `NODE_ENV` | Environment (development/production) | No | development |

**Note**: When using Docker, the MongoDB connection is automatically configured in the docker-compose.yml file.

## Usage

### Option 1: Local Development

#### Development Mode

To start the development server with auto-restart:

```bash
npm run dev
```

The server will start on `http://localhost:5000` (or your specified PORT).

#### Production Mode

To start the server in production:

```bash
node server.js
```

### Option 2: Docker Development

#### Quick Start

To build and start all services (MongoDB + Node.js app):

```bash
docker-compose up --build
```

#### Background Mode

To run services in the background:

```bash
docker-compose up -d
```

#### View Logs

```bash
docker-compose logs -f
```

#### Stop Services

```bash
docker-compose down
```

#### Stop and Remove Data

```bash
docker-compose down -v
```

#### Rebuild After Changes

```bash
docker-compose up --build
```

### Access Points

- **Application**: http://localhost:5000
- **MongoDB**: localhost:27017 (if using Docker, credentials: admin/password123)

## API Endpoints

*Note: Update this section with your actual API endpoints*

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/profile` - Get user profile (protected)

### Inventory Management
- `GET /api/products` - Get all products
- `POST /api/products` - Add new product
- `PUT /api/products/:id` - Update product
- `DELETE /api/products/:id` - Delete product
- `PUT /api/products/:id/quantity` - Update product quantity

## Project Structure

```
FI_MONEY_assignment/
├── server.js              # Main server file
├── package.json           # Project dependencies and scripts
├── docker-compose.yml     # Docker orchestration file
├── Dockerfile            # Docker image definition
├── .dockerignore         # Docker build exclusions
├── .env                  # Environment variables (create this)
├── .gitignore           # Git ignore file (create this)
├── assets/              # UI screenshots and images
│   ├── addProduct.jpeg  # Add product page screenshot
│   ├── login.jpeg       # Login page screenshot
│   ├── products.jpeg    # Products overview screenshot
│   ├── quantity.jpeg    # Quantity management screenshot
│   └── register.jpeg    # Registration page screenshot
├── config/              # Configuration files
├── controllers/         # Route controllers
├── middleware/          # Custom middleware
├── models/              # Database models
├── routes/              # API routes
├── test.py             # Test files
└── README.md           # Project documentation
```

## Dependencies

### Production Dependencies
- **express**: Web framework for Node.js
- **mongoose**: MongoDB object modeling tool
- **jsonwebtoken**: JWT implementation for authentication
- **bcryptjs**: Password hashing library
- **dotenv**: Environment variable loader

### Development Dependencies
- **nodemon**: Development tool for auto-restarting server

### Docker Dependencies
- **Docker**: Containerization platform
- **Docker Compose**: Multi-container orchestration

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Security Notes

- Always use HTTPS in production
- Keep your JWT secret secure and use a strong, random string
- Regularly update dependencies to patch security vulnerabilities
- Use environment variables for sensitive configuration
- Implement rate limiting for API endpoints

## License

This project is licensed under the ISC License.

## Support

If you encounter any issues or have questions, please open an issue in the repository.

---

**Version**: 1.0.0
