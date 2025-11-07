# Professional E-commerce Store - MERN Stack

A modern, professional e-commerce platform built with the MERN stack (MongoDB, Express.js, React, Node.js) featuring multi-language support, real-time notifications, and comprehensive admin dashboard.

## 🌟 Features

### 🌍 Multi-Language Support
- **Languages**: English, French, Arabic
- **RTL Support**: Proper Arabic text direction while maintaining layout structure
- **Dynamic Translation**: Real-time language switching with react-i18next
- **Localized Content**: Product names, descriptions, and UI elements in all languages

### 💰 Multi-Currency Support
- **Currencies**: USD, EUR, DZD (Algerian Dinar)
- **Real-time Conversion**: Dynamic price conversion with admin-configurable exchange rates
- **Base Currency**: USD with automatic conversion for display

### 🎨 Modern UI/UX
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Dark/Light Mode**: System preference detection with manual toggle
- **Smooth Animations**: Framer Motion for enhanced user experience
- **Accessibility**: WCAG compliant with keyboard navigation support

### 🛒 E-commerce Features
- **Product Catalog**: Advanced filtering, sorting, and search functionality
- **Shopping Cart**: Persistent cart with guest and user support
- **Checkout Process**: Streamlined checkout with multiple payment options
- **Order Management**: Complete order lifecycle tracking
- **User Profiles**: Address management and order history

### 🔐 Authentication & Security
- **JWT Authentication**: Secure token-based authentication
- **Role-based Access**: User and admin role management
- **Input Validation**: Comprehensive server-side validation
- **Security Headers**: Helmet.js for security best practices
- **Rate Limiting**: API rate limiting to prevent abuse

### 📊 Admin Dashboard
- **Analytics**: Sales charts, revenue tracking, and customer insights
- **Product Management**: CRUD operations with image upload
- **Order Management**: Status updates and order tracking
- **Customer Management**: User overview and management
- **Real-time Notifications**: Socket.IO for instant updates
- **Low Stock Alerts**: Automatic inventory monitoring

### 🔄 Real-time Features
- **Live Notifications**: New orders and feedback alerts
- **Socket.IO Integration**: Real-time communication
- **Order Status Updates**: Live order tracking
- **Admin Notifications**: Instant admin alerts

### 📱 Additional Features
- **Customer Reviews**: Product rating and review system
- **Feedback System**: Contact forms and customer testimonials
- **Image Gallery**: Product image carousel with zoom
- **Search & Filter**: Advanced product discovery
- **Responsive Images**: Optimized image loading

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ and npm
- MongoDB (local or Atlas)
- Docker (optional)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd e-com
   ```

2. **Install server dependencies**
   ```bash
   cd server
   npm install
   ```

3. **Install client dependencies**
   ```bash
   cd ../client
   npm install
   ```

4. **Environment Setup**
   
   Create `.env` file in the server directory:
   ```env
   NODE_ENV=development
   PORT=5000
   MONGO_URI=mongodb+srv://Mg_focus_dz:Mohamed-2025@cluster0.gxxhspn.mongodb.net/ecommerce
   JWT_SECRET=your_super_secret_jwt_key_here_replace_with_strong_secret
   JWT_EXPIRE=30d
   CLIENT_URL=http://localhost:3000
   
   # Cloudinary (for image uploads)
   CLOUDINARY_CLOUD_NAME=your_cloud_name
   CLOUDINARY_API_KEY=your_api_key
   CLOUDINARY_API_SECRET=your_api_secret
   
   # Stripe (for payments)
   STRIPE_SECRET_KEY=sk_test_your_stripe_secret_key
   STRIPE_PUBLISHABLE_KEY=pk_test_your_stripe_publishable_key
   
   # Exchange Rates API (optional)
   EXCHANGE_RATES_API_KEY=your_exchange_rates_api_key
   ```

5. **Seed the database**
   ```bash
   cd server
   npm run seed
   ```

6. **Start the development servers**
   
   Terminal 1 (Server):
   ```bash
   cd server
   npm run dev
   ```
   
   Terminal 2 (Client):
   ```bash
   cd client
   npm run dev
   ```

7. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000
   - Admin Dashboard: http://localhost:3000/dashboard

### Docker Setup

1. **Using Docker Compose**
   ```bash
   docker-compose up -d
   ```

2. **Access the application**
   - Frontend: http://localhost:3000
   - Backend: http://localhost:5000
   - MongoDB: localhost:27017

## 🔑 Default Login Credentials

After seeding the database:

- **Admin**: admin@ecommerce.com / admin123
- **User**: ahmed@example.com / user123
- **User**: marie@example.com / user123

## 📁 Project Structure

```
e-com/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── pages/         # Page components
│   │   ├── contexts/      # React contexts
│   │   ├── hooks/         # Custom hooks
│   │   ├── utils/         # Utility functions
│   │   ├── locales/       # Translation files
│   │   └── assets/        # Static assets
│   ├── public/            # Public assets
│   └── package.json
├── server/                # Node.js backend
│   ├── models/           # Mongoose models
│   ├── routes/           # Express routes
│   ├── controllers/      # Route controllers
│   ├── middleware/       # Custom middleware
│   ├── utils/            # Utility functions
│   ├── config/           # Configuration files
│   └── package.json
├── docker-compose.yml    # Docker configuration
└── README.md
```

## 🌐 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user
- `PUT /api/auth/profile` - Update profile

### Products
- `GET /api/products` - Get all products (with filters)
- `GET /api/products/:id` - Get single product
- `POST /api/products` - Create product (Admin)
- `PUT /api/products/:id` - Update product (Admin)
- `DELETE /api/products/:id` - Delete product (Admin)

### Orders
- `POST /api/orders` - Create order
- `GET /api/orders` - Get orders
- `GET /api/orders/:id` - Get single order
- `PUT /api/orders/:id/status` - Update order status (Admin)

### Cart
- `GET /api/cart` - Get cart
- `POST /api/cart/items` - Add item to cart
- `PUT /api/cart/items/:id` - Update cart item
- `DELETE /api/cart/items/:id` - Remove cart item

### Analytics (Admin)
- `GET /api/analytics/dashboard` - Dashboard analytics
- `GET /api/analytics/sales` - Sales reports
- `GET /api/analytics/products` - Product performance

### Exchange Rates
- `GET /api/rates` - Get current rates
- `PUT /api/rates` - Update rates (Admin)
- `POST /api/rates/convert` - Convert currency

## 🎨 Customization

### Adding New Languages

1. **Create translation file**
   ```bash
   # Add new language file
   client/src/locales/de.json
   ```

2. **Update i18n configuration**
   ```javascript
   // client/src/i18n.js
   import deTranslations from './locales/de.json'
   
   const resources = {
     // ... existing languages
     de: {
       translation: deTranslations
     }
   }
   ```

3. **Add language option to UI**
   Update language selector component to include the new language.

### Customizing Themes

1. **Update Tailwind configuration**
   ```javascript
   // client/tailwind.config.js
   theme: {
     extend: {
       colors: {
         primary: {
           // Your custom primary colors
         }
       }
     }
   }
   ```

2. **Update CSS variables**
   ```css
   /* client/src/index.css */
   :root {
     --primary-color: #your-color;
   }
   ```

### Adding Payment Methods

1. **Server-side integration**
   ```javascript
   // server/routes/payments.js
   // Add new payment provider logic
   ```

2. **Client-side components**
   ```javascript
   // client/src/components/checkout/PaymentMethods.jsx
   // Add new payment method UI
   ```

## 🧪 Testing

### Running Tests

```bash
# Server tests
cd server
npm test

