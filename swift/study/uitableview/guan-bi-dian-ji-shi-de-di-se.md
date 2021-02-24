# 關閉點擊時的底色

```swift
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = tableView.dequeueReusableCell(withIdentifier: "Cell", for: indexPath)
        
        // 加入以下這行
        cell.selectionStyle = .none
        
        return cell
    }
```

