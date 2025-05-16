# DAWN - Dark Tourism with AI Navigation

[![Demo Video](https://img.shields.io/badge/-Demo%20Video-red)](https://youtu.be/xGadBd0Dcfg)
&nbsp;
[![App Prototype Guide](https://img.shields.io/badge/-App%20Prototype%20Guide-blue)](https://github.com/DAWN-2025/dawn_frontend/wiki/App-Prototype-Guide)
&nbsp;
[![dawn_backend Repository](https://img.shields.io/badge/-dawn_backend-green?logo=github)](https://github.com/DAWN-2025/dawn_backend)
&nbsp;
[![dawn_frontend Repository (Flutter)](https://img.shields.io/badge/-dawn_frontend%20(Flutter)-blue?logo=github)](https://github.com/DAWN-2025/dawn_frontend)


> *"Those who do not remember the past are condemned to repeat it."*
> — George Santayana

---

> ⚠️ **Note on Repository Visibility & Sensitive File Removal**

We are currently in contact with the GitHub team regarding the removal of a mistakenly committed `.json` file that was included in a previous pull request.  
The file does not contain any critical credentials, but it was not intended for publication and we have requested its removal from the repository's commit history.

We plan to make this repository **public** in the near future once the cleanup process is complete.  
Thank you for your understanding and patience!

---

# 🌌 Overview

DAWN is an immersive AI-powered dark tourism platform that allows users to explore and emotionally engage with historically significant yet tragic events.
Users interact with AI-generated personas, experience site-based reconstructions, and collect digital memorials.

![DawnBanner](https://github.com/user-attachments/assets/c773b390-d515-4de9-a8e4-15003cc0d605)

---

# 📂 Table of Contents

* Solution Challenge Theme
* Architecture
* Core Concept
* Tech Stack
* How to Run
* Team

---
# Solution Challenge Theme

<table>
  <tr>
    <th>Tourism</th>
  </tr>
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/60b7b0f5-8a4f-4d23-a65b-7461e594eeb8" width="500"/>
    </td>
  </tr>
</table>

---
# 🏗️ Architecture

The DAWN platform is designed to provide an immersive dark tourism experience powered by AI, integrating various services using modern cloud-native technologies. Below is a breakdown of the architecture:


<p align="center">
  <img src="https://github.com/user-attachments/assets/fb8adc92-edd6-46c6-9217-563363e21ad4" width="700"/>
</p>

* `Spring Boot` Web Server with `JWT + Redis` authentication
* `FastAPI` RAG backend for AI persona response generation
* `MySQL (Cloud SQL)` as primary DB
* `GCP Storage` for image, letter, and event assets
* `LangChain + Vertex AI + Pinecone` for RAG pipeline
* `Flutter` mobile app client
* `Docker` deployment on GCP VM (Compute Engine)





### 🧭 Client Layer
- **Flutter**: Cross-platform mobile application framework.
- **Google Maps API**: Enables location-based features.
- **Google Design**: Ensures UI/UX consistency across devices.

The client communicates with the backend using RESTful APIs and receives both structured content and AI-generated responses.


### 🔐 Firebase Platform
- **Firebase Authentication**: Handles secure user login and identity verification.
- **Cloud Storage for Firebase**: Stores user-uploaded content such as images or letters.

Firebase communicates directly with both the client and server for authentication and media access.


### ⚙️ Server Layer (GCP Compute Engine)
- **Spring Boot**: Java-based backend that manages user data, historical content, and API endpoints.
- **FastAPI**: Python-based service for handling AI interactions.
- **Docker**: Containerization of backend services for portability and scalability.


### 🧠 AI Integration
- **LangChain**: Orchestrates communication with the AI model.
- **Vertex AI + Gemini**: Google’s powerful LLM platform for generating historical personas and contextual responses.


### 🗄️ Database
- **Cloud SQL (MySQL)**: Stores all persistent data including users, locations, events, and AI-generated content.


### 🔁 Communication Flow

- The **Flutter client** sends user requests to the **Spring Boot** backend.
- If AI content is needed, Spring Boot relays the request to **FastAPI**, which processes it via **LangChain** & **RAG** and **Vertex AI (Gemini)**.
- **Firebase Authentication** verifies users, and **Cloud Storage** manages uploaded files.
- **Cloud SQL** stores and retrieves all application data.


___

# ✨ Core Concept

* AI-generated persona interactions based on historical events
* Guestbook and memory sharing for visited locations
* Digital stamp collection to track historical journeys
* Firebase-based authentication and user data management
* Support for multi-language and immersive content rendering

---

# 🔧 Tech Stack

| Layer    | Tech Choices                             |
| -------- | ---------------------------------------- |
| Backend  | Java Spring Boot, MySQL                 |
| AI Model | Python, FastAPI, LangChain, VertexAI     |
| Frontend | Flutter (Dart), Google Maps API        |
| Storage  | GCP Cloud SQL, Firebase storage         |
| Auth     | Firebase Authentication                  |
| Deploy   | Docker, GCP VM                           |
| ML Infra | Pinecon                                 |

---

# 🛫 How to Run

### Backend Server

```bash
# 1. Build backend
./gradlew build

# 2. Build and run Docker containers
sudo docker compose up --build
```

### Mobile App (Flutter)
```
# 1. Install dependencies
flutter pub get

# 2. Run the app on the desired platform (make sure a device/emulator is connected)
flutter run -d <device>
```


---

# 🌑 TEAM DAWN

We are a four-member team from GDG on Campus CNU, combining strengths across frontend, backend, AI, and UI design.


<table>
  <tr>
    <th>Frontend, Team Leader</th>
    <th>Frontend, UI Design</th>
    <th>Backend, AI</th>
    <th>Backend, AI</th>
  </tr>
  <tr>
    <td><img src="https://avatars.githubusercontent.com/u/169421565?v=4" width="150"/></td>
    <td><img src="https://avatars.githubusercontent.com/u/163499519?v=4" width="150"/></td>
    <td><img src="https://avatars.githubusercontent.com/u/138632648?v=4" width="150"/></td>
    <td><img src="https://avatars.githubusercontent.com/u/96593737?v=4" width="150"/></td>
  </tr>
  <tr>
    <td><a href="https://github.com/yb0x00" target="_blank">@yb0x00</a></td>
    <td><a href="https://github.com/202780" target="_blank">@LBB</a></td>
    <td><a href="https://github.com/ji-mim" target="_blank">@ji-mim</a></td>
    <td><a href="https://github.com/KwanjoonPark" target="_blank">@KwanjoonParkm</a></td>
  </tr>
</table>
