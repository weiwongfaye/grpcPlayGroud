# GRPC 

### Steps:


1. create ecommerce.proto under ecommerce folder
2. generate server&client code 

        $ protoc --go_out=. --go_opt=paths=source_relative \
        --go-grpc_out=. --go-grpc_opt=paths=source_relative \
        ecommerce/ecommerce.proto
3. write server side code and implement real logic

### Notes:
- pay attention to the server defination, pb.UnimplementedProductInfoServer must be there

        type server struct {
            pb.UnimplementedProductInfoServer
            productMap map[string]*pb.Product
        }
