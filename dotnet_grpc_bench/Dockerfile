FROM mcr.microsoft.com/dotnet/sdk:6.0

WORKDIR /app
COPY dotnet_grpc_bench /app
COPY proto /proto

RUN dotnet build -c Release Greeter.sln

# set gc server compare test1
ENV DOTNET_ReadyToRun=0
ENV DOTNET_TieredPGO=1
ENV DOTNET_TC_QuickJitForLoops=1
# ENV DOTNET_gcServer=1
# ENV DOTNET_gcConcurrent=1


ENTRYPOINT [ "dotnet", "run" , "-c", "Release", "-p", "GreeterServer", "--no-build" ]
