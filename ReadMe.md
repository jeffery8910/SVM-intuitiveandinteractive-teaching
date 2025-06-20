# **互動式支持向量機 (SVM) 直觀理解工具**

這是一個簡單的互動式網頁應用程式，旨在幫助使用者直觀地理解支持向量機 (SVM) 的核心概念，特別是它如何在二維空間中找到最大邊界超平面來分類數據點。

\[插入一張應用程式截圖或 GIF 動畫，展示其運作方式\]

## **專案概覽**

支持向量機是一種強大的監督式學習演算法，常用於分類和迴歸任務。這個工具透過視覺化的方式，讓使用者可以：

* 在畫布上放置不同類別的數據點。  
* 即時計算並顯示 SVM 的決策邊界 (超平面) 和邊界 (margin)。  
* 觀察支持向量如何影響超平面的位置。

## **✨ 主要功能**

* **互動式數據點放置**：使用者可以選擇類別 (例如：類別 0 \- 藍色，類別 1 \- 紅色)，並在畫布上點擊以新增數據點。  
* **SVM 計算與視覺化**：  
  * 點擊「計算 SVM」按鈕，程式會計算並繪製：  
    * **超平面 (Hyperplane)**：一條綠色的實線，代表最佳的分類線。  
    * **邊界 (Margins)**：兩條綠色的虛線，平行於超平面，代表到最近數據點的距離。  
    * **支持向量 (Support Vectors)**：最靠近邊界的數據點，會以黃色邊框突顯。  
* **即時狀態更新**：顯示目前選擇的類別、計算結果或錯誤訊息。  
* **邊界寬度顯示**：計算並顯示找到的最大邊界寬度。  
* **清除功能**：一鍵清除畫布上的所有數據點和計算結果。  
* **響應式設計**：畫布會根據瀏覽器視窗大小自動調整。  
* **概念解釋**：側邊欄提供 SVM、超平面、邊界和支持向量的基本文字說明。

## **🚀 如何使用**

1. **開啟** index.html：在您的網頁瀏覽器中開啟 index.html 檔案。  
2. **選擇類別**：  
   * 點擊「添加類別 0 (藍)」按鈕以選擇類別 0。  
   * 點擊「添加類別 1 (紅)」按鈕以選擇類別 1。  
   * 目前選擇的類別按鈕會有藍色外框。  
3. **放置數據點**：在畫布區域點擊，即可放置所選類別的數據點。  
4. **計算 SVM**：  
   * 當您放置了足夠的數據點 (建議每個類別至少有一個點，且數據是線性可分的) 後，點擊「計算 SVM」按鈕。  
   * 畫布上將會顯示分類的超平面、邊界線，並且支持向量會被突顯。  
   * 狀態訊息區域會更新計算結果，邊界資訊區域會顯示最大邊界寬度。  
5. **清除畫布**：點擊「清除畫布」按鈕可以移除所有數據點和已計算的 SVM 結果，讓您可以重新開始。  
6. **觀察與學習**：  
   * 嘗試不同的數據點分佈，觀察超平面和邊界如何變化。  
   * 注意哪些點成為支持向量，以及它們如何「支撐」超平面。  
   * 閱讀側邊欄的說明，加深對 SVM 概念的理解。

## **🛠️ 技術細節**

* **前端**：純 HTML, CSS (使用 Tailwind CSS 框架進行樣式設計) 和 JavaScript。  
* **SVM 演算法**：  
  * 此工具實現了一個**簡化的 SVM 演算法**，主要用於教學和直觀演示。  
  * 它通過迭代所有可能的「類別0點」與「類別1點」的組合，將它們視為潛在的支持向量。  
  * 對於每一對潛在的支持向量，它計算它們之間的距離 (潛在的邊界寬度)。  
  * 然後，它檢查由這對點定義的「街道」(即邊界內的區域) 是否能正確分隔所有其他數據點。  
  * 演算法會選擇能夠正確分離所有點且具有最大邊界寬度的點對作為最終的支持向量，並由此確定超平面。  
  * **注意**：這個簡化演算法主要適用於線性可分的二維數據，並且可能無法處理更複雜或非線性可分的情況。它也沒有實現軟邊界 (soft margin) 或核技巧 (kernel trick)。

## **🔮 未來可能的改進**

* 引入更複雜的 SVM 演算法 (例如，使用二次規劃求解器)。  
* 支援軟邊界 (處理非線性可分數據)。  
* 加入核技巧 (例如，高斯核) 以處理更複雜的數據分佈。  
* 允許使用者拖動數據點。  
* 增加更多視覺化選項或參數調整。

希望這個工具能幫助您更好地理解支持向量機！
