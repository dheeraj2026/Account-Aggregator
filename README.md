# Account Aggregator Platform

## Project Overview

This project implements a secure Account Aggregator platform that enables consent-based retrieval of customer financial information.

The application allows users to:

* Register and Login
* Create customer consents
* Store consent information
* Store account information
* Store transaction information
* Generate AI-powered financial summaries
* Access dashboard insights

---

# Technology Stack

Backend:

* Java 17
* Spring Boot
* Spring Security
* Spring Data JPA

Database:

* PostgreSQL

AI:

* GenAI API Integration Ready

Security:

* BCrypt Password Hashing
* Session Management
* Secure Cookies

---

# Project Structure

## pom.xml

Purpose:

* Maven dependency management
* Build configuration

Contains:

* Spring Boot dependencies
* PostgreSQL dependency
* Security dependency
* JPA dependency

---

## application.properties

Purpose:

* Application configuration

Contains:

* Database configuration
* Session timeout configuration
* Server configuration
* Digio configuration placeholders
* GenAI API placeholders

---

## AaBackendApplication.java

Purpose:

* Main Spring Boot application

Responsibilities:

* Starts Spring Boot server
* Initializes all components

Entry Point:

public static void main(String[] args)

---

# Authentication Module

## User.java

Purpose:

* Represents user information

Fields:

* id
* name
* email
* password
* role

Database Table:
users

---

## UserRepository.java

Purpose:

* Database access layer

Responsibilities:

* Find users
* Save users
* Retrieve user information

---

## RegisterRequest.java

Purpose:

* User registration request

Fields:

* name
* email
* password

---

## LoginRequest.java

Purpose:

* User login request

Fields:

* email
* password

---

## SecurityConfig.java

Purpose:

* Security configuration

Responsibilities:

* BCrypt password hashing

Features:

* Password encryption

---

## AuthService.java

Purpose:

* Authentication business logic

Responsibilities:

* User registration
* User login
* Password validation

Features:

* BCrypt password verification

---

## AuthController.java

Purpose:

* Authentication APIs

Endpoints:

POST /api/auth/register

POST /api/auth/login

POST /api/auth/logout

Responsibilities:

* Accept user requests
* Create user sessions

---

# Consent Module

## Consent.java

Purpose:

* Consent information

Fields:

* consentId
* customerId
* purpose
* status

Database Table:
consents

---

## ConsentRepository.java

Purpose:

* Consent database operations

Responsibilities:

* Save consent
* Retrieve consent

---

## CreateConsentRequest.java

Purpose:

* Request object for creating consent

Fields:

* customerId
* purpose

---

## ConsentService.java

Purpose:

* Consent business logic

Responsibilities:

* Generate consent IDs
* Create consent records

---

## ConsentController.java

Purpose:

* Consent APIs

Endpoint:

POST /api/consents

Responsibilities:

* Create customer consent

---

# Financial Data Module

## Account.java

Purpose:

* Account information

Fields:

* accountNumber
* accountType
* balance
* customerId

Database Table:
accounts

---

## AccountRepository.java

Purpose:

* Account database operations

Responsibilities:

* Save account data
* Retrieve account data

---

## Transaction.java

Purpose:

* Transaction information

Fields:

* amount
* transactionType
* description
* transactionDate

Database Table:
transactions

---

## TransactionRepository.java

Purpose:

* Transaction database operations

Responsibilities:

* Save transactions
* Retrieve transactions

---

# AI Module

## GenAIService.java

Purpose:

* Generate financial insights

Responsibilities:

* Financial summary generation
* Spending analysis
* AI insights generation

Security:

* API key stored externally
* API key never committed to GitHub

Configuration:

genai.api.key=YOUR_API_KEY_HERE

---

# Dashboard Module

## DashboardController.java

Purpose:

* Dashboard APIs

Endpoint:

GET /api/dashboard/summary

Responsibilities:

* Generate financial summary
* Return AI-generated insights

---

# Security Features

Implemented:

✓ BCrypt Password Hashing

✓ Session-Based Authentication

✓ Session Timeout (30 Minutes)

✓ Secure Cookie Support

✓ Password Encryption

✓ API Key Protection

---

# Database Tables

users

consents

accounts

transactions

---

# How to Run

## Step 1

Install:

* Java 17
* Maven
* PostgreSQL

---

## Step 2

Create database:

CREATE DATABASE aa_db;

---

## Step 3

Update application.properties

spring.datasource.url=jdbc:postgresql://localhost:5432/aa_db

spring.datasource.username=postgres

spring.datasource.password=YOUR_PASSWORD

---

## Step 4

Open terminal

Navigate:

cd aa-backend

---

## Step 5

Build project

mvn clean install

---

## Step 6

Run project

mvn spring-boot:run

---

## Step 7

Verify server

http://localhost:8080

---

## Step 8

Test APIs

Register:

POST /api/auth/register

Login:

POST /api/auth/login

Create Consent:

POST /api/consents

Generate AI Summary:

GET /api/dashboard/summary

---

# Future Enhancements

* Full Digio API Integration
* Transaction Categorization
* Credit Risk Analysis
* Spending Analytics
* Financial Health Scoring
* Angular Frontend Dashboard
