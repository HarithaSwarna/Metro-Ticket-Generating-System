# 🚇 Metro Ticket Generating System

## 📌 Project Overview

The **Metro Ticket Generating System** is a ServiceNow-based application developed to automate the metro ticket booking and generation process.

The system allows passengers to enter their journey details, select the type of journey, specify the number of passengers, calculate the applicable fare, select a payment mode, and generate a digital metro ticket with a **QR code**.

The project demonstrates the use of **ServiceNow Service Catalog, Catalog Variables, Client Scripts, UI Policies, Flow Designer, Service Portal, and Service Portal Widgets** to build an automated ticketing solution.



## 🎯 Objectives

* Automate the metro ticket booking process.
* Provide a simple and user-friendly ticket booking form.
* Capture passenger journey details.
* Support both single and return journeys.
* Calculate the ticket fare based on the selected journey details.
* Support multiple passengers.
* Capture payment information.
* Generate a unique metro ticket number.
* Generate a digital QR code for the ticket.
* Display the generated ticket through the ServiceNow Service Portal.
* Reduce manual ticket processing and improve the overall user experience.
  
## ✨ Features

### 🎫 1. Metro Ticket Booking

Passengers can book metro tickets by submitting their journey details through a ServiceNow Catalog Item.

### 📍 2. Journey Details

The system captures:

* Starting Station
* Destination Station
* Type of Journey
* Number of Passengers

### 🔄 3. Journey Type

The system supports:

* **Single Journey**
* **Return Journey**

When **Return Journey** is selected, the **Amount Including Return** field is displayed.

### 💰 4. Fare Calculation

The system calculates the applicable fare based on the configured journey and passenger details.

### 💳 5. Payment Mode

Passengers can select their preferred payment method.

Examples:

* UPI
* Card
* Cash

### 🎟️ 6. Ticket Number

A unique ticket number is generated for every metro ticket request.

Example:

 text
MT10001
MT10002
MT10003


### 📱 7. QR Code

A QR code is generated for the digital metro ticket.

The QR code can contain information such as:

* Ticket Number
* Starting Station
* Destination
* Journey Type
* Number of Passengers
* Fare

### 🌐 8. Service Portal

The generated metro ticket is displayed through the ServiceNow Service Portal using a custom widget.



# 🛠️ Technologies Used

| Technology            | Usage                                 |
| --------------------- | ------------------------------------- |
| ServiceNow            | Application development platform      |
| ServiceNow Studio     | Application development               |
| Service Catalog       | Metro ticket booking                  |
| Catalog Variables     | Collect passenger and journey details |
| Client Scripts        | Form logic and dynamic behavior       |
| UI Policies           | Show/hide fields                      |
| Flow Designer         | Workflow automation                   |
| Service Portal        | Digital ticket display                |
| Service Portal Widget | QR code and ticket display            |
| JavaScript            | Business and client-side logic        |
| QR Code API           | QR code generation                    |



# 🏗️ System Architecture

  text
                    ┌──────────────────────┐
                    │       Passenger      │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Service Portal    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Service Catalog    │
                    │   Metro Ticket Form  │
                    └──────────┬───────────┘
                               │
                 ┌─────────────┼─────────────┐
                 │             │             │
                 ▼             ▼             ▼
          Journey Details  Fare Logic   Payment Mode
                 │             │             │
                 └─────────────┼─────────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Ticket Generation  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   QR Code Generation │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Digital Metro      │
                    │        Ticket        │
                    └──────────────────────┘

# 📋 Service Catalog Item

The main Catalog Item created for the project is:

**Metro Ticket Generating System**

## Catalog Variables

| Variable Label          | Variable Name               | Description                    |
| ----------------------- | --------------------------- | ------------------------------ |
| Ticket Number           | `ticket_number`             | Unique metro ticket number     |
| Starting From           | `starting_from`             | Starting metro station         |
| Going To                | `going_to`                  | Destination metro station      |
| Type of Journey         | `type_of_journey`           | Single or Return Journey       |
| Number of Passengers    | `number_of_passengers`      | Number of passengers           |
| Amount                  | `amount_for_single_journey` | Fare for single journey        |
| Amount Including Return | `amount_including_return`   | Fare for return journey        |
| Mode of Payment         | `mode_of_payment`           | Selected payment method        |
| Enter Payment Mode      | `enter_payment_mode`        | Additional payment information |

