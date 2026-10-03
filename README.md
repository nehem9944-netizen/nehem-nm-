# nehem-nm-
naan mudhalvan project .. WHAT NEXT VISION MOTORS
# WhatNext Vision Motors 🚗

## Salesforce CRM – Vehicle Order Management System

WhatNext Vision Motors is a **Salesforce-based CRM solution** designed to modernize vehicle ordering and dealership operations.

The system automates vehicle order processing, validates stock availability, assigns orders to the nearest dealer, manages test-drive scheduling, updates order statuses, and provides reports and dashboards for operational monitoring.

The project aims to reduce manual work, prevent order errors, improve real-time visibility, and provide a better customer experience.

---

## 📌 Project Overview

Traditional vehicle ordering processes often rely on manual registers, spreadsheets, and disconnected systems. This can result in stock errors, delayed updates, incorrect orders, and inefficient communication between customers and dealers.

This project addresses these problems using **Salesforce CRM**, providing a centralized platform for:

* Vehicle management
* Dealer management
* Customer management
* Vehicle ordering
* Stock validation
* Automatic dealer assignment
* Test-drive scheduling
* Service request management
* Automated order processing
* Reports and dashboards

Salesforce was selected because of its automation capabilities, scalability, and real-time visibility.

---

## 🎯 Objectives

* Automate the vehicle ordering process
* Prevent orders for out-of-stock vehicles
* Automatically assign orders to the nearest dealer
* Maintain accurate vehicle inventory
* Automate order status updates
* Send test-drive reminder emails
* Provide real-time operational visibility
* Reduce manual intervention
* Improve customer satisfaction
* Support multiple dealerships and locations

---

## 🏗️ System Architecture

### Main Components

```text
Customer
   │
   ▼
Vehicle Selection
   │
   ▼
Order Creation
   │
   ▼
Stock Validation
   │
   ├── Out of Stock ──► Pending Order
   │
   └── Available
          │
          ▼
   Dealer Assignment
          │
          ▼
   Order Status Update
          │
          ▼
   Reports & Dashboards
```

The system consists of Salesforce objects, Lightning UI, Flows, Apex Triggers, Batch Apex, Scheduled Apex, Reports, and Dashboards.

---

## 🛠️ Technology Stack

| Layer                | Technology                      |
| -------------------- | ------------------------------- |
| UI                   | Salesforce Lightning            |
| Business Logic       | Salesforce Flows                |
| Database             | Salesforce Objects              |
| Automation           | Validation Rules, Apex Triggers |
| Batch Processing     | Batch Apex                      |
| Scheduled Processing | Scheduled Apex                  |
| Reporting            | Salesforce Reports & Dashboards |

---

## 🗄️ Salesforce Data Model

The project uses the following custom objects:

### 1. Vehicle

Stores vehicle information such as:

* Vehicle Name
* Vehicle Model
* Stock Quantity
* Price
* Dealer
* Availability Status

### 2. Vehicle Dealer

Stores dealership information:

* Dealer Name
* Dealer Location
* Dealer Code
* Phone
* Email

### 3. Vehicle Customer

Stores customer information:

* Customer Name
* Email
* Phone
* Address
* Preferred Vehicle Type

### 4. Vehicle Order

Tracks customer vehicle purchases:

* Customer
* Vehicle
* Order Date
* Order Status

### 5. Vehicle Test Drive

Manages test-drive bookings:

* Customer
* Vehicle
* Test Drive Date
* Status

### 6. Vehicle Service Request

Tracks vehicle service requirements:

* Customer
* Vehicle
* Service Date
* Issue Description
* Status

---

## ⚙️ Key Features

### 1. Stock Validation

Apex Trigger logic checks vehicle availability before an order is placed.

If the vehicle has zero stock, the order is prevented and the user receives an error.

```text
Vehicle Stock = 0
       │
       ▼
Order Attempt
       │
       ▼
Order Blocked
       │
       ▼
"This vehicle is out of stock.
Order cannot be placed."
```

---

### 2. Automatic Stock Update

When a confirmed order is placed, the vehicle's stock quantity is automatically reduced by one.

```text
Confirmed Order
      │
      ▼
Vehicle Stock
      │
      ▼
Stock - 1
```

---

### 3. Automatic Dealer Assignment

A **Record-Triggered Flow** automatically assigns a dealer based on the customer's location.

```text
New Vehicle Order
       │
       ▼
Get Customer Information
       │
       ▼
Find Nearest Dealer
       │
       ▼
Assign Dealer
```

The flow is triggered when a vehicle order is created with a `Pending` status.

---

### 4. Test Drive Reminder

A scheduled Salesforce Flow sends an email reminder to customers before their scheduled test drive.

The reminder is scheduled **one day before the test drive**.

Example:

```text
Test Drive Scheduled
        │
        ▼
Scheduled Path
        │
        ▼
1 Day Before
        │
        ▼
Reminder Email
```

---

