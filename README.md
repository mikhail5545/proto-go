# Shared Protobuf Go module

## Protocol buffer compiler installation

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

## Install go packages

```bash
    go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
    go install google.golang.org/grpc/cmd/protoc-gen-go@latest
    which protoc-gen-go
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
    proto/product_service/category/v0/*.proto \
    proto/product_service/collection/v0/*.proto
    proto/product_service/course/v1/*.proto \
    proto/product_service/digital/v0/*.proto \
    proto/product_service/image/v0/*.proto \
    proto/product_service/lesson/v0/*.proto \
    proto/product_service/lesson/lesson_video/v0/*.proto \
    proto/product_service/physical/v1/*.proto \
    proto/product_service/product/v0/*.proto \
    proto/product_service/seminar/v1/*.proto \
    proto/product_service/training/v1/*.proto \
    proto/product_service/variant/v0/*.proto \
    proto/product_service/variant/variant_price/v0/*.proto \
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