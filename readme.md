📦 SmartChain - Supply Chain Management System
SmartChain Banner
Firebase
License

Transform your supply chain operations with AI-powered insights, real-time tracking, and seamless management.

SmartChain is a comprehensive web-based supply chain management platform that helps businesses efficiently manage suppliers, inventory, orders, and deliveries all in one place.

✨ Features
🎯 Core Features
📊 Real-time Dashboard - Visual analytics and statistics at a glance
🏢 Supplier Management - Add, edit, and manage supplier information
📦 Inventory Tracking - Monitor stock levels with low-stock alerts
📋 Order Management - Create and track orders from start to finish
🚚 Delivery Tracking - Real-time shipment status updates
📈 Analytics & Reports - Visual charts for performance insights
🤖 AI-Powered Insights - Smart recommendations using Gemini API (Optional)
🎨 Design Features
Modern Glassmorphism UI - Beautiful frosted glass effect design
Animated Background - Smooth gradient animations
Fully Responsive - Works perfectly on mobile, tablet, and desktop
Smooth Transitions - Professional animations throughout
Dark Theme - Eye-friendly gradient color scheme
🔐 Security Features
Firebase Authentication - Secure email/password login
User Isolation - Each user sees only their own data
Firestore Security Rules - Database-level security
Session Management - Automatic logout and session handling
🚀 Quick Start
Prerequisites
Modern web browser (Chrome, Firefox, Safari, Edge)
Firebase account (Free tier works fine)
Basic text editor (VS Code recommended)
Installation
Download the Files

Bash

# Clone or download the project
git clone https://github.com/yourusername/smartchain.git
cd smartchain
Project Structure

text

smartchain/
├── index.html          # Landing page
├── main.html           # Dashboard application
└── README.md           # This file
Open the Landing Page

Simply double-click index.html or
Open with your browser
Or use a local server:
Bash

# Python 3
python -m http.server 8000

# Or use VS Code Live Server extension
🔥 Firebase Setup
Step 1: Create Firebase Project
Go to Firebase Console
Click "Add Project" or "Create a project"
Enter project name: SmartChain (or any name you prefer)
Disable Google Analytics (optional)
Click "Create Project"
Step 2: Enable Authentication
In Firebase Console, click "Authentication" from left menu
Click "Get Started"
Select "Email/Password" from Sign-in providers
Enable the Email/Password option
Click "Save"
Step 3: Create Firestore Database
Click "Firestore Database" from left menu
Click "Create Database"
Select "Start in test mode" (for development)
Choose your location (closest to you)
Click "Enable"
Step 4: Configure Security Rules
Go to "Firestore Database" → "Rules" tab
Replace the rules with:
JavaScript

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Users can only read/write their own data
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
    
    match /suppliers/{supplierId} {
      allow create: if request.auth != null && 
                      request.resource.data.userId == request.auth.uid;
      allow read, update, delete: if request.auth != null && 
                                     resource.data.userId == request.auth.uid;
    }
    
    match /inventory/{inventoryId} {
      allow create: if request.auth != null && 
                      request.resource.data.userId == request.auth.uid;
      allow read, update, delete: if request.auth != null && 
                                     resource.data.userId == request.auth.uid;
    }
    
    match /orders/{orderId} {
      allow create: if request.auth != null && 
                      request.resource.data.userId == request.auth.uid;
      allow read, update, delete: if request.auth != null && 
                                     resource.data.userId == request.auth.uid;
    }
  }
}
Click "Publish"
Step 5: Get Firebase Configuration
Click the ⚙️ (Settings) icon → "Project Settings"
Scroll down to "Your apps"
Click "</>" (Web) icon
Register app with nickname: SmartChain Web
Copy the firebaseConfig object
Step 6: Add Config to main.html
Open main.html in your text editor
Find this section (around line 700):
JavaScript

const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT.firebaseapp.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
Replace with your actual Firebase config:
JavaScript

