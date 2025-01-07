# Setting up the ASP.NET Core (C#) Backend
This document provides detailed instructions to set up and run the ASP.NET Core backend for the CLI Task Timer project. Follow the steps below to ensure a smooth setup process.

---

## Prerequisites
1. **.NET SDK** (Version 6.0 or higher recommended)
   - Download and install the .NET SDK from dotnet.microsoft.com.
2. IDE (Integrated Development Environment)
   - Recommended: Visual Studio or Visual Studio Code.
4. Git
   - Ensure Git is installed to clone the repository.
   - Check by running
 ```bash
git --version
 ```

4. Postman or Browser
   - To test API endpoints
---

## File structure overview 
The backend folder structure is as follows:

```
.
├── Controllers
│   └── TimerController.cs
├── Data
│   └── database.json
├── Models
│   ├── AllTimers.cs
│   ├── TaskTimer.cs
│   └── functions.cs
├── Properties
│   └── launchSettings.json
├── obj
├── CLI_Task_Timer_CS.csproj
├── CLI_Task_Timer_CS.sln
├── Program.cs
├── Startup.cs
├── appsettings.Development.json
├── appsettings.json

```
- **`Controllers/TimerController.cs`**: Defines API endpoints for the timer.
- **`Data/database.json`**: Stores timer data.
- **`Models/`**: Contains core business logic classes (TaskTimer, AllTimers) and helper functions (functions.cs).
- **`Startup.cs`**: Configures application services and middleware.
- **`appsettings.json`**: Contains application settings like database paths or configurations.           

---

## Step-by-Step Guide

### 1. Clone the Repository

Clone the repository from GitHub:

```bash
git clone <repository-url>
cd <repository-folder>
```

Replace `<repository-url>` with the actual URL of the backend repository.

---
### 2. Open project in an IDE
- Open the solution file CLI_Task_Timer_CS.sln in Visual Studio or open the folder in Visual Studio Code.
- Ensure your IDE is configured to use the .NET Core SDK.

### 3. Restore Dependencies

Run the following command in the terminal to restore NuGet packages:
```bash
dotnet restore
```
This will download and install all the required dependencies listed in the .csproj file

### 4. Configure Database path
Check the appsettings.json or appsettings.Development.json file for the database path configuration. By default, it uses Data/database.json. Ensure this file exists and is accessible.

### 5. Run the Application 
Start the backend by executing the following command:
```bash
dotnet run
```
Alternatively, if you're using Visual Studio:
  1. Select the appropriate startup project (usually the .csproj file).
  2. Press F5 to run the application in debug mode or Ctrl + F5 to run it without debugging.
By default, the application will run on http://localhost:5000/.

### 6. Test API Endpoints
1. Open a browser or use Postman to navigate to the base URL:
```arduino
http://localhost:5000/
```
2. Test specific API routes defined in TimerController.cs.
   
---

## Common Commands
## Add new Dependencies
If you need to add a new NuGet package:
```bash
dotnet add package <Package-Name>
```

## Update Dependencies
Update all NuGet packages to their latest versions:
```bash
dotnet restore
```

## Build the application
To build the application and check for compile-time errors:
```bash
dotnet build
```

---

## Troubleshooting
1. Port in Use: If the default port (5000) is occupied, update the launchSettings.json file or add the following in Program.cs:
```csharp
    builder.WebHost.UseUrls("http://localhost:5001");
```
3. Restore Errors: Ensure that the .NET SDK is installed and the project file (.csproj) is intact.
4. File Path Issues: Verify the path to database.json in the appsettings.json file.
5. Dependency Issues: Run dotnet restore again to ensure all dependencies are installed.

---
Making sure you follow these steps correctly, you should be able to configure and run the ASP.NET Core backend succesfully.





