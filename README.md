# Supported tags and respective `Dockerfile` links

-       [`1.0-sdk-projectjson` (*1.0/debian/sdk/projectjson/Dockerfile*)](https://github.com/cvallance/dotnetandmono-docker/blob/master/1.0/debian/sdk/projectjson/Dockerfile)
-       [`1.0-sdk-msbuild` (*1.0/debian/sdk/msbuild/Dockerfile*)](https://github.com/cvallance/dotnetandmono-docker/blob/master/1.0/debian/sdk/msbuild/Dockerfile)
-       [`1.1-sdk-projectjson` (*1.1/debian/sdk/projectjson/Dockerfile*)](https://github.com/cvallance/dotnetandmono-docker/blob/master/1.1/debian/sdk/projectjson/Dockerfile)
-       [`1.1-sdk-msbuild` (*1.1/debian/sdk/msbuild/Dockerfile*)](https://github.com/cvallance/dotnetandmono-docker/blob/master/1.1/debian/sdk/msbuild/Dockerfile)

# About

This is a simple repo to extend the offical (microsoft/dotnet)[https://hub.docker.com/r/microsoft/dotnet/] docker images with mono.

It uses the installation method outlined on (Install Mono on Linux)[http://www.mono-project.com/docs/getting-started/install/linux/]. You can view the docker files in the repo but
specifically it has the following line:

```
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF && \
  echo "deb http://download.mono-project.com/repo/debian wheezy main" | tee /etc/apt/sources.list.d/mono-xamarin.list && \
  echo "deb http://download.mono-project.com/repo/debian wheezy-apache24-compat main" | tee -a /etc/apt/sources.list.d/mono-xamarin.list && \
  echo "deb http://download.mono-project.com/repo/debian wheezy-libjpeg62-compat main" | tee -a /etc/apt/sources.list.d/mono-xamarin.list && \
  apt-get update && \
  apt-get install -y mono-complete && \
  rm -rf /var/lib/apt/lists/*
```