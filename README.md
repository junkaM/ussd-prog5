# USSD Menu Simulation (MVola-like System)

This repository contains a Java-based simulation of a USSD menu system, inspired by MVola, a mobile money service in Madagascar. The project implements a command-line interface for managing user accounts, transactions, and various services like credit purchases, money transfers, and bill payments. It uses Maven for build management and Checkstyle for code quality enforcement.

## Overview

- **Language**: Java
- **Build Tool**: Apache Maven
- **Code Quality**: Checkstyle (configured via `checkstyle.xml`)
- **CI/CD**: GitHub Actions
- **Purpose**: Simulate a USSD menu .

The system includes:

- User authentication with phone numbers and PINs.
- Menu options for buying credits/offers, transferring money, managing savings, withdrawing cash, and paying bills.
- Transaction handling with balance checks.

## Prerequisites

- **Java Development Kit (JDK)**: Version 21 (or as specified in `pom.xml`).
- **Maven**: Version 3.9.6 or later.
- **Git**: For version control.
- **Operating System**: Windows, macOS, or Linux.

## Setup Instructions

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/junkaM/ussd-prog5.git
   cd ussd-prog5
   ```

2. **Install Dependencies**:

    - Ensure JDK 21 is installed. Verify with:

      ```bash
      java -version
      ```
    - Install Maven if not present. Verify with:

      ```bash
      mvn -version
      ```

3. **Build the Project**:

    - Run the following command to compile and verify the project:

      ```bash
      mvn clean verify
      ```
    - This also runs Checkstyle to enforce code quality rules.

4. **Run the Application**:

    - Execute the main class:

      ```bash
      mvn exec:java -Dexec.mainClass="org.prog5.Main"
      ```
    - Follow the USSD prompts (e.g., enter `#111#` to start).

## Usage

- **Start the Simulation**: Enter `#111#` to access the main menu.
- **Authentication**: Provide your phone number (e.g., `0321234567`) and PIN (e.g., `1234`).
- **Menu Options**:
    - 1: Buy Credit or Offer Yas
    - 2: Transfer Money
    - 3: Mvola Credit or Savings
    - 4: Withdraw Money
    - 5: Pay Bills & Partners
    - 6: Check Account Details
- **Example Interaction**:
    - Input: `#111#`
    - Input: `0321234567` (phone number)
    - Input: `1234` (PIN)
    - Select an option (e.g., `1` for credits).

## Project Structure

- `src/main/java/org/prog5/`:
    - `Main.java`: Entry point of the application.
    - `Transaction.java`: Handles transaction logic.
    - `User.java`: Manages user data (phone number, balance, PIN).
    - `USSDMenu.java`: Implements the USSD menu logic.
- `pom.xml`: Maven configuration file.
- `checkstyle.xml`: Checkstyle configuration for code quality.
- `.github/workflows/ci.yml`: GitHub Actions workflow for CI.

## Code Quality

- **Checkstyle**: Enforces rules like `NewlineAtEndOfFile`, `LineLength` (max 120), and proper indentation.
- **Verification**: Run locally with:

  ```bash
  mvn checkstyle:check
  ```
    - Check `target/site/checkstyle.html` for violations.
- **Fixing Violations**: Ensure all Java files end with a newline and follow the 4-space indentation rule.

## CI/CD Pipeline

- **GitHub Actions**: Configured in `.github/workflows/ci.yml`.
- **Workflow**:
    - Runs on `push` and `pull_request` to the `main` branch.
    - Uses JDK 21 and Maven 3.9.6.
    - Executes `mvn clean verify` and `mvn checkstyle:check`.
    - Caches Maven dependencies for efficiency.
- **Status**: Check the **Actions** tab on GitHub for build status.

## Contact

- **Owner**: junkaM
- **Repository**: https://github.com/junkaM/ussd-prog5
- **Issues**: Report bugs or suggestions in the Issues tab.

## Acknowledgments

- Inspired by MVola’s USSD interface.
- Built with guidance from Maven and Checkstyle communities.