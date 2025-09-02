For original README see rqlite github. 

This is for how to build rqlite from vendor and all of the dependencies that it uses. 



From rqlite.io website on how to build from source: 

mkdir rqlite # Or any directory of your choice.
cd rqlite/
export GOPATH=$PWD
mkdir -p src/github.com/rqlite
cd src/github.com/rqlite
git clone https://github.com/rqlite/rqlite.git
cd rqlite
go install ./...
$GOPATH/bin/rqlited ~/node.1

To download all the dependencies into the vendor directory: 

go mod vendor


To build rqlite using the vendored dependencies: 

go build -mod=vendor ./... 





For installation into $GOPATH/bin: 

go install -mod=vendor ./...




Additional C Compiler Settings: 
- Ensure CGO_ENABLED=1 (default for most systems) 
- If compilation errors reference SQLITE symbols, export the proper C compiler: 

export CC=gcc


Run rqlite: 

./rqlited ~/node.1



The actual rqlited might be in the ./bin folder in your rqlite directory (the main directory)



Successfully built using:

go version go1.24.6 linux/amd64



