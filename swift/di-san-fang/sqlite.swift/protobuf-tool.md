# protobuf tool

`bin/protoc`是官方預先編譯好的可執行檔

```bash
// 編譯指令
// larzio.proto為原始要被編譯的檔
// 若編譯成功會產出larzio.pb.swift檔

$ ./protoc --swift_out=. larzio.proto
```

{% embed url="https://github.com/protocolbuffers/protobuf/releases/tag/v3.12.3" caption="protobuf" %}

無法順利編譯或少了某些檔，可參考Apple官方的swift protobuf文件，如下

```bash
// 建立swift-protobuf資料夾並下載
$ git clone https://github.com/apple/swift-protobuf.git

// 切換至目錄
$ cd swift-protobuf

// 不指定安裝版本的話，預設會直接安裝最新版本
$ swift build -c release

// 產出protoc-gen-swift檔，於路徑.build/release底下

// 查詢環境變數路徑
% echo $PATH

// 將產出的protoc-gen-swift檔複製一份到環境變數底下
% sudo cp protoc-gen-swift /usr/local/bin

// 所有步驟完成回最上面重新編譯
```



{% embed url="https://github.com/apple/swift-protobuf" caption="swift-protobuf" %}





