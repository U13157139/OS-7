README
1. 通訊邏輯說明 (誰收誰發)
根據實驗結果（Serial Monitor 數據分析）：
發送端 (Transmitter) - COM4：
負責接收外部輸入的原始指令（如 {"count": 2}）。
執行 Decode 任務進行 JSON 解析，並將結果分發。
接收端 (Receiver) - COM3：
同步顯示解析後的結果（JSON Count is 0x2）。
作為指令執行的受控端，同步更新狀態。
2. 操作 SOP
專案導入：解壓縮 RPIPicoFreeRTOSCourse8.zip，以 VS Code 開啟 SerialCmds。
編譯燒錄：執行 Compile，並透過 BOOTSEL + RST 組合鍵將 .uf2 檔燒錄至 Pico。
功能驗證：
確認藍色 LED 與 LED 組正常閃爍。
開啟 Serial Monitor，透過發送端輸入 JSON 指令。
觀察接收端是否同步更新 JSON Count 數值。
