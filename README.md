# Articulate on .NET Core

This is the .NET Core version of the classic Articulate app.  It does not at this time have service binding for external storage, but serves as a good example to scaling and recovery.

To deploy this app, you will need the dotnet core package installed.  You can find the latest version at Microosft's site: https://www.microsoft.com/net/download

*Deploying the App*

1.  Navigate to the folder where you have saved these files

2.  Type: dotnet publish -o .\publish to create the application

3.  Type: cf push articulate-dot-net -p .\publish . to push up to PAS.  Note that PAS will automatically find the right buildpack

*Differences from Linux Version*

Note that this version does not have a separate Attendee-Service or connection to database service.  There are a couple other options for this functionality.  There is local persistence on the app instances themselves.  So you can store different data on different instances (assuming you have multiple instances and you refresh).  I use this as an example of why data _should_ be separated.

