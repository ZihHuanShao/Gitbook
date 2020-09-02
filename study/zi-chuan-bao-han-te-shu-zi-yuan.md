# 字串 包含特殊字元

```swift
func checkForIllegalCharacters(string: String) -> Bool {
    let invalidCharacters = CharacterSet(charactersIn: "\\/:*?\"<>|")
    .union(.newlines)
    .union(.illegalCharacters)
    .union(.controlCharacters)

    if string.rangeOfCharacter(from: invalidCharacters) != nil {
        print ("Illegal characters detected in file name")
        // Raise an alert here
        return true
    } else {
    return false
}
```



特殊字元的過濾條件需注意跳脫字元：

The problem is that characters `[`, `\`, and `]` need to be escaped because they have special meaning in a regular expression.

So you need `\[`, `\\`, and `\]` in the regular expression. But since this is inside a Swift string, each `\` needs to be escaped with a `\`.

So `[\]` becomes `\[\\\]` in the regular expression which becomes `\\[\\\\\\]` in the Swift string.

## Ref.

{% embed url="https://stackoverflow.com/questions/50179785/swift-regex-with-special-characters" %}

{% embed url="https://stackoverflow.com/questions/27703039/check-if-string-contains-special-characters-in-swift" %}



