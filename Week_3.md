1. Gamma
 
 - 전자기기 화면에 입력되는 신호의 밝기와 화면상에 나타나는 영상의 휘도 간 상관 관계를 결정하는 수치
 
 - 휘도(Luminance) : 일정한 면적을 통과 해 일정한 입체각으로 들어오는 빛의 양, 면에서 반사되는 빛의 양
                     
                     휘도 란 무엇인가..
                     
                     '광도(Luminous intensity) : 광원에서 특정한 방향으로 방사되는 광량', 단위는 cd(칸델라)
                     
                     1cd = 촛불 한개의 광량(1.067cd), 이 때 일정한 범위를 가진 광원 또는 빛의 반사체 표면의 밝기를 '휘도'라고 한다.(단위 면적 당 광원의 세기)
                     
                     디스플레이에서의 휘도 - 기기의 밝은 정도를 나타내는 개념
                     
                     화면을 밝게 표시할수록 야외의 태양 빛 아래에서도 화면을 또렷하게 볼 수 있기 때문에 디스플레이 성능의 중요한 지표, cd/m2, nit
                     
                     (https://news.samsungdisplay.com/17806/)
 
                     
 - 회색도(Gray Scale) : 이미지의 각 Pixel의 밝기를 표현한 수치 (0 ~ 255)
 
 (정리하면 아래 그래프에서 사용되는 휘도와 GrayScale의 의미는 GrayScale은 내가 보고자 하는 이미지 자체가 가지고 있는 픽셀들의 밝기이고 휘도는 그 이미지를 보여주고 있는
 디스플레이의 밝은 정도를 뜻 함)
 
 #감마커브
 ![GammaCurve](https://user-images.githubusercontent.com/90597842/143674785-60a4d02b-b13b-49a6-8017-e71d3518e0e0.jpg)
 
 감마값이 1인 경우는 입력과 출력의 밝기가 같지만
 (내가 보려는 이미지와 보여주는 기기의 밝기 값이 같으니까)
 1보다 크면 화면이 좀 더 어둡게 표현 되고
 (1일 경우 그레이가 128일 때, 휘도가 50%여야 하는데 낮으면 휘도가 낮아짐)
 반대로 1보다 작으면 밝게 표현된다.
 (위 반대)
 
 (감마 값 1 예시 = Grayscale(128), 휘도 50%)
 
 인간의 눈은 어두운 곳의 차이는 잘 구분하지만 밝은 곳의 차이는 잘 구분하지 못하기 때문에 감마값을 1로 설정해 놓는다면 높은 Gray로 갈수록 밝은 색을 잘 구분하지 못하게 된다.
 (감마 값을 높이면 높은 Gray에서 휘도가 낮아 구분하기 쉬운 어두운 곳이 됨)
 
 이를 보안하기 위해 인간의 눈에 최적화시킨 감마값을 적용하는데 NTSC 표준 감마값인 2.2
 
 중,저계조 영역에서 보여지는 휘도의 변화가 크지 않지만 고계조로 갈수록 Gray Level에 따른 휘도의 변화가 큼
 
 -계조(Gradation) : 색의 농도 차이를 단계별로 표현한 것(가장 밝은 부분부터 가장 어두운 부분까지를 표현할 수 있는 단계)
 
 (https://news.samsungdisplay.com/1869/)
 
2. Lineal Wokrflow

 - 선형 워크플로우, 리니어 워트 플로우
 
 - 모든 그래픽 작업이 선형 색 공간(Linear Color Space)에서 이루어지는 방식
 
 ![color_linear_color_space](https://user-images.githubusercontent.com/90597842/143681968-3eca3d03-cd2b-4257-a5c3-ed21591585ec.png)

 - 사람의 눈은 어두운 색에 민감하기 때문에 감마 색 공간(Gamma Color Space)의 그라데이션이 더 자연스럽다고 느낌
   하지만 실제 수학적으로 정확한 그라데이션은 선형 색 공간(Linear Color Space)의 그라데이션이다.
   
   (색이 밝아지는 정도를 어두운 색이 있는 왼쪽 부분에서 더 민감하게 느끼기 때문에 선형 색 공간 그라데이션은 검정색이 급격하게 밝아지는 것 같은 느낌이 드는 것)
   
   그래서 선형 색 공간의 그라데이션을 감마 색 공간의 그라데이션 처럼 우리 눈에 자연스럽게 만드려면 감마값을 조정해야한다.
   
   위의 감마 항목에서 언급한 것 처럼 감마값을 올리거나 내리는 것을 감마값을 보정한다 하고 보정한 이미지는 감마 색 공간에 있다고 한다
   
   감마값을 보정하지 않은, 원래의 색 분포 그대로의 이미지는 선형 색 공간에 있다고 한다.
   
   (https://kyoungwhankim.github.io/ko/blog/color_linearworkflow/)
   
  - 
  
 3. Premultiplication

    premult의 원리는 이미지에 있는 RGB값에 알파 값을 곱해 보여주는 방식이다.

    아래 이미지에 로토로 만들어진 알파값을 복사해 오면 이미지가 가지고 있는 알파값에 적용이 되지만 실제 RGB 이미지에는 적용 되지 않은 것을 알 수 있다.

![doge_nopre](https://user-images.githubusercontent.com/90597842/144406458-63e68da7-d3c5-49af-9a93-e30249dcd70a.png)
![doge_alpha_nopre](https://user-images.githubusercontent.com/90597842/144406518-120eb097-602e-4adf-a99f-66561385ffda.png)

   이 경우 Premult 노드를 사용해주면 알파 값이 RGB값에 곱해져 이미지에 반영된다.
   
![doge_premult](https://user-images.githubusercontent.com/90597842/144407012-ac07cabb-903a-4469-8072-e7fff5c01a90.png)

  (https://jamesprattvfx.com/blog/nuke-premult-unpremult)

  
    
  
  - black ( 0, 0, 0) alpha 1
  - white ( 1, 1, 1) alpha 0
 
 
 
 
 
