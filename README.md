# Azure AD User Management Automation Script

This repository contains a PowerShell script that automates the process of updating user properties in Azure Active Directory (Azure AD) from a CSV file. It handles updating job titles, departments, display names, and manager assignments, along with comprehensive logging and error handling.

## Key Features
- **Bulk User Updates**: Efficiently updates job title, department, and display name for users.
- **Manager Assignment**: Automatically assigns managers to users based on UPN.
- **Retry Logic**: Built-in retry mechanism for transient Azure AD failures.
- **Logging**: Detailed logs for both successful updates and errors.

## Prerequisites
To use this script, you need the following:
- PowerShell 5.1 or later.
- Azure AD PowerShell Module installed:
   ```powershell
   Install-Module -Name AzureAD

## How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/uceworld/azure-ad-management-script.git
   ```
2. Configure the CSV input file.
3. Run the script:
   ```powershell
   .\Update-AzureADUsers.ps1
   ```

## Example
Update the users based on the provided CSV file:
```powershell
.\Update-AzureADUsers.ps1
-CsvPath "C:\path\to\file.csv"
