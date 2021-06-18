# scRNAseq_autism

 Centers for Disease Control and Prevention(CDC)의 보고에 따르면 자폐아 비율은 점점 증가하고 있고, 최신 보고에 따르면 54명 중 1명의 아이가 Autism spectrum disorder(ASD)로 규정된다[5]. 자폐인은 눈 맞추기를 피하거나 다른 친구 혹은 양육자에게 낮은 관심, 언어의 제한적인 표현, 규칙의 작은 변화에도 성질을 부리는 등의 특징을 가지고 있으며, 18개월 혹은 더 어릴 때에 의사 혹은 전문가의 경험적 판단에 의해 진단된다.
 ASD를 고칠 수 있는 치료법은 현재까지 밝혀진 바 없으나, 자폐 스펙트럼을 겪는 많은 사람들이 겪는 사회, 인지, 정서적 고통을 경감시키기 위한 대처 기술을 교육하고 사회에 적응 할 수 있도록 중재하는 것이 가능하다. 그러한 사회적 능력이 발달하는 어린 시기에 개인에게 맞는 사회적 훈련을 제공하는 것이 자폐인의 이후 삶의 적응과 발전에 커다란 영향을 끼치며, 적절하게 개입된 자폐인은 일반인과 다른 개성과 능력으로 사회에 이바지 하기도 한다. 따라서 가능한 발달적으로 이른 시기에 자폐 아동에 대한 정확한 진단이 중요하다고 전문가들은 강조한다.
 자폐의 특징 중 하나는 다른 정신적 질병과는 다르게 유전적으로 대를 이어 이어지는 경우가 매우 빈번한 것이다. 이는 유전적 소인의 발견이 중요함을 뜻하고 있으며, 유전학적 발견이 진단과 개입에 있어 주요한 진보를 이룰 수 있음을 시사한다. 개별 신경세포간의 상호작용에서 드러나는 질병인 만큼 single-cell RNA seq의 방법론을 적용하여 신경세포 단위의 변이를 살펴보는 것이 중요한 과제이며, 현재 수많은 연구진에 의해서 그러한 연구가 활발하게 이루어지고 있다.
 본 실습은 2019년에 Science에 게재된 Autism에 대한 snRNAseq 선행 연구의 데이터를 활용하여, single cell 연구의 기초 분석을 시도하였다[1]. 또한 2020년에 Cell에서 게재된 Large scale exome sequencing 연구에서 새롭게 밝히고 있는 사실을 접목하여 자폐 관련 주요 유전자의 발현의 차이를 뉴런 세포 타입에 대입하여 시각화 비교 관찰하였다[2]. 


Result

1. Clustering and Cell identification

 t-SNE 알고리즘을 사용하여 높은 유전자 발현량을 기준으로 clustering 후 2차원 공간에 나타낸 결과 Prefrontal cortex 와 Anterior cingulate cortex의 sing nuclei cell 데이터는 14개의 cell cluster로 구분되었다[1].

Fig 1. Cell clustering (t-SNE)

                                                                                      Fig 2. Expression of gene markers 
2. Hierarchical clustering

 ADS과 통제 집단에서 발현량에서 가장 차이가 큰 상위 유전자 20개를 비교하였을 때, 그 양상에 따라 cell-type이 계층화 되었다. Interneuron(IN-PV, IN-SST, IN-SV2C, IN-VIP)과 NRGN expressing neuron (Neu-NRGN-1, Neu-NRGN-2), Astrocytes (AST-FB, AST-PP), 그리고 Layer 2-6가 각각 비슷한 양상을 보이는 것으로 확인되었다.

Fig3. Ranked differential expressed gene

3. Visualization of marker gene in control and ASD

 또 다른 선행 연구에서 밝히고 있는 ASD의 주요한 유전자 발현을 umap으로 시각화 하여 비교하였을 때, FOXP1, CHD8, DYRK1A 등이 autism 집단과 control 집단에서 일부 뉴런 세포에 대한 발현량의 차이를 보였다[2]. AST-PP에서 SYNGAP1, CHD8, ADNP, DYRK1A의 발현량이 많았고, Oligodendrocyte 에서는 PTEN, ADNP, DYRK1A의 발현량이 적었다.


A.UMAP 

B. Gene expression of Control

C. Gene expression of Autism

