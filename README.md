# plant_disease-dataset 實作
### 使用技能
建構深度學習神經網路 (numpy、Pytorch模組)
   
### 架構
1. 資料集：使用 Kaggles的  [New Plant Diseases Dataset](<https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset/data>)，其中有 38 種生病或健康植物資料集 (約 87,000 張 RGB 圖片)
2. 訓練資料和驗證資料：training / validation = 80 / 20
3. 測試資料：資料集test資料夾中照片 + 自行拍攝病害照片 (應只有Citrus和Tomato照片符合原訓練資料集的分類，其餘植物病蟲害不屬於原本的分類)
4. 目的：預測圖片中的植物所感染的病蟲害
5. 方法：使用預訓練模型(Resnet18)進行訓練
---
### 結果
1. 資料集中的test資料夾預測成果佳
2. 自行拍攝照片中的2張被準確預測  
   ![image](https://github.com/user-attachments/assets/05da3caf-923c-4a08-bdeb-52dbbe33fbe2)
   ![image](https://github.com/user-attachments/assets/16ebb6c6-cdc8-492b-97fc-edab88c17b90)

5. 自行拍攝照片中的16張被認為準確預測 (可能性90%以上) ，但標籤和預測結果不合，多半為：
   a. 相同的植物種類，但為不同的病害->照片的病害類似、不存在原本的分類中或複合感染
   
      ![image](https://github.com/user-attachments/assets/275c917e-5398-4d4d-8e7a-5bc478c6e1d4)
      ![image](https://github.com/user-attachments/assets/86aed123-435b-4417-b917-bf6626eb5988)
      ![image](https://github.com/user-attachments/assets/5f2b99af-7251-493e-bb9a-4493cba2a6ab)
      ![image](https://github.com/user-attachments/assets/80ad3232-6d31-42b3-b8d9-71df378ad7f6)
      ![image](https://github.com/user-attachments/assets/352711ff-4572-42c0-be65-5bf45ca5b25f)
      ![image](https://github.com/user-attachments/assets/c80c6529-9550-4fc5-a729-99765d0254e0)
      ![image](https://github.com/user-attachments/assets/7a322b6d-df2d-46a5-b021-2901aa085167)

   b.不同的植物種類病害->背景複雜或葉片扭曲或非典型
   
      ![image](https://github.com/user-attachments/assets/1454710d-7c00-4ca1-be28-1d05dc902b7a)
      ![image](https://github.com/user-attachments/assets/13d75204-be30-45fe-8c39-b4c1c0663765)
      ![image](https://github.com/user-attachments/assets/0e20cfb5-fece-427c-a61b-0db9815353b8)
      ![image](https://github.com/user-attachments/assets/57dda07a-8852-471f-9fe7-da5bc5ff5c20)
      ![image](https://github.com/user-attachments/assets/9f69177d-db66-4cf7-b401-2a72788d6d6c)
      ![image](https://github.com/user-attachments/assets/51223812-80f1-4d86-8b78-af00f8286cc3)
      ![image](https://github.com/user-attachments/assets/6c63e086-90cc-4d42-a633-1cdff609295c)
      ![image](https://github.com/user-attachments/assets/f481aa75-2eb3-48e0-99cd-f19ce97459a6)
      ![image](https://github.com/user-attachments/assets/7b14aa9b-5a8b-417c-8f3f-71c0e4c03eb5)
      ![image](https://github.com/user-attachments/assets/3004cc9e-1029-46c6-8e52-a3a1e7bba1c4)

   c. 果實的照片?
   
      ![image](https://github.com/user-attachments/assets/9978fe8b-68e8-4bdd-8e2c-7c70d98e5882)
   
### 結論與優化方向
  
   1. 該模型適用條件：非複合感染、背景乾淨之植物葉片特寫照片
   2. 直接使用田間照片在這個模型進行辨識目前不太可行
   3. 新增台灣常見的病害的進行訓練
   4. 新增不同的病害型態進行訓練，使模型可以辨識樣態不同但應為同類病蟲害
   5. 新增複雜背景的照片訓練/將照片前處理去除背景