---

# 🔄 Application Workflow

The complete workflow of the system is:

   text
1. Passenger opens Service Portal
             ↓
2. Selects Metro Ticket Generating System
             ↓
3. Enters starting station
             ↓
4. Enters destination station
             ↓
5. Selects journey type
             ↓
6. Enters number of passengers
             ↓
7. System calculates applicable fare
             ↓
8. Passenger selects payment mode
             ↓
9. Passenger submits the request
             ↓
10. Ticket number is generated
             ↓
11. Ticket information is processed
             ↓
12. QR code is generated
             ↓
13. Digital metro ticket is displayed


# 🔢 Fare Calculation

The system handles fare information according to the selected journey type.

### Single Journey

   text
Journey Type = Single Journey

        ↓

Single Journey Amount
        ↓
Displayed


The **Amount Including Return** field remains hidden.

### Return Journey

   text
Journey Type = Return Journey

        ↓

Return Fare
        ↓
Amount Including Return
        ↓
Displayed


The return fare field is dynamically displayed when the user selects **Return Journey**.



# 🧩 ServiceNow Components

## 1. Service Catalog

A Catalog Item is created to allow passengers to request metro tickets.

## 2. Catalog Variables

Variables are used to collect journey, passenger, fare, and payment information.

## 3. Client Scripts

Client-side logic is used to control dynamic form behavior and perform required calculations or validations.

## 4. UI Policies

UI Policies are used to dynamically show or hide fields.

For example:

  text
If Type of Journey = Return Journey
        ↓
Show Amount Including Return
```

  text
If Type of Journey = Single Journey
        ↓
Hide Amount Including Return

## 5. Flow Designer

Flow Designer can be used to automate the ticket processing workflow after the user submits the request.

## 6. Service Portal

Service Portal provides the user-facing interface for booking and viewing the metro ticket.

## 7. Service Portal Widget

A custom widget is used to display the digital ticket and QR code.


# 📱 QR Code Generation

The system generates a QR code for the metro ticket.

The QR code can contain the ticket information:

text
Ticket Number: MT10001
Starting From: Ameerpet
Going To: Hitech City
Journey Type: Return Journey
Passengers: 2
Amount: ₹80


The passenger can scan the QR code using a smartphone to access the encoded ticket information.


# 🎟️ Sample Digital Ticket

     text
╔══════════════════════════════════╗
║          🚇 METRO TICKET         ║
╠══════════════════════════════════╣
║                                  ║
║ Ticket Number : MT10001          ║
║                                  ║
║ From          : Ameerpet         ║
║ To            : Hitech City      ║
║                                  ║
║ Journey       : Return Journey   ║
║ Passengers    : 2                ║
║                                  ║
║ Amount        : ₹80              ║
║ Payment       : UPI              ║
║                                  ║
║          [ QR CODE ]             ║
║                                  ║
╚══════════════════════════════════╝


# 🧪 Testing

The following test cases can be used to verify the application.

| Test Case             | Expected Result                                  |
| --------------------- | ------------------------------------------------ |
| Select Single Journey | Return fare field is hidden                      |
| Select Return Journey | Return fare field is displayed                   |
| Enter passenger count | Fare is calculated according to configured logic |
| Select payment mode   | Selected payment mode is captured                |
| Submit ticket request | Ticket request is created                        |
| Generate ticket       | Unique ticket number is available                |
| Open digital ticket   | Ticket details are displayed                     |
| Generate QR code      | QR code is displayed                             |
| Scan QR code          | Encoded ticket information is available          |


# 🚀 Future Enhancements

The following features can be added in future versions:

* Online payment gateway integration
* Real-time metro station search
* Station-to-station fare database
* Ticket cancellation
* Ticket booking history
* Email/SMS ticket confirmation
* QR code validation
* Ticket expiry
* Admin dashboard
* Passenger profile
* Multiple metro routes
* Real-time metro information
* Automated ticket verification

---

# 🎓 Learning Outcomes

This project helped demonstrate practical knowledge of:

* ServiceNow Studio
* Service Catalog
* Catalog Items
* Catalog Variables
* Client Scripts
* UI Policies
* Flow Designer
* Service Portal
* Service Portal Widgets
* JavaScript
* Form validation
* Dynamic form behavior
* Workflow automation
* QR code integration