Fig4. Expression of major gene (UMAP)

 위의 자료에서 통제집단과 비교하여 일부 유전자가 과발현, 또는 과소 발현으로 추정되는 세포 타입인 AST-PP는 원형질별아교세포이고, 또 다른 세포 Oligodendrocyte는 희소돌기신경교세포이다. 이 세포들은 신경아교세포의 하위 범주로써 선행 연구에서 Autism의 중요한 세포 타입으로 밝혀졌다[1]. 이 실습을 통해서는 다른 연구에서 자폐에서 주요한 유전자로 규명된 일부 유전자가 해당 세포 타입에서 발현량의 차이가 시각적으로 확인되었다[2].
 신경아교세포는 신경 계통의 세포 대다수(90%)를 차지하며, 신경세포는 신경연접에서 ATP를 방출함으로써 신경아교세포에 신경을 전달한다. 신경 아교세포는 신경의 발생, 활성, 형성, 손상으로부터 회복에 중요한 역할을 한다. 중추신경계통에서 볼 수 있는 신경아교세포 중 하나인 원형질별아교세포는 몇몇 돌기 끝이 발돌기의 형태로 혈관과 연결되어 있거나 연질막과 접하여 연질-아교막을 형성한다. 희소돌기신경세포는 신경 세포의 성장에 기여하는 것으로 알려져 있다.


discussion

 이 실습은 사전 연구를 확인하는 목적으로, 향후 연구의 통찰을 얻기 위하여 실시되었다. 주로 clustering을 통한 시각적인 비교 분석을 토대로 이루어졌으며, 이 실습을 통해서 새롭게 배우게 된 사실은 자폐에 있어 주요한 cell type으로 알려진 세포에서, 이와는 별개로 연구된 주요 유전자의 발현량 차이를 시각적으로 확인한 것이다.
 연구를 위해서 먼저 셀 타입간의 차이를 보이는 marker gene의 발현 양의 차이를 통해 cell clustering 및 annotation을 하였고, 다음으로는 Autism와 Control에서 큰 차이를 보이는 상위 20개의 gene의 발현 양상을 살펴 보고, 비슷한 변화를 보이는 cell-type 의 그룹 계층을 살펴보았다. 마지막으로는 선행 연구에서 주요한 유전자로 스크리닝 된 유전자들이 각각의 셀 타입에서 발현이 어떠한지 시각화 하여 살펴보았다.
 기존 연구의 clustering결과와 다소 차이가 있었는데, 이는 기존연구에서는 clustering을 할 때에 batch 간 effective를 줄이기 위하여 batch간 공변량이 낮은 principal component를 선택적으로 cut-off 했기 때문인 것으로 추측된다. 선행 연구에서 구별된 VIP interneuron과 SV2C interneuron cluster는 모두 Layer 2 에서 4 사이에 존재하는 interneuron으로 본 실습에서는 통합되어 clustering 되었다[3].
 본 연구에서 신경아교세포의 하위 클러스터에서 동일한 유전자(ADNP, DYRK1A)의 발현량이 증가하기도 하고(원형질별아교세포), 감소하기도 하였는데(희소돌기신경세포), 향후에는 이 유전자의 발현량의 차이가 어떤 영향이 있는지 추가 연구가 진행될 수 있을 것 같다. 이러한 결과는 bulk 연구에서는 밝혀낼 수 없는 싱글셀 연구의 유용한 점인 것 이기도 하다. 
 세대간 유전을 밝히는 논문을 참고하여, 자페의 기능적 특징을 나타내는 유전자와 부모세대에서 자식세대로 전달되는 때에 작용하는 유전자 간의 상관성을 연구를 하면 좋을 것 같다[4].


Method and Material

 본 실습은 python3.8, scanpy1.7.2를 사용하였고, scanpy tutorial을 적극 활용하여 이루어졌다. 실습시 작성된 코드는 (https://github.com/MovmntR/scRNAseq_autism)에서 확인 할 수 있으며, 연구에 활용된 데이터는 web browser ( https://cells.ucsc.edu/?ds=autism )에서 다운로드 받을 수 있다. 데이터는 두가지 종류가 있는데, rawMatrix의 경우 일부 데이터가 소실된 것으로 보여, 연구자들이 quality control, normalization, log transformation의 전처리 과정을 사전 진행한 exprMatrix를 주로 활용하였다. 자세한 내용은 코드에 포함되어 있다.


References

[1] Single-cell genomics identifies cell type-specific molecular changes in autism
[2] Large-Scale Exome Sequencing Study Implicates Both Developmental and Functional Changes in the Neurobiology of Autism
[3] A survey of human brain transcriptome diversity at the single cell level
[4] Functional relationships between recessive inherited genes and genes with de novo variants in autism spectrum disorder
[5] https://www.cdc.gov/ncbddd/autism/treatment.html
