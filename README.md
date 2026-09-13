# AI Invoice & Document Data Extraction Automation

AI-powered invoice document processing workflow built with n8n Cloud, Google Gemini, PostgreSQL, Python, and Gmail.

## Overview

This project automates the extraction, validation, storage, and notification of invoice data from PDF documents.

The workflow receives an invoice PDF through a webhook, extracts the document text, uses AI to convert the invoice into structured data, validates the extracted values, stores the invoice in PostgreSQL, and sends a processing notification by email.

## Workflow Architecture

Invoice PDF
↓
Receive Document
↓
Extract Document Text
↓
AI Invoice Data Extraction
↓
Parse AI Invoice Result
↓
Validate Extracted Data
↓
Save Invoice to PostgreSQL
↓
Generate Processing Result
↓
Send Processing Notification

## Technology Stack

- n8n Cloud
- Google Gemini
- PostgreSQL / Neon
- Python
- JavaScript
- Gmail
- Webhook
- PDF document processing

## Features

- PDF invoice upload through webhook
- Automatic PDF text extraction
- AI-powered invoice data extraction
- Structured JSON output
- Invoice field validation
- Subtotal + tax total verification
- PostgreSQL invoice storage
- Invoice upsert using invoice number
- Automated processing result generation
- Gmail notification

## Extracted Invoice Data

The workflow extracts:

- Invoice number
- Invoice date
- Due date
- Vendor name
- Vendor address
- Customer name
- Customer address
- Invoice items
- Quantity
- Unit price
- Item total
- Subtotal
- Tax
- Total amount
- Currency
- Payment terms

## Validation

The workflow validates required invoice fields and verifies that:

Subtotal + Tax = Total Amount

For the test invoice:

- Subtotal: PHP 78,000.00
- Tax: PHP 9,360.00
- Total Amount: PHP 87,360.00
- Calculated Total: PHP 87,360.00
- Difference: PHP 0.00
- Validation Status: Valid

## Database

Invoice records are stored in a PostgreSQL database using the `invoices` table.

The workflow uses `invoice_number` as the matching field to prevent duplicate invoice records.

## Project Structure

```text
AI-Invoice-Document-Extraction
├── data
│   ├── sample_invoice.pdf
│   └── sample_invoice.txt
├── docs
├── screenshots
│   ├── 01-complete-workflow.png
│   ├── 02-ai-invoice-extraction-output.png
│   ├── 03-invoice-validation-output.png
│   ├── 04-invoice-postgresql-record.png
│   └── 05-processing-notification-email.png
├── workflow
│   └── AI Invoice & Document Data Extraction Automation.json
├── app.py
└── README.md