# Python 網路爬蟲

## Colab
- https://colab.research.google.com

## Anaconda
- https://www.anaconda.com/products/individual

## Selector Gadget
- https://chrome.google.com/webstore/detail/selectorgadget/mhjhnkcfbdhnjickkkdbjoemdmbfginb?hl=zh-TW

## Crome Driver
- https://chromedriver.chromium.org/

## Selenium 使用說明

先下載 Chromium (64 位元版)

- https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/814947/

請同仁下載chrome-win.zip (瀏覽器本體)

下載chromedriver_win32.zip (Driver) 

## Selenium Headers

```` 
options = webdriver.ChromeOptions()

# 添加UA
options.add_argument('user-agent="MQQBrowser/26 Mozilla/5.0 (Linux; U; Android 2.3.7; zh-cn; MB200 Build/GRJ22; CyanogenMod-7) AppleWebKit/533.1 (KHTML, like Gecko) Version/ 4.0 Mobile Safari/533.1"')

# 指定瀏覽器解析度
options.add_argument('window-size=1920x3000')

# Headless Mode
options.add_argument('--headless')  

# 加上這個屬性來規避bug
chrome_options.add_argument('--disable-gpu')

 # 隱藏滾動條, 應對一些特殊頁面
options.add_argument('--hide-scrollbars')

# 不加載圖片, 提升速度
options.add_argument('blink-settings=imagesEnabled=false')

# 瀏覽器不提供可視化頁面. linux下如果系統不支持可視化不加這條會啟動失敗
options.add_argument('--headless')

# 以最高權限運行
options.add_argument('--no-sandbox')

# 手動指定使用的瀏覽器位置
options.binary_location = r"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe"

#添加crx插件
option.add_extension('d:\crx\AdBlock_v2.17.crx')

# 禁用JavaScript
option.add_argument("--disable-javascript")

# 設置開發者模式啟動，該模式下webdriver屬性為正常值
options.add_experimental_option('excludeSwitches', ['enable-automation'])

# 禁用瀏覽器彈窗
prefs = {
    'profile.default_content_setting_values' : {
        'notifications' : 2
     }
}
options.add_experimental_option('prefs',prefs)


driver=webdriver.Chrome(chrome_options=chrome_options)

````

### 其他配置參數
````
–user-data-dir=”[PATH]”
# 指定用戶文件夾User Data路徑，可以把書籤這樣的用戶數據保存在系統分區以外的分區

　　–disk-cache-dir=”[PATH]“
# 指定緩存Cache路徑

　　–disk-cache-size=
# 指定Cache大小，單位Byte

　　–first run
# 重置到初始狀態，第一次運行

　　–incognito
# 隱身模式啟動

　　–disable-javascript
# 禁用Javascript

　　--omnibox-popup-count="num"
# 將地址欄彈出的提示菜單數量改為num個
--user-agent="xxxxxxxx"
# 修改HTTP請求頭部的Agent字符串，可以通過about:version頁面查看修改效果

　　--disable-plugins
# 禁止加載所有插件，可以增加速度。可以通過about:plugins頁面查看效果

　　--disable-javascript
# 禁用JavaScript，如果覺得速度慢在加上這個

　　--disable-java
# 禁用java

　　--start-maximized
# 啟動就最大化

　　--no-sandbox
# 取消沙盒模式

　　--single-process
# 單進程運行

　　--process-per-tab
# 每個標籤使用單獨進程

　　--process-per-site
# 每個站點使用單獨進程

　　--in-process-plugins
# 插件不啟用單獨進程

　　--disable-popup-blocking
# 禁用彈出攔截

　　--disable-plugins
# 禁用插件

　　--disable-images
# 禁用圖像

　　--incognito
# 啟動進入隱身模式
--enable-udd-profiles
# 啟用賬戶切換菜單

　　--proxy-pac-url
# 使用pac代理 [via 1/2]

　　--lang=zh-CN
# 設置語言為簡體中文

　　--disk-cache-dir
# 自定義緩存目錄

　　--disk-cache-size
# 自定義緩存最大值（單位byte）

　　--media-cache-size
# 自定義多媒體緩存最大值（單位byte）

　　--bookmark-menu
# 在工具 欄增加一個書籤按鈕

　　--enable-sync
# 啟用書籤同步


````

## Scroll Down
- driver.execute_script("window.scrollTo(0, document.body.scrollHeight);")