const firebaseConfig = {
    apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
    authDomain: "smartchain-xxxxx.firebaseapp.com",
    projectId: "smartchain-xxxxx",
    storageBucket: "smartchain-xxxxx.appspot.com",
    messagingSenderId: "123456789012",
    appId: "1:123456789012:web:abcdef123456"
};
Save the file
📖 Usage Guide
Landing Page (index.html)
Open index.html in your browser
Explore the features:
🏠 Home - Hero section with main CTA
✨ Features - Overview of all capabilities
📊 About - Stats and achievements
📧 Contact - Footer with links
Click "Get Started" or "Login" → Redirects to main.html
Dashboard (main.html)
First Time Setup
Sign Up

Click "Sign Up" link
Enter your full name
Enter email address
Create password (minimum 6 characters)
Click "Create Account"
Automatic Login

You'll be logged in automatically
Dashboard will load
Using the Dashboard
📊 Dashboard Overview
View total suppliers, inventory, orders, and deliveries
See statistics at a glance
🏢 Supplier Management
Add Supplier: Click "+ Add Supplier"
Enter supplier name
Contact person name
Email address
Set status (Active/Inactive)
Edit Supplier: Click ✏️ icon
Delete Supplier: Click 🗑️ icon
📦 Inventory Management
Add Item: Click "+ Add Item"
Product name
Category (Electronics, Clothing, Food, Other)
Stock level
Minimum stock threshold
Edit Item: Click ✏️ icon
Delete Item: Click 🗑️ icon
Low Stock Alert: Automatic warnings when stock is low
📋 Order Management
Create Order: Click "+ Create Order"
Select product from dropdown
Enter quantity
Choose status
View Orders: See all orders in table
Delete Order: Click 🗑️ icon
🛠️ Technologies Used
Frontend
HTML5 - Structure and semantics
CSS3 - Styling and animations
Glassmorphism effects
CSS Grid & Flexbox
Custom animations
JavaScript (ES6+) - Interactivity and logic
Chart.js - Data visualization (ready to implement)
Backend & Database
Firebase Authentication - User management
Cloud Firestore - NoSQL database
Firebase SDK - Client-side integration
Design
Google Fonts - Poppins font family
SVG Graphics - Scalable icons and illustrations
Gradient Backgrounds - Animated color schemes
📱 Browser Support
Browser	Version	Support
Chrome	90+	✅ Full
Firefox	88+	✅ Full
Safari	14+	✅ Full
Edge	90+	✅ Full
Opera	76+	✅ Full
🎨 Customization
Change Color Scheme
Edit main.html CSS variables:

CSS

:root {
    --primary: #2563eb;      /* Primary blue */
    --secondary: #3b82f6;    /* Secondary blue */
    --success: #10b981;      /* Success green */
    --warning: #f59e0b;      /* Warning orange */
    --danger: #ef4444;       /* Danger red */
}
Modify Gradient Background
CSS

.animated-bg {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
    /* Change to your preferred colors */
}
🐛 Troubleshooting
Common Issues
❌ "Permission Denied" Error
Problem: Can't add/edit suppliers or inventory

Solution:

Check Firebase Firestore Rules
Make sure you're logged in
Verify userId field is being saved correctly
Use the security rules provided above
❌ "Firebase not defined" Error
Problem: Firebase SDK not loading

Solution:

Check internet connection
Verify Firebase CDN links are correct
Make sure scripts are loaded before initialization
❌ Authentication Not Working
Problem: Can't login or signup

Solution:

Check Firebase Authentication is enabled
Verify Email/Password provider is active
Check console for specific error messages
Ensure firebaseConfig is correct
❌ Data Not Showing
Problem: Dashboard is empty

Solution:

Open browser console (F12)
Check for JavaScript errors
Verify Firestore connection
Try logging out and back in
📊 Database Structure
Collections
users
JavaScript

{
  name: "John Doe",
  email: "john@example.com",
  createdAt: Timestamp
}
suppliers
JavaScript

{
  name: "ABC Suppliers",
  contact: "Jane Smith",
  email: "jane@abc.com",
  status: "Active",
  userId: "user_id_here",
  createdAt: Timestamp
}
inventory
JavaScript

{
  product: "Laptop",
  category: "Electronics",
  stock: 50,
  minStock: 20,
  userId: "user_id_here",
  createdAt: Timestamp
}
orders
JavaScript

{
  productId: "product_id",
  productName: "Laptop",
  quantity: 10,
  status: "Pending",
  userId: "user_id_here",
  createdAt: Timestamp
}
