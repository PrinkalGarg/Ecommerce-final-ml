# 🛍️ E-Commerce Platform with AI-Powered Visual Search

A full-stack e-commerce application featuring AI-powered visual search capabilities using Jina AI, built with React, Node.js, and MongoDB.

## 🌟 Features

### 🎯 Core Features
- **AI-Powered Visual Search**: Upload an image to find similar products using Jina AI embeddings
- **Product Management**: Complete CRUD operations for products with multiple images
- **User Authentication**: Secure login/registration with JWT tokens
- **Shopping Cart**: Add, update, and manage cart items with size selection
- **Order Management**: Place orders with multiple payment methods (COD, Stripe, Razorpay)
- **Admin Panel**: Dedicated admin interface for product and order management
- **Responsive Design**: Mobile-first design with Tailwind CSS

### 🤖 AI Features
- **Visual Search**: Upload product images to find visually similar items
- **Image Embeddings**: Automatic generation of embeddings for all product images
- **Similarity Matching**: Cosine similarity-based product recommendations
- **Multi-image Support**: Support for multiple product images with individual embeddings

## 🏗️ Architecture

### Frontend Applications
- **Customer Frontend** (`Frontend/`): React-based customer-facing application
- **Admin Panel** (`admin/`): React-based admin dashboard for product management

### Backend
- **API Server** (`Backend/`): Node.js/Express REST API with MongoDB
- **AI Integration**: Jina AI for visual search and embeddings
- **Cloud Storage**: Cloudinary for image storage and management

## 🛠️ Tech Stack

### Frontend
- **React 18** with Vite
- **React Router** for navigation
- **Tailwind CSS** for styling
- **Framer Motion** for animations
- **Axios** for API calls
- **React Toastify** for notifications

### Backend
- **Node.js** with Express
- **MongoDB** with Mongoose
- **JWT** for authentication
- **Multer** for file uploads
- **Cloudinary** for image storage
- **Jina AI** for visual search
- **Bcrypt** for password hashing

### AI & ML
- **Jina AI API**: For generating image embeddings
- **CLIP Model**: `jina-clip-v1` for visual similarity
- **Cosine Similarity**: For matching similar products

## 📁 Project Structure

```
Ecomerce/
├── Frontend/                 # Customer-facing React app
│   ├── src/
│   │   ├── component/        # Reusable components
│   │   ├── pages/           # Page components
│   │   ├── context/         # React context (ShopContext)
│   │   └── assets/          # Static assets
├── admin/                   # Admin panel React app
│   ├── src/
│   │   ├── components/      # Admin components
│   │   └── pages/          # Admin pages
├── Backend/                 # Node.js API server
│   ├── config/             # Database & Cloudinary config
│   ├── controller/         # Route controllers
│   ├── middleware/         # Auth & file upload middleware
│   ├── models/             # MongoDB schemas
│   ├── routes/             # API routes
│   └── server.js           # Main server file
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local or cloud)
- Cloudinary account
- Jina AI API key

### Environment Variables

Create a `.env` file in the `Backend/` directory:

```env
# Database
MongoDB_URL=mongodb://localhost:27017
# or MongoDB Atlas: mongodb+srv://username:password@cluster.mongodb.net

# JWT Secret
JWT_SECRET=your_jwt_secret_key

# Cloudinary Configuration
Cloudinary_NAME=your_cloudinary_cloud_name
Cloudinary_API_Key=your_cloudinary_api_key
Cloudinary_API_SECRETE=your_cloudinary_api_secret

# Jina AI Configuration
JINA_API_KEY=your_jina_api_key

# Admin Credentials
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=admin_password

# Optional: Search Configuration
SEARCH_SAMPLE_SIZE=2000
```

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Ecomerce
   ```

2. **Install Backend Dependencies**
   ```bash
   cd Backend
   npm install
   ```

3. **Install Frontend Dependencies**
   ```bash
   cd ../Frontend
   npm install
   ```

4. **Install Admin Panel Dependencies**
   ```bash
   cd ../admin
   npm install
   ```

### Running the Application

1. **Start the Backend Server**
   ```bash
   cd Backend
   npm run server
   ```
   Server will run on `http://localhost:3000`

2. **Start the Customer Frontend**
   ```bash
   cd Frontend
   npm run dev
   ```
   Frontend will run on `http://localhost:5173`

3. **Start the Admin Panel**
   ```bash
   cd admin
   npm run dev
   ```
   Admin panel will run on `http://localhost:5174`

## 🔧 API Endpoints

### Authentication
- `POST /api/user/register` - User registration
- `POST /api/user/login` - User login
- `POST /api/user/admin` - Admin login

### Products
- `GET /api/product/list` - Get all products
- `POST /api/product/add` - Add new product (Admin only)
- `POST /api/product/remove` - Remove product (Admin only)
- `POST /api/product/listsingle` - Get single product
- `POST /api/product/search-image` - Visual search by image

### Orders
- `POST /api/order/place` - Place order (COD)
- `POST /api/order/userorder` - Get user orders
- `GET /api/order/listadmin` - Get all orders (Admin)
- `POST /api/order/stripe` - Stripe payment
- `POST /api/order/razor` - Razorpay payment

### Cart
- `POST /api/cart/add` - Add to cart
- `POST /api/cart/update` - Update cart
- `POST /api/cart/get` - Get user cart

## 🤖 AI Visual Search

The application uses Jina AI's CLIP model for visual similarity search:

### How it Works
1. **Image Upload**: Users upload an image for search
2. **Embedding Generation**: Jina AI generates embeddings for the query image
3. **Similarity Matching**: Cosine similarity is computed against all product embeddings
4. **Results Ranking**: Products are ranked by similarity score

### Implementation Details
- **Model**: `jina-clip-v1` for image embeddings
- **Embedding Storage**: Each product image has its own embedding
- **Aggregation**: Product-level embeddings are computed as mean of image embeddings
- **Search Algorithm**: Cosine similarity with configurable sample size

## 🎨 Key Components

### Frontend Components
- **Hero**: Landing page hero section
- **ProductDisplay**: Product listing and display
- **CartTotal**: Shopping cart summary
- **Navbar**: Navigation with cart count
- **Footer**: Site footer with links

### Admin Components
- **AddProduct**: Product creation form with image upload
- **ListProduct**: Product management interface
- **Orders**: Order management dashboard

## 🔐 Authentication & Security

### User Authentication
- JWT-based authentication
- Password hashing with bcrypt
- Protected routes with middleware

### Admin Authentication
- Separate admin login system
- Environment-based admin credentials
- Admin-only routes protection

## 📱 Responsive Design

- Mobile-first approach
- Tailwind CSS for styling
- Responsive grid layouts
- Touch-friendly interfaces

## 🚀 Deployment

### Backend Deployment
1. Set up MongoDB Atlas or local MongoDB
2. Configure Cloudinary account
3. Get Jina AI API key
4. Set environment variables
5. Deploy to platforms like Render, Heroku, or Vercel

### Frontend Deployment
1. Build the production version: `npm run build`
2. Deploy to platforms like Netlify, Vercel, or GitHub Pages

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

For support and questions:
- Create an issue in the repository
- Check the documentation
- Review the API endpoints

## 🔮 Future Enhancements

- [ ] Advanced filtering and sorting
- [ ] Recommendation engine
- [ ] Real-time notifications
- [ ] Multi-language support
- [ ] Advanced analytics dashboard
- [ ] Mobile app development
- [ ] Social login integration
- [ ] Advanced payment methods

---

**Built with ❤️ using React, Node.js, MongoDB, and Jina AI**
