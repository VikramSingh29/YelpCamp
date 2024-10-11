YelpCamp
YelpCamp is a full-stack web application that allows users to create and share campgrounds. It also features reviews and ratings for campgrounds, user authentication, and the ability to manage personal campgrounds. The project is built using Node.js, Express, MongoDB, and Bootstrap.

Table of Contents
Features
Technologies
Installation
Usage
Project Structure
API Routes
Contributing
License
Features
User authentication (signup, login, logout)
Authorization: campground ownership and review protection
CRUD operations for campgrounds and reviews
Image upload for campgrounds using Cloudinary
Responsive UI design using Bootstrap
Map integration using Mapbox for campground locations
Error handling for invalid routes and user inputs
Technologies
Backend: Node.js, Express, MongoDB, Mongoose
Frontend: EJS (Embedded JavaScript templates), Bootstrap
Authentication: Passport.js (local strategy)
Image Hosting: Cloudinary API
Maps: Mapbox API
Validation: Joi validation middleware
Session & Cookies: Express-session, Connect-flash
Installation
Prerequisites
Node.js (v14 or above)
MongoDB (local or Atlas instance)
Cloudinary account (for image storage)
Mapbox API key
Setup
Clone the repository:

bash
Copy code
git clone https://github.com/VikramSingh29/yelpcamp.git
cd yelpcamp
Install dependencies:

bash
Copy code
npm install
Set up environment variables:

Create a .env file in the root of the project and add the following:

makefile
Copy code
CLOUDINARY_CLOUD_NAME=your-cloudinary-cloud-name
CLOUDINARY_KEY=your-cloudinary-api-key
CLOUDINARY_SECRET=your-cloudinary-api-secret
MAPBOX_TOKEN=your-mapbox-token
DB_URL=mongodb://localhost:27017/yelp-camp
SECRET=your-session-secret
Start the MongoDB server:

bash
Copy code
mongod
Run the app:

bash
Copy code
node app.js
Open your browser and navigate to http://localhost:3000.

Usage
Sign up for an account to create your own campgrounds.
View, edit, and delete campgrounds you own.
Add reviews to other campgrounds.
View campgrounds on the map, filter, and search by location.
Project Structure
bash
Copy code
YelpCamp/
│
├── public/                   # Static assets (CSS, JS, images)
│   ├── stylesheets/
│   └── scripts/
│
├── routes/                   # Application routes
│   ├── campgrounds.js        # Routes for campgrounds
│   ├── reviews.js            # Routes for reviews
│   └── users.js              # Routes for authentication
│
├── views/                    # EJS templates
│   ├── campgrounds/
│   ├── layouts/
│   ├── partials/
│   └── reviews/
│
├── models/                   # Mongoose models
│   ├── campground.js
│   ├── review.js
│   └── user.js
│
├── middleware/               # Custom middleware
│   └── index.js
│
├── app.js                    # Main application file
├── package.json              # Node.js dependencies
└── .env                      # Environment variables (ignored in Git)
API Routes
Campgrounds
GET /campgrounds – View all campgrounds
GET /campgrounds/:id – View a specific campground
POST /campgrounds – Create a new campground (authenticated users)
PUT /campgrounds/:id – Edit a campground (authenticated users)
DELETE /campgrounds/:id – Delete a campground (authorized users)
Reviews
POST /campgrounds/:id/reviews – Add a review to a campground
DELETE /campgrounds/:id/reviews/:reviewId – Delete a review (review owner only)
Users
GET /register – Show registration form
POST /register – Register a new user
GET /login – Show login form
POST /login – Login user
GET /logout – Logout user
Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Fork the repository
Create your feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a pull request
License
This project is licensed under the MIT License. See the LICENSE file for details.
