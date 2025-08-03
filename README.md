# 🛒 E-Commerce Web App – Firebase-Based Shopping Platform

This is a fully functional E-Commerce website built with **HTML**, **CSS**, **JavaScript**, and **Firebase**. It allows users to register, browse products, add items to the cart, enter address, make mock payments, and view their order history.

> ✅ Live and Safe on Firebase Hosting  
> 🎓 Ideal for students and beginner developers  
> 🌙 Modern dark theme + fully responsive  

---

## 🌐 Live Demo

🚀 [Click to open the live site](https://ecommerce-eb22f.web.app)

---

## 📸 Preview Screens

| Register | Login | Home |
|---------|-------|------|
| ![](https://github.com/yaswanthaddula/Ecommerce/blob/main/register.png) | ![](https://github.com/yaswanthaddula/Ecommerce/blob/main/login.png) | ![](https://github.com/yaswanthaddula/Ecommerce/blob/main/home.png) |

| Cart | Address | Address (Full) |
|------|---------|----------------|
| ![](https://github.com/yaswanthaddula/Ecommerce/blob/main/cart.png) | ![](https://github.com/yaswanthaddula/Ecommerce/blob/main/address.png) | ![](https://github.com/yaswanthaddula/Ecommerce/blob/main/address1.png) |

| Success | History |
|---------|---------|
| ![](https://github.com/yaswanthaddula/Ecommerce/blob/main/success.png) | ![](https://github.com/yaswanthaddula/Ecommerce/blob/main/history.png) |

---

## 📁 Folder Structure

Ecommerce/
├── firebase.json
├── .firebaserc
├── README.md
└── public/
├── index.html
├── register.html
├── login.html
├── home.html
├── product.html
├── cart.html
├── address.html
├── success.html
├── history.html
├── css/
│ ├── address.css
│ ├── cart.css
│ ├── history.css
│ ├── home.css
│ ├── login.css
│ ├── register.css
│ └── success.css
└── scripts/
├── address.js
├── auth.js
├── cart.js
├── firebase-config.js
├── home.js
└── product.js


---

## 🧰 Technologies Used

- 🌐 HTML5, CSS3, JavaScript (ES6)
- 🔥 Firebase Authentication – For user login/register
- 📄 Firebase Firestore – To store user orders and data
- 🌍 Firebase Hosting – For live deployment

---

## 🚀 How to Run This Project

### 🔧 1. Clone the Repo
```bash
git clone https://github.com/yaswanthaddula/Ecommerce.git
cd Ecommerce
🔐 2. Set Up Firebase
Go to Firebase Console

Create a new project

Enable:

Firebase Authentication (Email/Password)

Firestore Database

Add a new Web App

Copy Firebase config into public/scripts/firebase-config.js:

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "...",
  messagingSenderId: "...",
  appId: "..."
};
🔐 Firestore Rules
In Firestore > Rules, paste this and click Publish:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {

    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }

    match /cart/{docId} {
      allow read, write: if request.auth != null;
    }

    match /orders/{orderId} {
      allow create: if request.auth != null && request.resource.data.userId == request.auth.uid;
      allow read: if request.auth != null && request.auth.uid == resource.data.userId;
    }
  }
}

🧾 How to Create Firestore Database Collections (Optional)
📦 1. users Collection
No need to create manually. It is created automatically after registration ✅

🛒 2. cart Collection (optional for testing)
Create a collection called cart and add:

userId – string
productId – string
productName – string
price – number
quantity – number

📜 3. orders Collection
Auto-created after successful order. To test manually, add:

userId – string
items – array
totalPrice – number
timestamp – timestamp

📤 Deploy to Firebase (Optional)
npm install -g firebase-tools
firebase login
firebase init hosting
# Select "public" folder, choose SPA: yes
firebase deploy
Your app will go live at:
🔗 https://your-project-id.web.app

🧠 Features
🎨 Dark-themed responsive design
🔐 Secure register/login using Firebase Auth
🛒 Add to cart with real-time price update
📍 Address entry and mock payment
✅ Order success screen with summary
🕒 Booking history tied to logged-in user

🧠 What's Next?
💳 Real payment gateway (Razorpay/Stripe)
🧑‍💼 Admin dashboard to manage products
⭐ User product reviews and ratings
📩 Email confirmation on order
📦 QR code on success screen

👨‍💻 Developed By
Yaswanth Addula
🎓 B.Tech – AI & Data Science
🏫 Saveetha School of Engineering

📄 License
This project is licensed under the MIT License.

📬 Contact
📧 yaswanthofficial@gmail.com
🔗 GitHub: @yaswanthaddula
