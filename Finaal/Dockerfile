#Build an image starting with the latest .net image
FROM microsoft/dotnet:latest

#Add the current directory . into the path /app in the image.
ADD . /app

#Set the working directory to /app
WORKDIR /app

RUN ["dotnet", "restore"]
RUN ["dotnet", "build"]

#Expose port 5000 to the host
EXPOSE 5000/tcp

#Sets the environment variable ASPNETCORE_URLS in the container.
#This will ensure that ASP.NET Core binds to the correct port and address.
ENV ASPNETCORE_URLS http://*:5000

#Specifies the command to execute when the container starts up.
ENTRYPOINT ["dotnet", "run"]