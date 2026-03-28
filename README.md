<div align="center">
  <h1>🚖 Rydex - Real-Time Ride Sharing Platform</h1>
  <p>A production-ready, full-stack ride-sharing application designed for low-latency live map tracking, seamless dispatching, and secure payment processing.</p>

  <!-- Add some badges here later -->
  [![Next.js](https://img.shields.io/badge/Next.js-v15-black)](https://nextjs.org/)
  [![Node.js](https://img.shields.io/badge/Node.js-Backend-green)](https://nodejs.org/)
  [![Socket.io](https://img.shields.io/badge/Socket.io-Real--Time-blueviolet)](https://socket.io/)
  [![MongoDB](https://img.shields.io/badge/MongoDB-Database-success)](https://www.mongodb.com/)
</div>

<br />

Rydex is a robust ride-sharing infrastructure featuring a dynamic **Next.js** frontend and a dedicated **Express.js & Socket.io** backend. It enables riders to book vehicles, drivers (partners) to accept rides, and admins to oversee the entire platform—all in real time.

## ✨ Key Features

- **Real-Time Location Tracking:** Visualize active rides with interactive map integrations using Leaflet and low-latency driver coordinate updates via Socket.io.
- **Instant Dispatch System:** Bi-directional communication architecture enabling split-second ride requests, acceptances, and status updates.
- **In-App Communication (WebRTC):** Built-in audio and video calling features powered by the ZEGOCLOUD UI Kit.
- **Secure Payment Gateways:** Unified checkout experience supporting both Stripe and Razorpay integrations.
- **Complete User Roles:** Dedicated dashboards and onboarding flows for Riders, Partners (Drivers), and Administrators (including KYC video verification).
- **Secure Authentication:** Passwordless and password-based login flows managed securely via NextAuth.js (v5) and bcrypt.
- **Data Visualization:** Modern charts and metrics powered by Recharts for admin and partner earnings.

---

## 💻 Tech Stack

### Frontend (`/rydex`)
- **Framework:** [Next.js 15](https://nextjs.org) (App Router)
- **Styling:** [Tailwind CSS v4](https://tailwindcss.com/) & [Framer Motion](https://www.framer.com/motion/)
- **State Management:** [Redux Toolkit](https://redux-toolkit.js.org/)
- **Maps:** [Leaflet](https://leafletjs.com/) & React-Leaflet
- **Authentication:** [NextAuth.js](https://authjs.dev/)
- **Communication:** [ZEGOCLOUD](https://www.zegocloud.com/) UIKit
- **Payments:** Stripe & Razorpay (Client SDKs)

### Backend (`/socketServer`)
- **Runtime:** [Node.js](https://nodejs.org/)
- **Framework:** [Express.js](https://expressjs.com/)
- **Real-time Server:** [Socket.io](https://socket.io/)
- **Database ORM:** [Mongoose](https://mongoosejs.com/) (MongoDB)

---

## 🚀 Getting Started

Follow these steps to set up the project locally on your machine.

### Prerequisites
- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [MongoDB](https://www.mongodb.com/) (Local or Atlas cluster URL)

### 1. Clone the repository
```bash
git clone https://github.com/Surajgupta007/Rydex.git
cd Rydex
```

### 2. Backend Setup (Socket & Database Server)
Navigate to the backend directory and install dependencies:
```bash
cd socketServer
npm install
```

Create a `.env` file in the `socketServer` directory and add the following:
```env
PORT=8000
MONGODB_URI=your_mongodb_connection_string
# Add any other required backend variables
```

Start the backend server in development mode:
```bash
npm run dev
```

### 3. Frontend Setup (Next.js Application)
Open a new terminal window, navigate back to the root directory, and then into the frontend codebase:
```bash
cd rydex
npm install
```

Create a `.env.local` file in the `rydex` directory. You will need API keys for various services to get the application fully functional:
```env
# Standard Next.js Env
NEXT_PUBLIC_BASE_URL=http://localhost:3000

# Auth.js Configuration
AUTH_SECRET=generate_a_random_secret_key_here

# MongoDB Connection
DATABASE_URL=your_mongodb_connection_string

# ZEGOCLOUD Settings (For Video/Audio Calls)
NEXT_PUBLIC_ZEGO_APP_ID=your_zego_app_id
NEXT_PUBLIC_ZEGO_SERVER_SECRET=your_zego_server_secret

# Payment Gateways (Stripe & Razorpay)
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_pub_key
STRIPE_SECRET_KEY=your_stripe_secret_key

NEXT_PUBLIC_RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret

# Socket IO Backend URL
NEXT_PUBLIC_SOCKET_URL=http://localhost:8000
```

Start the Next.js development server:
```bash
npm run dev
```

### 4. Open the App
Once everything is running, open [http://localhost:3000](http://localhost:3000) in your browser. 
The background socket server will be running simultaneously on [http://localhost:8000](http://localhost:8000).

---

## 📁 Repository Structure
```text
Rydex/
├── rydex/                  # Frontend Next.js Codebase
│   ├── public/             # Static Assets
│   └── src/                
│       ├── app/            # Next.js App Router Pages & API Routes
│       ├── components/     # Reusable React UI Components
│       ├── lib/            # Utilities (db, mailer, socket, stripe configurations)
│       ├── models/         # Mongoose Schemas (Shared with Next.js API Routes)
│       └── redux/          # Global State Management
└── socketServer/           # Node.js/Express Backend Codebase
    ├── index.js            # Main HTTP & Socket.io server entry point
    └── models/             # Mongoose Schemas for socket-specific logic
```

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/Surajgupta007/Rydex/issues).

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License
This project is licensed under the MIT License.
