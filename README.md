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

3. On the first section of the script, replace ```C:\path\to\``` with the actual path to your users csv file.
   For ```user_update_log.txt``` and ```user_update_error_log.txt```, choose a preferred path to replace their               ```C:\path\to\```, your preferred will determine where the logFile and erorrLogFile would be created.
   ```powershell
   # Path to the CSV file and log files
   $csvPath = "C:\path\to\users.csv"
   $logFilePath = "C:\path\to\user_update_log.txt"
   $errorLogFilePath = "C:\path\to\user_update_error_log.txt"
   ```

5. Run the script:
   ```powershell
   .\Update-AzureADUsers.ps1
   ```
6. Review the Logs:
   After execution, logs will be saved to ```user_update_log.txt``` and ```user_update_error_log.txt``` in your specified directory.


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
Contributions are welcome! Please see the [Contributing Guidelines](CONTRIBUTING.md) for more information.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
