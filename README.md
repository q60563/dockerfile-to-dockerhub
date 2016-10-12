# 如何透過 github 將 Dockerfile 上傳至 Dockerhub
- 與 github 建立連結
 - 首先進到 [Dockerhub首頁](https://hub.docker.com)登入
 - 點選 Create/Create Automated Build
 - 選擇 github 
 - 於 github 點選同意

- 將 dockerfile push 至 github
 - 在 [github](https://github.com/) 中新建一個 repository
 - 並將 dockerfile push 至該 repository

- 於 dockerhub 建立與 github 連結的 repository
 - 回到 [dockerhub](https://hub.docker.com) 再次點選 Create/Create Automated Build
 - 選擇 github
 - 此時會看到 github 中所有的 repository 提供選取
 - 選取剛剛建立的 repository
 - 輸入 Short Description (此欄為必填)
 - 後點選 Create 創建一個 docker repository

- dockerfile 內容為空的？
 - 剛建立完畢後會發現 dockerfile 內容為空的
 - 此時點選 Build Details 去看看發生了什麼事
 - 此處會看到有個上傳項目處於 Building 狀態
 - 等待個約莫 5 分鐘
 - 會看到狀態變更為 Success
 - 此時回到 dockerfile 會看到內容和 github 上的 dockerfile 相同
 - 該連結為自動更新，因此如github上的 dockerfile 有所更動 dockerhub 也會同步更新

- 將 image 上傳至 dockerhub
 - 此處需將 image tag 更改為和 repository 相同的名稱
 ```
 $ docker tag mongodb:latest chunwang/mongodb-dockerfile:latest
 ```


