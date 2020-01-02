1./bin, 51./sbin
/bin 主要放置一般使用者可以操作的指令，/sbin 放置系統管理員可以操作的指令。連結到 /usr/bin，/usr/sbin

2./boot
主要放置開機相關檔案

3./dev
放置 device 裝置檔案，包話滑鼠鍵盤等

4./etc
主要放置系統檔案

5./home, 52./root
/home 主要是一般帳戶的家目錄，/root 為系統管理者的家目錄

6./lib, 53./lib64
主要為系統函式庫和核心函式庫，若是 64 位元則放在 /lib64。連結到 /usr/lib, /usr/lib64

7./proc
將記憶體內的資料做成檔案類型

8./sys
與 /proc 類似，但主要針對硬體相關參數

9./usr
/usr 全名為 unix software resource 縮寫，放置系統相關軟體、服務（注意不是 user 的縮寫喔！）

10./var
全名為 variable，放置一些變數或記錄檔

11./tmp
全名為 temporary，放置暫存檔案

12./media, 47./mnt
放置隨插即用的裝置慣用目錄， /mnt 為管理員/使用者手動掛上（mount）的目錄

13./opt
全名為 optional，通常為第三方廠商放置軟體處

14./run
系統進行服務軟體運作管理處

15./srv
通常是放置開發的服務（service），如：網站服務 www 等

16.ls：list，查看檔案及子目錄

17.pwd：print work directory，印出目前工作目錄

18.cd：change directory，移動進入資料夾

19.mkdir：make directory，創建新資料夾

20.cp：copy，複製檔案

21.mv：move (rename) files，移動檔案或是重新命名檔案

22.rm：remove file，刪除檔案

23.touch：用來更新已存在文件的 timestamp 時間戳記或是新增空白檔案

24.cat：將文件印出在終端機上

25.tail：顯示檔案最後幾行內容

26.more：將檔案一頁頁印在終端機上

27.file：檢查檔案類型

28.nano：在終端機編輯文字檔案

29.vim：在終端機編輯文字檔案

30.chmod：修改檔案權限

31.chown：修改檔案擁有者與群組

32.sudo：使用最高權限（superuser）執行指令

33.su：su 指令可以讓一般的 Linux 使用者輸入 root 密碼取得 root 權限(最高權限)

34.kill：根據 Process ID 指定要終止程式

35.killall：直接使用程式的名稱來指定要終止的程式

36.apt-get：套件管理工具

37.ping：網路檢測工具

38.traceroutes：檢查從你的電腦到網路另一端的主機是走的什麼路徑

39.nslookup：查詢 DNS 回應是否正常

40.man：查詢 Linux 線上手冊（man page）

41.find：查詢檔案

42.grep：文件字串搜尋工具

43.crontab：例行性工作排程

44.$0	目前的檔案檔名

45.$n	n 從 1 開始，代表第幾個參數	

46.$#	傳遞到程式或函式目前有幾個參數	

47.$*	傳遞到程式或函式所有參數	

48.$@	類似 $* 但是在被雙引號包含時有些許不同	

49.$?	上一個指令退出狀態或是函式的返回值	

50.$$	目前 process PID
