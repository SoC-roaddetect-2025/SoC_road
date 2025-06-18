<html>
<body>
<!--StartFragment--><h2 data-start="117" data-end="126">✨ 專案簡介</h2>
<p data-start="128" data-end="201">本專案致力於在嵌入式平台上實現「道路與車道線即時辨識系統」，結合影像處理技術與 FPGA 硬體加速，透過 SoC 架構實現高效影像分析與即時輸出。</p>
<blockquote data-start="203" data-end="267">
<p data-start="205" data-end="267">開發人員：<br data-start="210" data-end="213">
F113112131 歐育典<br data-start="229" data-end="232">
C109112107 康佳元<br data-start="248" data-end="251">
F113112134 余立凱</p>
</blockquote>  

![Image](https://github.com/user-attachments/assets/8f13ad3b-c245-415a-9497-94f375e37e13)  
## PL流程圖  
![Image](https://github.com/user-attachments/assets/eae98649-a56f-4dcf-8ed3-3978db0cb545)  
## 完整流程圖   
![Image](https://github.com/user-attachments/assets/4d364a5e-9898-4ff8-9d3d-923f04a5b29c)  

<hr data-start="269" data-end="272">
<h2 data-start="274" data-end="284">⚙️ 系統功能</h2>
<ul data-start="286" data-end="425">
<li data-start="286" data-end="346">
<p data-start="288" data-end="299">從輸入影像中即時辨識：</p>
<ul data-start="302" data-end="346">
<li data-start="302" data-end="314">
<p data-start="304" data-end="314">車道線 / 道路區域</p>
</li>
<li data-start="317" data-end="346">
<p data-start="319" data-end="346">使用 Sobel 邊緣檢測與其他影像處理演算法提取特徵</p>
</li>
</ul>
</li>
<li data-start="347" data-end="364">
<p data-start="349" data-end="364">顯示辨識結果於 VGA 顯示器</p>
</li>
<li data-start="365" data-end="425">
<p data-start="367" data-end="425">利用 PS (Processing System) 與 PL (Programmable Logic) 協作加速處理</p>
</li>
</ul>
<hr data-start="427" data-end="430">
<h2 data-start="432" data-end="442">🧱 系統架構</h2>
<h3 data-start="444" data-end="455">🔩 硬體平台</h3>
<ul data-start="457" data-end="523">
<li data-start="457" data-end="475">
<p data-start="459" data-end="475">SoC 架構：Zynq FPGA</p>
</li>
<li data-start="476" data-end="496">
<p data-start="478" data-end="496">控制器：INTEL i7-13600</p>
</li>
<li data-start="497" data-end="523">
<p data-start="499" data-end="523">PL 模組開發語言：Verilog / VHDL</p>
</li>
</ul>
<h3 data-start="525" data-end="540">🔧 自製 IP 模組</h3>
<ul data-start="542" data-end="616">
<li data-start="542" data-end="552">
<p data-start="544" data-end="552">FSM 控制模組</p>
</li>
<li data-start="553" data-end="567">
<p data-start="555" data-end="567">Sobel 邊緣偵測模組</p>
</li>
<li data-start="568" data-end="583">
<p data-start="570" data-end="583">Gaussian 模糊模組</p>
</li>
<li data-start="584" data-end="591">
<p data-start="586" data-end="591">二值化模組</p>
</li>
<li data-start="592" data-end="606">
<p data-start="594" data-end="606">WaterShed 模組</p>
</li>
<li data-start="607" data-end="616">
<p data-start="609" data-end="616">車道線檢測模組</p>
</li>
</ul>
<hr data-start="618" data-end="621">
<h2 data-start="623" data-end="633">🔌 介面規格</h2>
<ul data-start="635" data-end="820">
<li data-start="635" data-end="699">
<p data-start="637" data-end="647"><strong data-start="637" data-end="647">記憶體介面：</strong></p>
<ul data-start="650" data-end="699">
<li data-start="650" data-end="674">
<p data-start="652" data-end="674">DDR Memory + DMA 傳遞影像幀</p>
</li>
<li data-start="677" data-end="699">
<p data-start="679" data-end="699">AXI 接口連接 PS ⇄ PL 資料流</p>
</li>
</ul>
</li>
<li data-start="701" data-end="745">
<p data-start="703" data-end="712"><strong data-start="703" data-end="712">輸出介面：</strong></p>
<ul data-start="715" data-end="745">
<li data-start="715" data-end="725">
<p data-start="717" data-end="725">VGA 顯示結果</p>
</li>
<li data-start="728" data-end="745">
<p data-start="730" data-end="745">可擴充 HDMI / UART</p>
</li>
</ul>
</li>
<li data-start="747" data-end="820">
<p data-start="749" data-end="758"><strong data-start="749" data-end="758">控制介面：</strong></p>
<ul data-start="761" data-end="820">
<li data-start="761" data-end="784">
<p data-start="763" data-end="784">由 PS 發送控制信號至 FSM 控制模組</p>
</li>
<li data-start="787" data-end="820">
<p data-start="789" data-end="820">使用 AXI-Lite 設定 Sobel 閥值、遮罩區域等參數</p>
</li>
</ul>
</li>
</ul>
<hr data-start="822" data-end="825">
<h2 data-start="827" data-end="837">📐 技術規格</h2>
<div class="_tableContainer_16hzy_1"><div tabindex="-1" class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse">  

項目 | 描述
-- | --  
Sobel | 採用 3x3 kernel，需建立 2 行 Linebuffer，輸入有效時才寫入資料，透過 enable 啟動膨脹處理。  
Gaussian | 同樣採 3x3 kernel，處理方式與 Sobel 類似。  
二值化 | 採用固定或自訂閥值轉換灰階為黑白。  
WaterShed | 用於分割影像區域，強化邊界。  

<div class="sticky end-(--thread-content-margin) h-0 self-end select-none"><div class="absolute end-0 flex items-end"><span class="" data-state="closed"><button class="bg-token-bg-primary hover:bg-token-bg-tertiary text-token-text-secondary my-1 rounded-sm p-1 transition-opacity group-[:not(:hover):not(:focus-within)]:pointer-events-none group-[:not(:hover):not(:focus-within)]:opacity-0"><svg width="20" height="20" viewBox="0 0 20 20" fill="currentColor" xmlns="http://www.w3.org/2000/svg" class="icon-md-heavy"><path d="M12.668 10.667C12.668 9.95614 12.668 9.46258 12.6367 9.0791C12.6137 8.79732 12.5758 8.60761 12.5244 8.46387L12.4688 8.33399C12.3148 8.03193 12.0803 7.77885 11.793 7.60254L11.666 7.53125C11.508 7.45087 11.2963 7.39395 10.9209 7.36328C10.5374 7.33197 10.0439 7.33203 9.33301 7.33203H6.5C5.78896 7.33203 5.29563 7.33195 4.91211 7.36328C4.63016 7.38632 4.44065 7.42413 4.29688 7.47559L4.16699 7.53125C3.86488 7.68518 3.61186 7.9196 3.43555 8.20703L3.36524 8.33399C3.28478 8.49198 3.22795 8.70352 3.19727 9.0791C3.16595 9.46259 3.16504 9.95611 3.16504 10.667V13.5C3.16504 14.211 3.16593 14.7044 3.19727 15.0879C3.22797 15.4636 3.28473 15.675 3.36524 15.833L3.43555 15.959C3.61186 16.2466 3.86474 16.4807 4.16699 16.6348L4.29688 16.6914C4.44063 16.7428 4.63025 16.7797 4.91211 16.8027C5.29563 16.8341 5.78896 16.835 6.5 16.835H9.33301C10.0439 16.835 10.5374 16.8341 10.9209 16.8027C11.2965 16.772 11.508 16.7152 11.666 16.6348L11.793 16.5645C12.0804 16.3881 12.3148 16.1351 12.4688 15.833L12.5244 15.7031C12.5759 15.5594 12.6137 15.3698 12.6367 15.0879C12.6681 14.7044 12.668 14.211 12.668 13.5V10.667ZM13.998 12.665C14.4528 12.6634 14.8011 12.6602 15.0879 12.6367C15.4635 12.606 15.675 12.5492 15.833 12.4688L15.959 12.3975C16.2466 12.2211 16.4808 11.9682 16.6348 11.666L16.6914 11.5361C16.7428 11.3924 16.7797 11.2026 16.8027 10.9209C16.8341 10.5374 16.835 10.0439 16.835 9.33301V6.5C16.835 5.78896 16.8341 5.29563 16.8027 4.91211C16.7797 4.63025 16.7428 4.44063 16.6914 4.29688L16.6348 4.16699C16.4807 3.86474 16.2466 3.61186 15.959 3.43555L15.833 3.36524C15.675 3.28473 15.4636 3.22797 15.0879 3.19727C14.7044 3.16593 14.211 3.16504 13.5 3.16504H10.667C9.9561 3.16504 9.46259 3.16595 9.0791 3.19727C8.79739 3.22028 8.6076 3.2572 8.46387 3.30859L8.33399 3.36524C8.03176 3.51923 7.77886 3.75343 7.60254 4.04102L7.53125 4.16699C7.4508 4.32498 7.39397 4.53655 7.36328 4.91211C7.33985 5.19893 7.33562 5.54719 7.33399 6.00195H9.33301C10.022 6.00195 10.5791 6.00131 11.0293 6.03809C11.4873 6.07551 11.8937 6.15471 12.2705 6.34668L12.4883 6.46875C12.984 6.7728 13.3878 7.20854 13.6533 7.72949L13.7197 7.87207C13.8642 8.20859 13.9292 8.56974 13.9619 8.9707C13.9987 9.42092 13.998 9.97799 13.998 10.667V12.665ZM18.165 9.33301C18.165 10.022 18.1657 10.5791 18.1289 11.0293C18.0961 11.4302 18.0311 11.7914 17.8867 12.1279L17.8203 12.2705C17.5549 12.7914 17.1509 13.2272 16.6553 13.5313L16.4365 13.6533C16.0599 13.8452 15.6541 13.9245 15.1963 13.9619C14.8593 13.9895 14.4624 13.9935 13.9951 13.9951C13.9935 14.4624 13.9895 14.8593 13.9619 15.1963C13.9292 15.597 13.864 15.9576 13.7197 16.2939L13.6533 16.4365C13.3878 16.9576 12.9841 17.3941 12.4883 17.6982L12.2705 17.8203C11.8937 18.0123 11.4873 18.0915 11.0293 18.1289C10.5791 18.1657 10.022 18.165 9.33301 18.165H6.5C5.81091 18.165 5.25395 18.1657 4.80371 18.1289C4.40306 18.0962 4.04235 18.031 3.70606 17.8867L3.56348 17.8203C3.04244 17.5548 2.60585 17.151 2.30176 16.6553L2.17969 16.4365C1.98788 16.0599 1.90851 15.6541 1.87109 15.1963C1.83431 14.746 1.83496 14.1891 1.83496 13.5V10.667C1.83496 9.978 1.83432 9.42091 1.87109 8.9707C1.90851 8.5127 1.98772 8.10625 2.17969 7.72949L2.30176 7.51172C2.60586 7.0159 3.04236 6.6122 3.56348 6.34668L3.70606 6.28027C4.04237 6.136 4.40303 6.07083 4.80371 6.03809C5.14051 6.01057 5.53708 6.00551 6.00391 6.00391C6.00551 5.53708 6.01057 5.14051 6.03809 4.80371C6.0755 4.34588 6.15483 3.94012 6.34668 3.56348L6.46875 3.34473C6.77282 2.84912 7.20856 2.44514 7.72949 2.17969L7.87207 2.11328C8.20855 1.96886 8.56979 1.90385 8.9707 1.87109C9.42091 1.83432 9.978 1.83496 10.667 1.83496H13.5C14.1891 1.83496 14.746 1.83431 15.1963 1.87109C15.6541 1.90851 16.0599 1.98788 16.4365 2.17969L16.6553 2.30176C17.151 2.60585 17.5548 3.04244 17.8203 3.56348L17.8867 3.70606C18.031 4.04235 18.0962 4.40306 18.1289 4.80371C18.1657 5.25395 18.165 5.81091 18.165 6.5V9.33301Z"></path></svg></button></span></div></div></div></div>
<hr data-start="1047" data-end="1050">
<h2 data-start="1052" data-end="1062">🚧 系統限制</h2>
<ul data-start="1064" data-end="1211">
<li data-start="1064" data-end="1103">
<p data-start="1066" data-end="1103"><strong data-start="1066" data-end="1075">解析度限制</strong>：建議使用 VGA 或較低解析度以節省 FPGA 資源。</p>
</li>
<li data-start="1104" data-end="1146">
<p data-start="1106" data-end="1146"><strong data-start="1106" data-end="1115">模型複雜度</strong>：複雜 CNN 模型無法全數部署於 PL，須依賴 PS 合作。</p>
</li>
<li data-start="1147" data-end="1176">
<p data-start="1149" data-end="1176"><strong data-start="1149" data-end="1157">光照影響</strong>：在低光、強光或水滴遮擋下易產生誤判。</p>
</li>
<li data-start="1177" data-end="1211">
<p data-start="1179" data-end="1211"><strong data-start="1179" data-end="1187">同步處理</strong>：影像處理模組需與 DDR 資料流進行精準同步。</p>
</li>
</ul>
<hr data-start="1213" data-end="1216">
<h2 data-start="1218" data-end="1228">🧪 測試驗證</h2>
<h3 data-start="1230" data-end="1240">✅ 單元測試</h3>
<ul data-start="1242" data-end="1296">
<li data-start="1242" data-end="1296">
<p data-start="1244" data-end="1296">Sobel / Gaussian / Binary / WaterShed 模組均以影像幀進行功能驗證。</p>
</li>
</ul>
<h3 data-start="1298" data-end="1308">✅ 整體驗收</h3>
<ul data-start="1310" data-end="1350">
<li data-start="1310" data-end="1350">
<p data-start="1312" data-end="1350">透過 PL 處理邏輯 + PS 控制介面組合測試全流程辨識與 VGA 輸出。</p>
</li>
</ul>
<!--EndFragment-->
</body>
</html>
📌 未來展望
將處理模組升級為支持高階模型（如 CNN）

提升低光環境下的辨識穩定度

增加即時通訊能力（如 Ethernet 視訊串流輸出）

<html>
<body>
<!--StartFragment--><h2 data-start="66" data-end="93">
---


