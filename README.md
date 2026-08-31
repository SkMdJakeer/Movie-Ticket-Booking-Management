# NIP Movie Ticket Booking

## Project Overview

**NIP-MovieTicket-SHAIK MOHAMMAD JAKEER** is a Pega Platform application
for managing movie ticket booking requests from submission through
confirmation and resolution.

The application uses a structured case lifecycle to collect booking
information, check availability, calculate cost, obtain approval,
execute the booking, and complete the case.

## Project Details

  Item               Details
  ------------------ ------------------------------------------------
  Project            Movie Ticket Booking
  Pega Application   NIP-MovieTicket-SHAIK MOHAMMAD JAKEER
  Case Type          Movie Ticket Request
  Operator           Shaik Mohammad Jakeer
  Email              shaikjakeer0205@gmail.com
  Course             BTech CSE
  College            KKR & KSR INSTITUTE OF TECHNOLOGY AND SCIENCES
  State              Andhra Pradesh

## Case Lifecycle

The Movie Ticket Request follows these stages:

1.  **Initial Request** -- Captures Movie Name, Show Date, Show Time,
    and Number of Tickets with required-field validation.
2.  **Availability** -- Captures available seat information and
    availability status before booking proceeds.
3.  **Approval** -- Allows the booking to be confirmed or
    rejected/cancelled through the Booking Status decision.
4.  **Booking Execution** -- Maintains the Ticket ID, Seat Numbers, and
    Booking Confirmation Status.
5.  **Resolved** -- Finalizes the booking and completes the confirmation
    correspondence.

## Main Features

### 1. Movie Ticket Request

Customers provide the movie name, show date, show time, and number of
tickets. Required-field validation is applied.

### 2. Show Availability

The Availability stage records the available seat count and seat
availability information before the booking continues.

### 3. Automatic Booking Cost

The application calculates Total Cost automatically using:

**Total Cost = Ticket Price × Number of Tickets**

The rule used is:

-   **Rule Name:** `CalculateTotalCost`
-   **Rule Type:** Declare Expression
-   **Properties:** Ticket Price, Number of Tickets

### 4. Booking Approval

The Approval stage lets the customer confirm the booking through the
Booking Status decision and continue through the confirmed path.

### 5. Movie and Show Data

Reusable data objects are used:

-   **Movie:** Movie Name, Genre
-   **Show:** Show Date, Show Time, Seat Capacity

These objects are associated with the Movie Ticket Request case.

### 6. Booking Execution

The Booking Execution stage maintains:

-   Ticket ID
-   Seat Numbers
-   Booking Confirmation Status

### 7. Confirmation Email

A confirmation correspondence step is configured for case completion.
The email contains booking information such as the movie, show
date/time, seats, number of tickets, and total cost.

### 8. Service-Level Agreement

A Custom SLA is configured with:

-   **Goal:** 1 day
-   **Deadline:** 2 days
-   **Urgency:** Increased on breach

### 9. Show-Type Routing

Business Logic routes cases according to Show Type:

-   `PremiumShowQueue` -- IMAX/premium or special screenings
-   `StandardShowQueue` -- all other show types
-   `BookingAgentQueue` -- booking approval/work assignment in the case
    flow

For example, IMAX requests are routed to `PremiumShowQueue`, while other
show types are routed to `StandardShowQueue`.

## Personas

The application uses these personas:

-   Booking Agent
-   Customer
-   Users

## Important Rules

  Rule                        Type
  --------------------------- --------------------
  `CalculateTotalCost`        Declare Expression
  `ProcessConfirmedBooking`   Data Transform
  `BookingExecution_Flow`     Flow

## Example Booking

The completed project demonstrates a confirmed booking with:

-   Customer: **Shaik Mohammad Jakeer**
-   Number of Tickets: **5**
-   Seat Numbers: **A5, A6, B5**
-   Show Date: **September 5, 2026**
-   Show Time: **2:30 PM**
-   Show Type: **Standard**
-   Total Cost: **\$45.50**
-   Booking Status: **Confirmed**

## Workflow Summary

``` text
Customer creates request
        ↓
Initial Request
        ↓
Availability Check
        ↓
Calculate Booking Cost
        ↓
Approval
        ↓
Booking Execution
        ↓
Confirmation Correspondence
        ↓
Resolved
```

## Technology

-   **Platform:** Pega Platform
-   **Application:** Pega App Studio / Dev Studio
-   **Case Type:** Movie Ticket Request
-   **Business Logic:** Work-queue routing and case rules
-   **Automation:** Declare Expression, Data Transform, Flow,
    Correspondence, and SLA configuration

## Project Outcome

The project provides an end-to-end movie ticket booking workflow in
Pega. It demonstrates case management, reusable data objects, calculated
fields, approval handling, work-queue routing, SLA configuration,
booking execution, and customer confirmation.

## Author

**Shaik Mohammad Jakeer**\
BTech CSE\
KKR & KSR INSTITUTE OF TECHNOLOGY AND SCIENCES
