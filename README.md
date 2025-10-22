# Shared Protobuf Go module

## Protocol bufffer compiler installation

To compile .proto fils you need to install *protocol buffer compiler*, to do so:

### Linux, WSL

```bash
    sudo apt-get install -y protobuf-compiler
    protoc --version #Ensure compiler version satisfies your expectations
```

### Windows

```PowerShell
    winget install protobuf
    protoc --version #Ensure compiler version satisfies your expectations
```

## Compile .proto files

To compile .proto files use:

```bash
    protoc  --proto_path=proto \|
    --go_out=. --go_opt=module=github.com/mikhail5545/proto-go \|
    --go-grpc_out=. --go-grpc_opt=module=github.com/mikhail5545/proto-go \| 
    proto/product/v0/*.proto        \|
    proto/training_session/v0/*.proto        \|
    proto/course/v0/*.proto        \|
    proto/seminar/v0/*.proto
```

