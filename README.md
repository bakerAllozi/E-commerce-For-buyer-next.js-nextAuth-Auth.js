# [E-commerce Platform] - Prototype Version

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)  
[![Next.js](https://img.shields.io/badge/Next.js-v15-blue)](https://nextjs.org/)  
[![Tailwind CSS](https://img.shields.io/badge/TailwindCSS-v3.4-green)](https://tailwindcss.com/)  
[![Supabase](https://img.shields.io/badge/Supabase-Database%20%26%20Auth-brightgreen)](https://supabase.com/)

---

## 🌟 Introduction

This **E-commerce Platform** is a **prototype version** designed to provide a seamless shopping experience. Built with **Next.js**, it offers fast rendering, enhanced SEO, and advanced features, all aimed at creating an intuitive user experience.

This project is part of a multi-application platform that communicates with a **React-based customer application** to enable seamless real-time interactions and data synchronization between customers and vendors.

---

## 🚀 Key Features

### **Product Search & Filters**

- **Advanced Filtering System:**  
  Users can filter products by:
  - **Color**
  - **Size**
  - **Price Range**
- **Sharable Filters:** Filters can be shared via URL, making it easy to share specific product searches with others.

### **Product Showcase**

- Elegant product cards displaying:
  - **High-quality images**
  - **Pricing and available stock**
  - **Product descriptions**

### **User & Vendor Communication**

- **Real-Time Chat:**  
  Powered by **Supabase Realtime**, enabling **real-time communication** between the customer app and the vendor app. Customers can:
  - Ask questions about products.
  - Request offers.
  - Negotiate prices directly with vendors.  
    The system ensures instant updates on messages and interactions without the need for manual refresh.

### **Integration with React Customer App**

This platform is integrated with the customer-facing **React-based application**.  
The integration includes:

- **Supabase Realtime** for instant updates on chats, notifications, and product availability.
  Example flow:

1. **Customer App:** Sends a request to fetch available products or initiate a chat.
2. **Vendor App (Next.js):** Processes the request, updates the database, and sends a response in real time.

### **Access Control & SaaS Subscription**

- **SaaS Service:**  
  The platform is connected to a **Middleware** layer to optimize performance and manage revenue generation.  
  Features include:
  - **Subscription-based Access:** Ensuring only premium users have access to advanced tools and analytics.
  - **Performance Optimization:** By using caching and efficient route handling for better user experience.

---

## 🔒 Security Practices for Supabase and Next.js

Ensuring the security of the platform is a top priority. Below are the measures taken to safeguard data and interactions:

1. **Using `.env` to Hide Keys:**

   - All sensitive API keys and environment variables (e.g., `SUPABASE_URL` and `SUPABASE_KEY`) are stored in a `.env` file. This file is excluded from the repository using `.gitignore` to prevent accidental exposure.

2. **Row Level Security (RLS):**

   - RLS is enabled on all Supabase tables to ensure that users can only access data they own or are authorized to view. For example:
     - A user can only see their own orders or messages.
     - Unauthorized operations (e.g., accessing another user's data) are blocked.

3. **Authentication Enforcement:**

   - All API calls are protected by authentication checks to ensure only logged-in users can perform operations. Without valid authentication, requests are denied.

4. **Using "`use server`" Directive:**
   - To enhance security, critical operations (e.g., data updates, sensitive queries) are performed on the server-side using Next.js API routes. This ensures that sensitive operations are not exposed to the client and cannot be tampered with by end users.

---

## 🌟 Best Practices for Using SSR, CSR, ISR, and SSG

### **SSR (Server-Side Rendering)**

- **Advantages**:
  - Greatly enhances SEO by delivering fully rendered pages to search engines.
  - Provides up-to-date dynamic data on every request.
- **When to Use It?**
  - Pages requiring frequently updated data, like product details based on user queries or live sales pages.
- **Best Practices**:
  - Minimize database queries to ensure low response time.
  - Use caching techniques to speed up rendering for frequently requested data.

---

### **Distribution of Techniques in the Platform**

- **SSR**: For pages requiring dynamic user-specific data (e.g., product pages).
- **CSR**: For real-time user interaction (e.g., live chat or account management).
- **ISR**: For pages needing periodic updates (e.g., offers and discounts).
- **SSG**: For static pages that rarely change (e.g., Privacy Policy pages).

---

## 🛠️ Technologies Used

- **Next.js**: Framework for server-side rendering and static site generation.
- **Supabase**: Database and real-time communication solution.
- **NextAuth**: Authentication library for social login (Google).
- **Tailwind CSS**: For responsive and modern designs.
- **Framer Motion**: Adding smooth animations for better user experience.
- **Supabase Realtime**: For real-time database updates and interactions.
- **Middleware**: For SaaS feature handling and access control.

---

## 📂 Project Structure

```plaintext
src/
├── components/       # Reusable UI components
├── pages/            # Next.js page structure
├── styles/           # Tailwind CSS and global styling
├── middleware/       # Access control and route restrictions
├── services/         # Supabase API integrations
├── context/          # Global state management using Context API
├── utils/            # Helper functions
├── public/           # Static assets
└── app.tsx           # Application entry point
```

---

## 🌱 Upcoming Enhancements

- **Enhanced Vendor Features:** Advanced analytics and subscription-based premium features.
- **Product Reviews:** Customers can rate and review products, and sellers can respond to reviews.
- **Dynamic Promotions:** Implement discount codes and special deals for customers.
- **Mobile Optimization:** Full responsive design for a seamless mobile shopping experience.

---

## 🔗 Related Repositories

- **React Customer App Repository**:  
  The front-end application for customers is available [here](https://github.com/Baker-Allozi/react-customer-app).

---

## 📖 How to Run Both Applications Locally

1. Clone both repositories:

   - Vendor (Next.js):
     ```bash
     git clone https://github.com/Baker-Allozi/nextjs-vendor-app
     ```
   - Customer (React):
     ```bash
     git clone https://github.com/Baker-Allozi/react-customer-app
     ```

2. Install dependencies for both:

   - Vendor (Next.js):
     ```bash
     cd nextjs-vendor-app
     npm install
     npm run dev
     ```
   - Customer (React):
     ```bash
     cd react-customer-app
     npm install
     npm start
     ```

3. Ensure both applications are running:

   - Vendor app:  
     Accessible at `http://localhost:3000`.
   - Customer app:  
     Accessible at `http://localhost:3001`.

4. Communication:  
   Ensure the **React customer app** sends requests to `http://localhost:3000/api`.
