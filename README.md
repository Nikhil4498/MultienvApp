# Multi-Environment Application Deployment (Local Setup)

## 🖍 Overview
This project demonstrates deploying a **multi-environment ticket management application** locally using **Docker and Docker Compose**. The application consists of:
- **Frontend** (React)
- **Development Backend** (Flask, running on port `3001`)
- **Production Backend** (Flask, running on port `3002`)

## 📌 Prerequisites
Ensure you have the following installed on your local machine:
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Node.js](https://nodejs.org/en) (for running React frontend)
- [Python 3.x](https://www.python.org/downloads/) (for running Flask backend)

---

## 🏢 Project Structure
```
multiEnv/
├── docker-compose.yml
├── backend/
│   ├── dev/
│   │   ├── app.py
│   │   ├── requirements.txt
│   │   ├── Dockerfile
│   │   ├── .env
│   ├── prod/
│   │   ├── app.py
│   │   ├── requirements.txt
│   │   ├── Dockerfile
│   │   ├── .env
└── frontend/
    ├── src
    ├── public
    ├── Dockerfile
    └── package.json
```

---

## 🚀 Step-by-Step Setup & Deployment

### 1⃣ Clone the Repository
Open **VS Code** or a terminal and run:
```sh
git clone https://github.com/your-repo/multiEnv.git
cd multiEnv
```

### 2⃣ Backend Setup
#### 🔹 Development Backend (`backend/dev`)
1. Navigate to the **development backend** folder:
   ```sh
   cd backend/dev
   ```
2. Install Python dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Run the Flask application:
   ```sh
   python app.py
   ```
4. The **development backend** should now be running at:
   ```
   http://localhost:3001/
   ```

#### 🔹 Production Backend (`backend/prod`)
1. Navigate to the **production backend** folder:
   ```sh
   cd ../prod
   ```
2. Install Python dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Run the Flask application:
   ```sh
   python app.py
   ```
4. The **production backend** should now be running at:
   ```
   http://localhost:3002/
   ```

---

### 3⃣ Frontend Setup
1. Navigate to the **frontend** folder:
   ```sh
   cd ../../frontend
   ```
2. Install Node.js dependencies:
   ```sh
   npm install
   ```
3. Start the React frontend:
   ```sh
   npm start
   ```
4. The **frontend** should now be running at:
   ```
   http://localhost:3000/
   ```
5. Access different environments:
   - **Development:** `http://localhost:3000/dev`
   - **Production:** `http://localhost:3000/prod`

---

## 💪 Dockerizing the Application

Instead of running services manually, we can use **Docker Compose** to containerize everything.

### 4⃣ Build and Run with Docker Compose
1. Ensure you're in the project root directory (`multiEnv`):
   ```sh
   cd ..
   ```
2. Build and run all services:
   ```sh
   docker-compose up --build
   ```
3. The application should now be accessible at:
   ```
   Frontend:        http://localhost:3000/
   Dev Backend:     http://localhost:3001/
   Prod Backend:    http://localhost:3002/
   ```

### 5⃣ Stopping the Application
To stop all running containers:
```sh
docker-compose down

---

## 🎯 Success Criteria
✔ All services are running correctly  
✔ Frontend communicates with both backend environments  
✔ Application accessible at `http://localhost:3000/`  
✔ Proper documentation is provided  

---

## 📣 Conclusion
You have successfully deployed a **multi-environment Flask & React application** locally using **Docker and Docker Compose**! 🎉

