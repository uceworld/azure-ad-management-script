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
- Administrative access to Azure AD.

## How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/uceworld/azure-ad-management-script.git
   ```
2. Prepare Your CSV File
   Use the sample CSV file (```users.csv```) in the repository to format your data.

3.  Configure the CSV input file.

4. Run the script:
   ```powershell
   .\Update-AzureADUsers.ps1
   ```
5. Review the Logs:
   After execution, logs will be saved to ```user_update_log.txt``` and ```user_update_error_log.txt``` in your specified directory.


## Example
Update the users based on the provided CSV file:
```powershell
.\Update-AzureADUsers.ps1
-CsvPath "C:\path\to\file.csv"
```

## Example CSV File
The CSV file should be structured as follows:
```csv
UserPrincipalName,JobTitle,Department,DisplayName,ManagerUPN
johndoe@company.com,Engineer,Engineering,John Doe,janedoe@company.com
janedoe@company.com,Manager,Operations,Jane Doe,johndoe@company.com
```

## Error Handling
- The script includes retry logic for up to 3 attempts in case of transient issues.
- Errors encountered during execution are logged in the error log file for review.

## Contributions
Contributions are welcome! Please see the Contributing Guidelines for more information.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
