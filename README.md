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
    protoc  --proto_path=proto \
    --go_out=. --go_opt=module=github.com/mikhail5545/proto-go \
    --go-grpc_out=. --go-grpc_opt=module=github.com/mikhail5545/proto-go \
    /path/to/proto_file/file.proto /path/to/proto_file/file2.proto
```

To compile files for `product_service` directory:

```bash
    protoc  --proto_path=proto \
    --go_out=. --go_opt=module=github.com/mikhail5545/proto-go \
    --go-grpc_out=. --go-grpc_opt=module=github.com/mikhail5545/proto-go \
    proto/product_service/course/v0/*.proto \
    proto/product_service/course/v1/*.proto \
    proto/product_service/course_part/v0/*.proto \
    proto/product_service/physical_good/v0/*.proto \
    proto/product_service/physical_good/v1/*.proto \
    proto/product_service/product/v0/*.proto \
    proto/product_service/seminar/v0/*.proto \
    proto/product_service/seminar/v1/*.proto \
    proto/product_service/training_session/v0/*.proto \
    proto/product_service/training_session/v1/*.proto \
    proto/product_service/image/v0/*.proto \
    proto/product_service/video/v0/*.proto
```

To compile files for `media_service` directory:

```bash
    protoc  --proto_path=proto \
    --go_out=. --go_opt=module=github.com/mikhail5545/proto-go \
    --go-grpc_out=. --go-grpc_opt=module=github.com/mikhail5545/proto-go \
    proto/media_service/mux/asset/v0/*.proto
```

To compile files for `user_service` directory:

```bash
    protoc  --proto_path=proto \
    --go_out=. --go_opt=module=github.com/mikhail5545/proto-go \
    --go-grpc_out=. --go-grpc_opt=module=github.com/mikhail5545/proto-go \
    proto/user_service/user/v0/*.proto \
    proto/user_service/address/v0/*.proto 
```