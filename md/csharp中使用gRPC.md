#
***
[Hello World 示例项目地址](https://github.com/grpc/grpc/tree/master/examples/csharp/Helloworld)
***

# helloworld.proto
    syntax = "proto3";

    option java_multiple_files = true;
    option java_package = "io.grpc.examples.helloworld";
    option java_outer_classname = "HelloWorldProto";
    option objc_class_prefix = "HLW";

    package helloworld;

    // The greeting service definition.
    service Greeter {
    // Sends a greeting
    rpc SayHello (HelloRequest) returns (HelloReply) {}
    }

    // The request message containing the user's name.
    message HelloRequest {
    string name = 1;
    }

    // The response message containing the greetings
    message HelloReply {
    string message = 1;
    }
# Helloworld\GreeterServer\Program.cs
    using System;
    using System.Threading.Tasks;
    using Grpc.Core;
    using Helloworld;

    namespace GreeterServer
    {
        class GreeterImpl : Greeter.GreeterBase
        {
            // Server side handler of the SayHello RPC
            public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
            {
                return Task.FromResult(new HelloReply { Message = "Hello " + request.Name });
            }
        }

        class Program
        {
            const int Port = 50051;

            public static void Main(string[] args)
            {
                Server server = new Server
                {
                    Services = { Greeter.BindService(new GreeterImpl()) },
                    Ports = { new ServerPort("localhost", Port, ServerCredentials.Insecure) }
                };
                server.Start();

                Console.WriteLine("Greeter server listening on port " + Port);
                Console.WriteLine("Press any key to stop the server...");
                Console.ReadKey();

                server.ShutdownAsync().Wait();
            }
        }
    }

# Helloworld\GreeterClient\Program.cs

    using System;
    using Grpc.Core;
    using Helloworld;

    namespace GreeterClient
    {
        class Program
        {
            public static void Main(string[] args)
            {
                Channel channel = new Channel("127.0.0.1:50051", ChannelCredentials.Insecure);

                var client = new Greeter.GreeterClient(channel);
                String user = "you";

                var reply = client.SayHello(new HelloRequest { Name = user });
                Console.WriteLine("Greeting: " + reply.Message);

                channel.ShutdownAsync().Wait();
                Console.WriteLine("Press any key to exit...");
                Console.ReadKey();
            }
        }
    }


# Helloworld\Greeter\Greeter.csproj

    <Project Sdk="Microsoft.NET.Sdk">

    <PropertyGroup>
        <TargetFramework>netstandard1.5</TargetFramework>
    </PropertyGroup>

    <ItemGroup>
        <PackageReference Include="Google.Protobuf" Version="3.6.1" />
        <PackageReference Include="Grpc" Version="1.17.0" />
        <PackageReference Include="Grpc.Tools" Version="1.17.0" PrivateAssets="All" />
    </ItemGroup>

    <ItemGroup>
        <Protobuf Include="../../../protos/helloworld.proto" Link="helloworld.proto" />
    </ItemGroup>

    </Project>

# Helloworld\GreeterServer\GreeterServer.csproj

    <Project Sdk="Microsoft.NET.Sdk">

    <PropertyGroup>
        <TargetFramework>netcoreapp2.1</TargetFramework>
        <OutputType>Exe</OutputType>
    </PropertyGroup>

    <ItemGroup>
        <ProjectReference Include="..\Greeter\Greeter.csproj" />
    </ItemGroup>

    </Project>


# Helloworld\GreeterClient\GreeterClient.csproj

    <Project Sdk="Microsoft.NET.Sdk">

    <PropertyGroup>
        <TargetFramework>netcoreapp2.1</TargetFramework>
        <OutputType>Exe</OutputType>
    </PropertyGroup>

    <ItemGroup>
        <ProjectReference Include="..\Greeter\Greeter.csproj" />
    </ItemGroup>

    </Project>