# Client tests
cd client
npm test
```

### Test Coverage

```bash
# Generate coverage report
npm run test:coverage
```

## 🚀 Deployment

### Heroku Deployment

1. **Prepare for deployment**
   ```bash
   # Install Heroku CLI
   npm install -g heroku
   
   # Login to Heroku
   heroku login
   ```

2. **Deploy server**
   ```bash
   cd server
   heroku create your-app-name-api
   heroku config:set NODE_ENV=production
   heroku config:set MONGO_URI=your_mongodb_uri
   # Set other environment variables
   git push heroku main
   ```

3. **Deploy client**
   ```bash
   cd client
   heroku create your-app-name
   heroku buildpacks:set mars/create-react-app
   heroku config:set VITE_API_URL=https://your-app-name-api.herokuapp.com/api
   git push heroku main
   ```

### Vercel Deployment

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Deploy client**
   ```bash
   cd client
   vercel --prod
   ```

3. **Configure environment variables**
   Set environment variables in Vercel dashboard.

### Docker Production

```bash
# Build production images
docker-compose -f docker-compose.prod.yml up -d
```

## 🔧 Configuration

### Environment Variables

#### Server (.env)
```env
NODE_ENV=production
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
JWT_EXPIRE=30d
CLIENT_URL=your_client_url
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
STRIPE_SECRET_KEY=your_stripe_secret
EXCHANGE_RATES_API_KEY=your_rates_api_key
```

#### Client (.env)
```env
VITE_API_URL=your_api_url
VITE_SOCKET_URL=your_socket_url
VITE_STRIPE_PUBLISHABLE_KEY=your_stripe_public_key
```

## 📚 Documentation

### API Documentation
- Postman Collection: `docs/postman_collection.json`
- OpenAPI Spec: `docs/api-spec.yaml`

### Component Documentation
- Storybook: `npm run storybook`
- Component docs in `docs/components/`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support and questions:
- Create an issue on GitHub
- Email: support@yourstore.com
- Documentation: [Wiki](https://github.com/yourrepo/wiki)

## 🙏 Acknowledgments

- React team for the amazing framework
- MongoDB team for the database
- Tailwind CSS for the utility-first CSS framework
- All open-source contributors

---

**Built with ❤️ using the MERN Stack**