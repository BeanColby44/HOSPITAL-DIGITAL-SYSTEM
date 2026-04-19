# 🏥 Hospital Digital Decision Support System (HDSS)

**A healthcare management and clinical decision-support system designed to improve hospital operations, patient care, and communication.**

## 🛠️ Technologies & Skills

### Core Technologies

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![OOP](https://img.shields.io/badge/OOP-4B5563?style=for-the-badge)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Maven](https://img.shields.io/badge/Apache_Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)
![UML](https://img.shields.io/badge/UML-2563EB?style=for-the-badge)
![Agile](https://img.shields.io/badge/Agile-0F766E?style=for-the-badge)
![Kanban](https://img.shields.io/badge/Kanban-0052CC?style=for-the-badge&logo=trello&logoColor=white)

### Planned Web Application Stack

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
![Render](https://img.shields.io/badge/Render-000000?style=for-the-badge&logo=render&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?style=for-the-badge&logo=railway&logoColor=white)

> **Development status:** The Java repository layer and system design are documented in this project. The React, Node.js, PostgreSQL, authentication, and hosting technologies are part of the planned web application architecture.

---

## 📌 Project Overview

The **Hospital Digital Decision Support System (HDSS)** is a healthcare software project focused on digitizing hospital workflows and improving access to patient information.

The system is designed to support healthcare professionals in managing patient records, appointments, medication schedules, clinical workflows, and hospital resources.

The project covers software architecture, requirements engineering, UML modeling, Agile planning, and Java-based repository development.

## 🎯 Problem Statement

Many healthcare facilities, especially smaller and rural hospitals, experience challenges such as:

- Paper-based patient records that are difficult to maintain.
- Long waiting times caused by manual scheduling.
- Limited access to patient medical history.
- Inefficient communication between hospital staff and patients.
- Difficulty tracking medications and follow-up appointments.
- Limited visibility into hospital resources.

HDSS aims to address these challenges through centralized information management and structured digital workflows.

## ✨ Key Features & System Design

### 📂 Digital Patient Records

Designed to manage:

- Patient profiles and medical histories
- Diagnoses and prescriptions
- Laboratory test results
- Treatment records
- Patient information updates

### 🧠 Clinical Decision Support

Designed to help healthcare professionals review patient histories, access relevant alerts, and use available information when making clinical decisions.

The system is intended to assist healthcare professionals, not replace their clinical judgment.

### 📅 Appointment Management

Includes workflows for:

- Appointment booking and rescheduling
- Doctor availability
- Appointment status tracking
- Cancellations and missed appointments

### 🔔 Notifications & Reminders

The system design includes:

- Appointment reminders
- Medication schedule notifications
- Follow-up visit reminders
- Notification delivery tracking

### 👨‍⚕️ Hospital Staff Dashboard

Designed to provide access to:

- Patient information
- Appointment schedules
- Treatment progress
- Hospital resources
- Administrative workflows

## 🏗️ System Architecture

The architecture separates the system into layers to improve maintainability and extensibility.

### Application Layer

Handles user interactions, hospital workflows, and application operations.

### Business Logic Layer

Manages the rules for patient, doctor, appointment, and hospital resource workflows.

### Repository Layer

Separates data access from application logic using the Repository Pattern.

### Storage Layer

The documented Java implementation uses in-memory HashMap repositories. Persistent database integration is a future extension.

## 💾 Repository Pattern Implementation

The project uses a generic repository interface:

```java
Repository<T, ID>
```

It defines common data operations:

- `save()`
- `findById()`
- `findAll()`
- `delete()`

Entity-specific repository interfaces include:

- `PatientRepository`
- `DoctorRepository`
- `AppointmentRepository`

This approach reduces duplicated persistence logic and makes the code easier to maintain.

### In-Memory Repository Implementation

The repository layer uses Java HashMap collections.

Example:

```java
private Map<String, Patient> storage = new HashMap<>();
```

Implemented repository classes described in the project include:

- `InMemoryPatientRepository`
- `InMemoryDoctorRepository`
- `InMemoryAppointmentRepository`

These repositories support lightweight development and testing.

**Note:** In-memory storage is temporary and does not preserve data across application restarts.

## 🏭 Factory Pattern Implementation

The project uses a factory to select repository implementations.

Example:

```java
RepositoryFactory.getPatientRepository("MEMORY");
```

Benefits include:

- Reduced coupling
- Centralized repository creation
- Easier testing
- Improved maintainability
- Support for future storage implementations

## 🔄 UML System Modeling

The project includes state diagrams and activity diagrams to document hospital workflows.

### State Diagrams

| Entity | Example Lifecycle |
|---|---|
| Appointment | Requested → Confirmed → Completed / Cancelled |
| Patient Record | Created → Active → Archived |
| Doctor Availability | Available → Busy → On Leave |
| Bed Allocation | Free → Reserved → Occupied → Cleaning |
| Medication Schedule | Scheduled → Due → Administered / Missed |
| Lab Test | Requested → In Progress → Completed → Reviewed |
| Notification | Queued → Sending → Delivered / Failed |

### Activity Diagrams

The documented workflows include:

1. Patient registration
2. Appointment booking
3. Patient admission
4. Doctor consultation
5. Medication administration
6. Laboratory test processing
7. Patient discharge
8. Emergency handling

These diagrams help identify dependencies, edge cases, and responsibilities before implementation.

## 📋 Agile Project Management

The project documents a Kanban workflow for organizing development tasks.

| Status | Description |
|---|---|
| Backlog | Tasks awaiting prioritization |
| Ready | Tasks prepared for development |
| In Progress | Active development tasks |
| Blocked | Tasks waiting on dependencies |
| Testing | Features undergoing validation |
| Done | Completed and verified tasks |

### Work-in-Progress Limits

| Column | Limit |
|---|---|
| In Progress | 3 |
| Testing | 3 |
| Blocked | 3 |

### Task Labels

- `must-have`
- `should-have`
- `could-have`
- `bug`
- `feature`

The project documentation connects requirements, use cases, user stories, and system behavior.

## 🧪 Testing

The repository layer includes manual unit-test examples for:

- `InMemoryPatientRepository`
- `InMemoryDoctorRepository`
- `InMemoryAppointmentRepository`

Test scenarios cover:

- Creating objects
- Saving entities
- Finding records by ID
- Listing records
- Deleting records

Additional automated tests would be needed before production deployment.

## 📁 Project Structure

The documented Java repository components are organized as follows:

```text
repositories/
├── Repository.java
├── PatientRepository.java
├── DoctorRepository.java
├── AppointmentRepository.java
├── inmemory/
│   ├── InMemoryPatientRepository.java
│   ├── InMemoryDoctorRepository.java
│   └── InMemoryAppointmentRepository.java
└── database/
    └── DatabasePatientRepository.java

factories/
└── RepositoryFactory.java

tests/
├── InMemoryPatientRepositoryTest.java
├── InMemoryDoctorRepositoryTest.java
└── InMemoryAppointmentRepositoryTest.java
```

The `DatabasePatientRepository` component is described as a stub for future database integration.

## 🚀 Getting Started

### Prerequisites

- Java 17
- Apache Maven
- Git

### 1. Clone the Repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd rural-hospital-digital-system
```

Replace the placeholder with your actual repository URL.

### 2. Build the Project

If the repository includes a configured Maven project:

```bash
mvn clean install
```

### 3. Run the Application

If a Spring Boot entry point is configured:

```bash
mvn spring-boot:run
```

The provided documentation does not establish that a complete Spring Boot application is available. Confirm the project's build configuration before running this command.

## 🔒 Security & Privacy Considerations

A production healthcare platform should include:

- Role-based access control
- Secure authentication
- Encryption in transit and at rest
- Protection of sensitive patient information
- Audit logging
- Input validation
- Secure API integrations
- Backup and recovery procedures
- Appropriate healthcare privacy and compliance controls

These are production requirements, not claims that the current prototype has implemented or passed compliance validation.

## 🔮 Future Improvements

- PostgreSQL database integration
- React-based frontend
- Node.js and Express REST APIs
- JWT authentication
- Patient search
- SMS and email notifications
- Analytics dashboards
- Mobile application support
- Telemedicine integrations
- Automated testing and CI/CD
- Production security and access controls

## 📚 Documentation

The project documentation includes:

- System specifications
- Software architecture
- Stakeholder analysis
- Requirements engineering
- Use case diagrams
- State and activity diagrams
- Agile planning
- Kanban workflow design
- Repository architecture
- Persistence design
- Test scenarios

## 👨‍💻 Contact

**Colby Bean**

Full-Stack Software Engineer

- **Location:** Winter Park, Florida, USA
- **Email:** [colbybean321@gmail.com](mailto:colbybean321@gmail.com)
- **Phone:** +1 (689) 260-2573
- **GitHub:** [github.com/BeanColby44](https://github.com/BeanColby44)
- **LinkedIn:** [linkedin.com/in/colby-bean-922179449](https://www.linkedin.com/in/colby-bean-922179449/)

## 📄 License

Refer to the repository's existing `LICENSE` file for applicable terms, copyright notices, and attribution requirements.