### 5. Batch Order Processing

Pending vehicle orders can be processed automatically when new stock becomes available.

The Batch Apex job checks pending orders and confirms eligible orders when stock is available.

```text
Pending Order
      │
      ▼
Batch Apex
      │
      ▼
Check Vehicle Stock
      │
      ├── Stock Available
      │       ▼
      │    Confirm Order
      │
      └── No Stock
              ▼
          Remain Pending
```

---

### 6. Scheduled Apex

A Scheduled Apex class runs the vehicle order batch process automatically.

The project uses a scheduler to execute the batch job periodically.

---

## 📊 Reports & Dashboards

Salesforce Reports and Dashboards provide visibility into:

* Order status
* Dealer performance
* Sales metrics
* Operational activity

This allows managers to monitor vehicle ordering and dealership operations from a centralized platform.

---

## 🔄 Customer Journey

```text
Inquiry
   ↓
Vehicle Selection
   ↓
Order Placement
   ↓
Dealer Assignment
   ↓
Stock Validation
   ↓
Test Drive
   ↓
Confirmation
   ↓
Reporting
```

---

## 🔐 Non-Functional Requirements

| Requirement  | Implementation                    |
| ------------ | --------------------------------- |
| Usability    | Salesforce Lightning UI           |
| Security     | Role-based access control         |
| Reliability  | Automated and accurate processing |
| Performance  | Fast order processing             |
| Availability | 24/7 cloud access                 |
| Scalability  | Multi-dealer support              |

---

## 📅 Development Methodology

The project follows an **Agile development methodology**.

Development is organized using:

* Epics
* User Stories
* Story Points
* Sprint-based execution
* Velocity estimation

The project plan divides implementation into multiple sprints covering Salesforce setup, data modeling, automation, Apex development, reports, and dashboards.

---

## 🧪 Testing

The project was tested using Salesforce to validate:

* Vehicle creation
* Dealer assignment
* Stock validation
* Order status updates
* Batch processing
* Scheduled reminders
* Dashboard analytics

The documented testing verified the implemented features and their intended functionality.

---

## ✅ Advantages

* Centralized data management
* Automated workflows
* Real-time reporting
* Reduced manual intervention
* Improved order accuracy
* Better inventory management
* Improved customer experience

## ⚠️ Limitations

* Dependency on Salesforce
* Initial configuration effort is required

---

## 🚀 Future Scope

The project can be further enhanced with:

* 📱 Mobile vehicle ordering application
* 📍 Dealer GPS integration
* 📩 SMS notifications
* 🤖 AI-based vehicle demand forecasting

---

## 📂 Project Components

```text
WhatNext Vision Motors
│
├── Salesforce Objects
│   ├── Vehicle
│   ├── Dealer
│   ├── Customer
│   ├── Order
│   ├── Test Drive
│   └── Service Request
│
├── Salesforce Flows
│   ├── Auto Assign Dealer
│   └── Test Drive Reminder
│
├── Apex
│   ├── VehicleOrderTriggerHandler
│   ├── VehicleOrderTrigger
│   ├── VehicleOrderBatch
│   └── VehicleOrderBatchScheduler
│
├── Reports
│
└── Dashboards
```

---

## 💻 Apex Components

### Trigger Handler

`VehicleOrderTriggerHandler`

Responsible for:

* Preventing orders when stock is unavailable
* Updating vehicle stock after confirmed orders

### Trigger

`VehicleOrderTrigger`

Handles:

```text
Before Insert
Before Update
After Insert
After Update
```

and invokes the trigger handler.

### Batch Class

`VehicleOrderBatch`

Processes pending orders and confirms orders when inventory becomes available.

### Scheduler

`VehicleOrderBatchScheduler`

Executes the batch process through Salesforce Scheduled Apex.

---

## 📖 Learning Outcomes

Through this project, the following Salesforce concepts are covered:

1. Data Modeling
2. Fields and Relationships
3. Lightning App Builder
4. Record-Triggered Flows
5. Apex
6. Apex Triggers
7. Batch Apex
8. Scheduled Apex

---

## 🎓 Project Purpose

This project demonstrates how Salesforce CRM can be used to build an automated vehicle order management system that connects customers, vehicles, dealers, inventory, test drives, and service requests within a centralized platform.

It combines **Salesforce configuration, Flow automation, Apex development, batch processing, scheduled automation, and reporting** to address real-world dealership operations.

---

## 📌 Project Status

**Status:** Completed / Demonstration Project

**Platform:** Salesforce CRM

**Domain:** Automotive / Customer Relationship Management

**Primary Focus:** Vehicle Order & Dealership Management

---

## 👨‍💻 Author

**WhatNext Vision Motors – Salesforce CRM Project**

> Built as a Salesforce CRM implementation project demonstrating automated vehicle ordering and dealership management.

---

## 📄 Reference

Project documentation: *WhatNext Vision Motors: Shaping the Future of Mobility with Innovation and Excellence*
