# UITableView 分頁、滑至列表最後一筆上拉載入更多資料

```swift
//
//  ViewController.swift
//  tableViewReloadTest
//
//  Created by kokome maxkit on 2020/5/25.
//  Copyright © 2020 kokome maxkit. All rights reserved.
//


//
// UITableView 分頁、滑至列表最後一筆上拉載入更多資料
// Ref: https://reurl.cc/4RlKVY
//


import UIKit

// 頁面狀態
enum PageStatus {
    case LoadingMore
    case NotLoadingMore
}

class ViewController: UIViewController {

    @IBOutlet weak var tableView: UITableView!
    
    var dataList: [String] = {
        return Array(repeating: "", count: 12)
    }()

    var pageStatus: PageStatus = .NotLoadingMore
    
    override func viewDidLoad() {
        super.viewDidLoad()
        tableView.dataSource = self
        tableView.delegate = self
    }
    
}

// MARK: UITableViewDataSource
extension ViewController: UITableViewDataSource {
    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        
        var rows: Int = 0
        
        switch self.pageStatus {
        case .LoadingMore:
            rows = self.dataList.count + 1
        default:
            rows = self.dataList.count
        }
        
        return rows
    }
    
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
      
        if indexPath.row == self.dataList.count {
            let cell = tableView.dequeueReusableCell(withIdentifier: "LoadingMoreTableViewCell", for: indexPath) as! LoadingMoreTableViewCell
            cell.activityIndicatorView.startAnimating()
                                
            return cell
        } else {
            let cell = tableView.dequeueReusableCell(withIdentifier: "MyCell", for: indexPath)
            cell.textLabel?.text = "\(indexPath.row + 1)"
            return cell
            
        }
        
    }
    
}

// MARK: UITableViewDelegate
extension ViewController: UITableViewDelegate {
    func tableView(_ tableView: UITableView, heightForRowAt indexPath: IndexPath) -> CGFloat {
        return 75
    }
    
}

extension UITableView {
    func reloadData(completion:@escaping ()->()) {
        
        UIView.animate(
            withDuration: 0,
            animations: {
                // 第一次reload, 讓tableView cell render indicator動畫, 等render完成後會執行到94行
                self.reloadData()
            }) {
                // 第二次reload入口
                _ in completion()
        }
    }
}


// MARK: UIScrollViewDelegate
extension ViewController: UIScrollViewDelegate {
    func scrollViewDidEndDragging(_ scrollView: UIScrollView, willDecelerate decelerate: Bool) {
        
        // EX: iPhone 11
        // scrollView.contentSize.height: 896(default), 900(捲動時, contentSize會根據捲動時增加)
        // self.tableView.frame.height: 896, 高度與scrollView相同
        // scrollView.frame.size.height: 896
        
        // 當滾動的範圍超過 TableView 的高度「且」頁面狀態為 NotLoadingMore 的時侯
        // 才會判斷使用者是否已滾動到最後一筆資料。
        guard scrollView.contentSize.height > self.tableView.frame.height,
            self.pageStatus == .NotLoadingMore else {
            return
        }
        
        // 判斷使用者是否已滾動到最後一筆資料, 且又持續往下拉
        if scrollView.contentSize.height - (scrollView.frame.size.height + scrollView.contentOffset.y) <= -10 {
                        
            self.pageStatus = .LoadingMore
            
            // 第一次reload入口
            self.tableView.reloadData {
                
                // 第二次reload, 再載入新的六筆資料, 並將狀態改為NotLoadingMore
                // 模擬 Call API 的時間
                DispatchQueue.main.asyncAfter(deadline: .now() + 2) {
                    
                    self.dataList += Array(repeating: "", count: 6)
                    self.pageStatus = .NotLoadingMore
                    
                    // 最後一次reload, 更新畫面
                    self.tableView.reloadData()
                }
            }
            
        }
    }
}

```

## Ref.

{% embed url="https://medium.com/@mikru168/ios-uitableview-%E5%88%86%E9%A0%81-%E6%BB%91%E8%87%B3%E5%88%97%E8%A1%A8%E6%9C%80%E5%BE%8C%E4%B8%80%E7%AD%86%E4%B8%8A%E6%8B%89%E8%BC%89%E5%85%A5%E6%9B%B4%E5%A4%9A%E8%B3%87%E6%96%99-loading-more-69ee25eae045" %}



