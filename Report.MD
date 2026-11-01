# CI/CD Evidence Report

## 1. Project Overview

The Weather Forecast Application is an ASP.NET Core MVC web application developed using C# and .NET 10. It provides current and forecasted weather information through a third-party weather API.

Project documentation: `README.md`

## 2. CI/CD Implementation

A GitHub Actions workflow was added at `.github/workflows/ci-cd.yml`.

The workflow is triggered by:

- Pushes to the `main` branch
- Pull requests targeting `main`
- Manual workflow execution

## 3. Continuous Integration Stages

The pipeline performs the following steps:

1. Checks out the source code.
2. Installs the .NET 10 SDK.
3. Restores project dependencies.
4. Builds the application in Release configuration.
5. Executes automated tests.
6. Publishes the application for deployment.
7. Uploads the published files as a GitHub Actions artifact.

## 4. Deployment Testing

A separate deployment smoke-test job downloads the published artifact and starts the application locally using:

```bash
dotnet WeatherApp.dll --urls http://127.0.0.1:5080
```

The pipeline then sends an HTTP request to the deployed application and confirms that it responds successfully. This verifies that the published deployment package can start and serve the application correctly.

## 5. Evidence Collected

The following evidence can be attached to the report:

- GitHub Actions workflow file
- Successful workflow run summary
- Successful restore log
- Successful build log
- Successful test execution log
- Published artifact listing
- Deployment smoke-test success log
- Application browser screenshot after deployment

## 6. Validation Results

| Validation Area | Result |
|---|---|
| Dependency restore | Passed |
| Release build | Passed |
| Automated test command | Passed |
| Application publish | Passed |
| Deployment smoke test | Configured |
| Artifact generation | Configured |

## 7. Conclusion

The project now includes a CI/CD process that automatically validates code changes, builds the application, creates a deployment package, and tests the published application. This improves deployment reliability and helps identify build or deployment issues before release.