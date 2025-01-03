### **README.md**
# Zigment


---

# **User Notification API**

The **User Notification API** is a serverless application built with NestJS. It provides a robust system for managing user notification preferences and sending notifications via multiple channels (email, SMS, push). The API includes features like validation, rate limiting, error handling, and notification logs.

---

## **Features**

- **User Preferences**:
  - Create, retrieve, update, and delete user notification preferences.
  - Supports customization for channels (email, SMS, push), frequency, and time zones.

- **Notification Management**:
  - Send notifications based on user preferences.
  - Log notification delivery status (e.g., sent, failed).

- **Rate Limiting**:
  - Prevents abuse by limiting the number of requests per user.

- **Error Handling**:
  - Custom exception filters for consistent error responses.

- **Validation**:
  - Request validation using `class-validator` and `class-transformer`.

---

## **Tech Stack**

- **Framework**: NestJS
- **Database**: MongoDB (via Mongoose)
- **Deployment**: Vercel
- **Rate Limiting**: NestJS Throttler Module
- **Testing**: Jest, Supertest
- **Environment Variables**: `@nestjs/config`

---

## **Installation**

### **Prerequisites**

- Node.js (v16+ recommended)
- MongoDB instance
- Vercel CLI (optional for deployment)

### **Steps**

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd user-notification-api
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Set Environment Variables**:
   Create a `.env` file in the root directory and add the following:
   ```env
   MONGO_URL=mongodb://localhost:27017/user-notifications
   PORT=3000
   ```

4. **Start the Server**:
   ```bash
   npm run start
   ```
   The application will be available at `http://localhost:3000`.

5. **Run in Watch Mode (Optional)**:
   ```bash
   npm run start:dev
   ```

---

## **API Documentation**

Refer to the [API Documentation](#api-documentation) section for detailed information about the available endpoints.

---

## **Project Structure**

```
user-notification-api/
├── src/
│   ├── app.module.ts         # Root application module
│   ├── main.ts               # Application entry point
│   ├── preferences/          # User preferences module
│   ├── notifications/        # Notifications module
│   ├── common/               # Shared utilities, filters, interceptors
│   └── ...
├── test/                     # Unit and integration tests
├── .env                      # Environment variables
├── vercel.json               # Vercel configuration
├── package.json              # Project metadata and scripts
└── README.md                 # Project documentation
```

---

## **API Endpoints**

### **Base URL**

- **Local**: `http://localhost:3000`
- **Production**: `<Your-Vercel-Deployment-URL>`

### **1. User Preferences**

- **Create Preferences**: `POST /api/preferences`
- **Get Preferences**: `GET /api/preferences/:userId`
- **Update Preferences**: `PATCH /api/preferences/:userId`
- **Delete Preferences**: `DELETE /api/preferences/:userId`

### **2. Notifications**

- **Send Notification**: `POST /api/notifications/send`
- **Get Notification Logs**: `GET /api/notifications/:userId/logs`
- **Get Notification Statistics**: `GET /api/notifications/stats`

---

## **Testing**

### **Run Unit Tests**:
```bash
npm run test
```

### **Run E2E Tests**:
```bash
npm run test:e2e
```

### **Check Test Coverage**:
```bash
npm run test:cov
```

---

## **Deployment**

### **Deploy on Vercel**

1. **Install Vercel CLI**:
   ```bash
   npm install -g vercel
   ```

2. **Deploy**:
   ```bash
   vercel
   ```

3. **Set Environment Variables on Vercel**:
   - Navigate to **Settings > Environment Variables** in the Vercel dashboard.
   - Add variables (e.g., `MONGO_URL`).

---

## **Contributing**

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Make your changes and commit:
   ```bash
   git commit -m "Add your message"
   ```
4. Push to the branch:
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a pull request.

---


## **Contact**

For any questions or suggestions, contact the developer:

- **Name**: Nitesh Kumar
- **Email**: niteshsingh6206@gmail.com

---

This README provides comprehensive documentation for setting up, running, and deploying the **User Notification API**.
