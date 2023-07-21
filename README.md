# Carved Rock - Docker
This repo contains some simple code that illustrates .NET applications targeting
Docker containers.

## Initial Creation Notes
The project was created by using the ASP.NET Web API (.NET 5 - C#) template and including Docker Support.

It also added the `.vscode` folder to support running and debugging the project within VS Code.

No other initial changes were made for the initial commit of the repo.


## GitHub Actions
This repo contains a `yaml` file that defines a GitHub
Action that will build the container image and push it to hub.docker.com when changes
are made to the `main` branch (either by pull request or direct push).  Changes to readme, vscode, and
gitignore will not trigger this action.

It uses the https://github.com/docker/build-push-action action.

docker run -p 5000:80 -e SimpleProperty="docker!" -e ASPNETCORE_ENVIRONMENT="Development" --name crtest -d carvedrockdocker
docker tag --help
docker tag carvedrockdocker:latest dahlsailrunner/carvedrockapi:latest
docker tag dahlsailrunner/carvedrockapi:latest dahlsailrunner/carvedrockapi:1.0
docker info

docker push --all-tags dahlsailrunner/carvedrockapi
docker push dahlsailrunner/carvedrockapi:latest


docker tag dahlsailrunner/carvedrockapi:latest seadavdicloxxess/carvedrockapi:latest
docker login
docker push seadavdicloxxess/carvedrockapi:latest