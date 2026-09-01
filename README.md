<div align="center">

# 🏦 Commonwealth Bank Software Engineering Job Simulation

### Full-Stack Feature Implementation — Goal Tracker Icon Support

[![Forage](https://img.shields.io/badge/Forage-Virtual%20Experience-6C2EB9?style=for-the-badge)](https://www.theforage.com/)
[![Commonwealth Bank](https://img.shields.io/badge/Commonwealth%20Bank-Simulation-FFCC00?style=for-the-badge&logo=commonwealthbank&logoColor=black)](https://www.commbank.com.au/)
[![Status](https://img.shields.io/badge/Status-Completed-2EA043?style=for-the-badge)](#)

![.NET](https://img.shields.io/badge/.NET%206.0-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=csharp&logoColor=white)
![React](https://img.shields.io/badge/React%2017-61DAFB?style=flat-square&logo=react&logoColor=black)
![Redux](https://img.shields.io/badge/Redux-764ABC?style=flat-square&logo=redux&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Material UI](https://img.shields.io/badge/Material--UI-0081CB?style=flat-square&logo=mui&logoColor=white)
![xUnit](https://img.shields.io/badge/xUnit-6C2EB9?style=flat-square)

</div>

---

## 🎯 Project Overview

This repository contains my completed work for the **Commonwealth Bank Software Engineering Virtual Experience** on Forage.

The task: add **icon support** to the Goal Tracker application — a full-stack feature spanning the .NET backend, the React/Redux frontend, API integration, and automated testing.

> A small feature on the surface, but one that touches every layer of the stack — a good showcase of end-to-end engineering discipline.

---

## 🧭 Tech Stack

| Layer | Technologies |
|---|---|
| 🖥️ **Backend** | .NET 6.0 · C# · MongoDB · xUnit |
| 🎨 **Frontend** | React 17 · Redux · TypeScript · Material-UI |
| 🔧 **Tooling** | Git · GitHub · Postman |

---

## 📋 Tasks Completed

### 1️⃣ Modify .NET Backend
**Objective:** Extend the `Goal` model to support an optional icon field.

- ✅ Added an `Icon` property (`string`, optional) to the Goal model
- ✅ Fully compatible with the existing MongoDB schema
- ✅ Maintains backward compatibility with existing goal records

📄 `Task-1-Backend/Goal.cs`

---

### 2️⃣ Modify React/Redux Frontend
**Objective:** Build the UI for icon selection and display.

- ✅ Extended the Goal TypeScript interface with an optional icon field
- ✅ Integrated an emoji picker component for icon selection
- ✅ Added icon display on goal cards
- ✅ Connected icon selection to Redux state management

📄 `Task-2-Frontend/types.ts` — TypeScript interface  
📄 `Task-2-Frontend/GoalManager.tsx` — Emoji picker implementation  
📄 `Task-2-Frontend/GoalCard.tsx` — Icon display component

---

### 3️⃣ Wire Backend and Frontend
**Objective:** Connect icon selection to the backend API for persistence.

- ✅ Icon changes trigger `PUT` requests to the backend
- ✅ Redux state updates persist to the database
- ✅ Real-time synchronization between UI and backend

**Status:** Integrated into Task 2 files (`GoalManager.tsx`)

---

### 4️⃣ Unit Testing
**Objective:** Write comprehensive unit tests for the `GetGoalsForUser` route.

- ✅ Built with the xUnit test framework
- ✅ Uses a fake service pattern for mocking
- ✅ Covers success scenarios and data validation
- ✅ Follows repository testing conventions

📄 `Task-4-Testing/GoalControllerTests.cs`

---

### 5️⃣ Version Control & Pull Requests
**Objective:** Create a feature branch, commit changes, and submit PRs.

- ✅ Created a `feature/goal-icons` branch in both repositories
- ✅ Committed all changes with descriptive messages
- ✅ Opened Pull Requests on GitHub
- ✅ Documented changes for team review

📄 `Task-5-Documentation/`

---

## 🚀 Features Implemented

| | Feature | Layer |
|---|---|---|
| ✅ | Optional icon field on Goal model | Backend |
| ✅ | Emoji picker for goal icon selection | Frontend |
| ✅ | Icon display on goal cards | Frontend |
| ✅ | Persistent icon storage via API | Integration |
| ✅ | Unit test coverage for `GetGoalsForUser` | Testing |
| ✅ | Git workflow and Pull Requests | Version Control |

---

## 📁 Repository Structure

```text
CommonWealth-Bank-Simulation/
├── README.md                          # This file
├── Task-1-Backend/
│   └── Goal.cs                        # Extended Goal model
├── Task-2-Frontend/
│   ├── types.ts                       # TypeScript interfaces
│   ├── GoalManager.tsx                # Emoji picker implementation
│   └── GoalCard.tsx                   # Icon display component
├── Task-3-Integration/
│   ├── README.md                      
├── Task-4-Testing/
│   └── GoalControllerTests.cs         # Unit tests
└── Task-5-Documentation/
    ├── SETUP.md                       # Project setup guide
    └── WORKFLOW.md                    # Git workflow documentation
```

---

## 🛠️ Setup & Installation

<details>
<summary><b>🔹 Backend (.NET)</b></summary>

```bash
cd commbank-server
dotnet restore
dotnet build
dotnet run
```
</details>

<details>
<summary><b>🔹 Frontend (React)</b></summary>

```bash
cd commbank-web
npm install
npm start
```
</details>

<details>
<summary><b>🔹 Testing</b></summary>

```bash
cd commbank-server/CommBank.Tests
dotnet test
```
</details>

---

## 🧪 Testing

All tests follow the repository's existing patterns:

- 🧩 xUnit testing framework
- 🧩 Fake service pattern for dependency injection
- 🧩 Arrange / Act / Assert structure
- 🧩 Comprehensive coverage of success and edge cases

**Run tests:**
```bash
dotnet test CommBank.Tests/CommBank.Tests.csproj
```

---

## 📝 Key Learnings

| # | Skill | Description |
|---|---|---|
| 1 | 🔗 **Full-stack development** | Coordinating backend and frontend changes |
| 2 | 🗂️ **State management** | Redux patterns for React applications |
| 3 | 🌐 **API integration** | Connecting UI actions to backend persistence |
| 4 | 🧪 **Unit testing** | Writing meaningful tests with mocking patterns |
| 5 | 🌳 **Version control** | Git branching, commits, and Pull Requests |

---

## 👤 Author

<div align="center">

**Shah Mubarak Zaib**

[![GitHub](https://img.shields.io/badge/GitHub-@zaibutman-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/zaibutman)

Commonwealth Bank Software Engineering Virtual Experience — Forage · September 2026

</div>

---

## 📄 License

This project was completed as part of the **Commonwealth Bank Virtual Experience** program on Forage.

---

## 🔗 Links

- 🏦 [Commonwealth Bank](https://www.commbank.com.au/)
- 🌱 [Forage Virtual Experience](https://www.theforage.com/)
- 💻 [My GitHub Profile](https://github.com/zaibutman)

<div align="center">

⭐ **If this helped you understand the simulation, consider starring the repo!**

</div>
