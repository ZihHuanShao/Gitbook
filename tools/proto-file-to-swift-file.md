# proto file to swift file

由Google定義的`.proto`檔轉換成`.swift`檔的步驟：

1. 下載 `$ git clone https://github.com/apple/swift-protobuf.git`  `$ cd swift-protobuf`
2. 查詢版本，看要套用哪個版本 `$ git tag -l`
3. 產生build tool `$ git checkout tags/[tag_name]`  `$ swift build -c release` 完成後會產生一個**protoc-gen-swift**的檔案，在路徑`.build/release`底下\(該路徑是隱藏的\)
4. 把你編輯好的`.proto`檔\(假設為`hw.proto`\)與**protoc-gen-swift**檔案放在同一個路徑底下
5. 編譯 `$ protoc --swift_out=. hw.proto` 編譯成功後會產生相對應的`.swift`檔 \(檔名為`hw.pb.swift`\)
6. 接下來可以在XCode直接存取該檔

若有使用其他第三方工具還需要額外的步驟，如cocoapods，請參考下方連結

## Ref.

{% embed url="https://github.com/apple/swift-protobuf" %}

{% embed url="https://yami.io/protobuf/" caption="Protobuf優勢介紹" %}





