If the Kestrel / IIS Express development certificate has expired, simply create and use a new certificate with the following steps.

1. Clean the old certificate and generate a new trusted one.
```PowerShell
dotnet dev-certs https --clean
dotnet dev-certs https --trust
```
2. Go to `%APPDATA%\Microsoft\UserSecrets` and open the folder containing the GUID of the problematic project you are struggling with and delete the folder with its content.
