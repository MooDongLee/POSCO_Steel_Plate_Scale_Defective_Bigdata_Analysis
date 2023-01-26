# SCALE 불량 요인 분석 및 개선안 도출 (분류 모델)
 
**- 진행 기간 : 2022.08.01 ~ 2022.08.26 (빅데이터 분석 과정)**   
**- 프로젝트 내용 : SCALE 불량 요인 분석 및 개선안 도출 보고서.pdf 참고**   
**- Source Code : SCALE 불량 요인 분석 및 개선안 도출.ipynb**    
**- 분석 Data : SCALE 불량.csv 사용**     
**- 핵심 인자: Scale_핵심인자(중요 설명변수) 정리 템플릿.xlsx 참고**     
**- 분석 상세: Normalizer 적용을 통한 Heatmap 출력, Random Forest, Gradient Boosting, 로지스틱 회귀분석, KNN, SVM, Decision Tree를 통하여, 압연온도(ROLLING_TEMP_T5), 가열로 균열대 시간(FUR_SZ_TEMP), 고열의 스케일 브레이커(HSB) 조절을 통해 Scale 불량을 줄이는 데이터 기반의 제조 정책이 필요**   

<p align="center">
  <img src="https://user-images.githubusercontent.com/47058935/214865019-ad7fe74c-6dab-43d5-8224-d67fd22f2dae.PNG" alt="1" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214865220-7600d876-273d-46ca-b067-00226677a946.PNG" alt="2" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214865357-6c5cb633-c143-434f-ae33-fa443013c290.PNG" alt="3" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214865896-c7a9c351-595b-45d2-9aaa-011fcc12a332.PNG" alt="4" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214866005-7fc01f46-819f-49d7-8823-ec4df6d268dd.PNG" alt="5" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214866284-82e4153d-349a-494d-8153-30014cb9c3d4.PNG" alt="6" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214866408-0c4d42d2-ea28-4331-9a0c-8a362f4b1d81.PNG" alt="7" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214866691-992c537b-746b-4804-bbfc-17890ac42c10.PNG" alt="8" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214866855-4f0dacd5-b2c8-4daf-b933-9a11fc6fe3ff.PNG" alt="9" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214866977-9b2417a2-e0e3-4802-a3b1-760ab13308b2.PNG" alt="10" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214867177-66e2fe97-c62d-4262-a80c-9eb9618f3805.PNG" alt="11" width="number" />  
  <img src="https://user-images.githubusercontent.com/47058935/214867386-c876a2cb-acf7-4d6c-b755-f2ea48bc6b5f.PNG" alt="12" width="number" />  
  <img src="https://user-images.githubusercontent.com/47058935/214867506-8f16525a-8bed-4f34-b6f6-92d4ee89ec44.PNG" alt="13" width="number" />  
  <img src="https://user-images.githubusercontent.com/47058935/214867655-a71507fd-4ff0-4d03-9a87-3179d18da56a.PNG" alt="14" width="number" />  
  <img src="https://user-images.githubusercontent.com/47058935/214867762-9f1b072b-6491-4bc4-a6b6-2efd5f61cb9e.PNG" alt="15" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214867873-eaf27f79-c5b8-40c5-9fae-c4a7c2dca765.PNG" alt="16" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214867979-d3961224-ed6d-4638-b3e0-6805895caeb4.PNG" alt="17" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214868144-080471fd-9e6a-47f2-8694-b259488e425d.PNG" alt="18" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214868303-25c48c61-c4d0-4f7c-a87e-551a16b8766e.PNG" alt="19" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214868436-16b3b944-5b10-4541-870a-ec26a1f4b7ab.PNG" alt="20" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214868607-bacc9199-b6f4-4b8a-850d-505a38ef242a.PNG" alt="21" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214868859-a6bd5197-2989-4df5-afa0-25e95acfc184.PNG" alt="22" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214869046-411b6b08-1279-4653-8fe0-2140f05177a1.PNG" alt="23" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214869202-085f17a9-9ef9-419f-89e7-334742a68ebf.PNG" alt="24" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214869332-e6cf5447-bc4d-4e9e-87b3-4c46b576e2be.PNG" alt="25" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214869445-86d95b0f-67a3-4027-b401-8bca40ace95a.PNG" alt="26" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214869637-f6071efb-474d-4ca7-96e7-3df8603296c2.PNG" alt="27" width="number" />
  <img src="https://user-images.githubusercontent.com/47058935/214869741-b66dfb1e-ae1b-4f1d-a720-d0a0ce92e8b6.PNG" alt="28" width="number" />
</p>
