# plant_disease-dataset 實作
### 使用技能
建構深度學習神經網路 (numpy、Pytorch模組)
   
### 架構
1. 資料集：使用 Kaggles的  [New Plant Diseases Dataset](<https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset/data>)，其中有 38 種生病或健康植物資料集 (約 87,000 張 RGB 圖片)
2. 訓練資料和驗證資料：training / validation = 80 / 20
3. 測試資料：資料集test資料夾中 33 張照片 + 自行拍攝病害照片 31 張 (應只有一張符合原訓練資料集的分類)
4. 目的：預測圖片是否生病
5. 方法：使用預訓練模型修改參數進行訓練
---
### 結果與下一步
1. 資料集中的test資料夾預測成果佳
2. 自行拍攝照片中的1張被準確預測
  
   ![image](https://github.com/user-attachments/assets/05da3caf-923c-4a08-bdeb-52dbbe33fbe2)
4. 自行拍攝照片中的16張被認為準確預測 (可能性90%以上) ，但標籤和預測結果不合，多半為：
   
   a. 相同的植物種類，但為不同的病害->病害相似
   
      ![image](https://github.com/user-attachments/assets/275c917e-5398-4d4d-8e7a-5bc478c6e1d4)
      ![image](https://github.com/user-attachments/assets/86aed123-435b-4417-b917-bf6626eb5988)
      ![image](https://github.com/user-attachments/assets/5f2b99af-7251-493e-bb9a-4493cba2a6ab)
      ![image](https://github.com/user-attachments/assets/80ad3232-6d31-42b3-b8d9-71df378ad7f6)
      ![image](https://github.com/user-attachments/assets/352711ff-4572-42c0-be65-5bf45ca5b25f)
      ![image](https://github.com/user-attachments/assets/c80c6529-9550-4fc5-a729-99765d0254e0)

   b.不同的植物種類病害->背景複雜或葉片扭曲或非典型
   
      ![image](https://github.com/user-attachments/assets/1454710d-7c00-4ca1-be28-1d05dc902b7a)
      ![image](https://github.com/user-attachments/assets/13d75204-be30-45fe-8c39-b4c1c0663765)
      ![image](https://github.com/user-attachments/assets/0e20cfb5-fece-427c-a61b-0db9815353b8)
      ![image](https://github.com/user-attachments/assets/57dda07a-8852-471f-9fe7-da5bc5ff5c20)
      ![image](https://github.com/user-attachments/assets/9f69177d-db66-4cf7-b401-2a72788d6d6c)
      ![image](https://github.com/user-attachments/assets/51223812-80f1-4d86-8b78-af00f8286cc3)
      ![image](https://github.com/user-attachments/assets/6c63e086-90cc-4d42-a633-1cdff609295c)
      ![image](https://github.com/user-attachments/assets/f481aa75-2eb3-48e0-99cd-f19ce97459a6)


   c. 果實的照片?
   
      ![image](https://github.com/user-attachments/assets/9978fe8b-68e8-4bdd-8e2c-7c70d98e5882)
   
6. 優化方向
  
   a. 新增不同病害的進行訓練
   
   b. 新增不同的病害型態進行訓練
