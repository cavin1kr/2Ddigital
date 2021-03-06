# 2Ddigital

1. Digital
  물질-시스템 등의 상태를 이산적(離散的)인 숫자·문자 등의 신호로 표현하는 일. 순화어는 `숫자식'
  데이터를 '0', '1' 두가지 상태로 생성 저장
  컴퓨터, 노트북은 모든 자료를 디지털 방식으로 처리
  아날로그 자료 샘플을 디지털로 변환하는 과정을 샘플링이라고 함.
  
2. Color
  *photon(광자)
  *이산적이다(연속적이지 않다)
  
  
   -RGB
  빛의 3원색(Red, Green, Blue)의 합성어
  3가지 색을 혼합해 모든 색을 만들어낸다.
  더하면 더할수록 밝아지는 가산혼합이 특징
  
   -CMYK
  청록색, 자홍색, 노란색(Cyan, Magenta, Yellow)를 혼합해 색을 만들어낸다
  완전한 검정이 존재하지 않기 때문에 별도로 검은색을 추가해 4도로 색상을 표현한다.
  더하면 더할수록 어두워지는 감산혼합이 특징
  *(https://m.blog.naver.com/worms1000/221250487676)
  
   -Bit depth
  *색 깊이, 컬러 심도, 색심도
  비트맵 이미지나 비디오 프레임 버퍼에서 하나의 화소의 색을 지시하기 위해 사용되는 비트 수, 비트 숫자가 커질 수 록 사용할 수 있는 숫자의 수는 많아진다. 
  
   Color depth나 bit-depth는 같은 말이며 각 픽셀의 색 채널을 정의하기 위해 사용되는 비트의 수를 이야기 할 때 사용되는 용어
  (color channel - 컴퓨터는 컬러 표현에 필요한 신호를 분리해서 처리, 픽셀 하나마다 가진 신호의 세기는 다르지만 같은 범주에 속한 신호끼리는 같은 속성을 가지고 있음.
  그 종류별 신호 묶음을 channel이라고 함. color channel은 그 중에서 이미지가 사용하는 색상 모드에 따라 RGB가 될 수 도 있고 CMYK가 될 수 도 있음.
  - https://phominator.tistory.com/34)
  
   대부분의 RGB 환경에서는 각 Color Channel에 256개의 shade(a mixture with black, which increases darkenss(https://en.wikipedia.org/wiki/Tint,_shade_and_tone)가 존재 함.
  256이라는 숫자는 2의 8승이다. 이것은 각 RGB채널이 256개의 shade를 가지고 있고 256*256*256, 16,777,216개의 색상을 8비트 RGB시스템에서 가지고 있다는 것을 의미함.
  비트 숫자가 커질 수 록 사용할 수 있는 숫자의 수는 많아진다. 
   예를 들어 8비트 안 에서는 1600만가지의 색상을 사용할 수 있지만 10비트 시스템에선 1024*1024*1024, 1,073,741,824가지, 8비트의 64배에 해당하는 색상을 사용 가능. 
   
   결과적으로 Color depth가 높으면 높을 수 록 내가 보는 색을 더 잘 보여주게 된다.
   (https://www.datavideo.com/eu/article/412/what-are-8-bit-10-bit-12-bit-4-4-4-4-2-2-and-4-2-00)
   
   -Alpha
  
  알파값은 색이 얼마나 불투명(Opaque)한지 나타내는 채널이다. 
  
  예를 들어 #8921F2 -> rgb(137, 33, 242)는 보라색이다. 아래 예시에 두개의 상자가 있다. 왼쪽 위에 있는 상자와 오른쪽 아래에 있는 상자는 서로 같은 색을 가지고 있지만
  오른쪽 상자는 알파 채널이 0.5로 설정되어 있다. 덕분에 우리는 오른쪽 상자 너머에 있는 텍스트를 볼 수 있게 된다.
  (https://developer.mozilla.org/en-US/docs/Glossary/Alpha)
  
![ALPHA_EXAPMLE](https://user-images.githubusercontent.com/90597842/137617089-a73f79ed-aa6a-4f33-aae4-371fb5c049e5.png)
  
  또 알파채널은 선택영역을 만들어 이미지의 선택영역을 정밀하게 수정할 수 있는 기능도 가지고 있다.
  알파채널은 흰색과 검은색으로 이루어지는데, 힌색으로 된 부분을 수정할 수 있고 검은색으로 이루어진 부분은 수정할 수 없다
  흰색 -> 검은색의 단계로 표현되는 shades는 모드 256개, 알파 채널은 흰색과 검은색, shade컬러의 256단계로 선택영역을 설정할 수 있기 때문에 정밀한 선택이 가능
  이렇게 여러개의 알파채널을 만든 후 흰색의 농도를 조절해 선택영역을 더하거나 빼면서 영역을 만든 후 최종적으로 RGB 색상 채널에 효과를 적용 함.
  알파채널의 흰 색 부분은 마스크 래이어와 같은 개념.
  (http://egloos.zum.com/knyatom/v/1458411)
  
3. Color space
  - 색 공간, Color space는 우리가 보는 색들이 어떻게 표현되는 지를 수치적으로 표현하는 방법. 
  
  ![color_space](https://user-images.githubusercontent.com/90597842/137617255-fb830f3b-7b6c-4d29-b685-74749456590c.png)
  
  - Gamut
  Color gamut(색역)은 사용하는 장치가 보여주거나 만들어 낼 수 있는 색상의 범위 이다. 보통 장치에서 사용되는 컬러 모델에 따라 Chromaticity diagram(색도도)에 삼각형으로 표현된다.
  ![color-gamut](https://user-images.githubusercontent.com/90597842/137618529-156e5469-3060-4dde-92f2-fe672cf0e72a.jpg) 
  *다른 색역들이 색도도에서 표현되는 예시
  
  가장 큰 특징은 Color gamut은 2차원이 아닌 3차원이라는 것이다. 그 이유는 우리가 색에 대해 이야기 할 때 세 가지 요소로 이야기 하게 된다.
  색상(hue), 명도(lightness), 채도(saturation), 각 각 3차원 축에서 x,y,z로 표현 되 는 것. 하지만 3차원 그래프로 표현해서 나타내는 것은 굉징히 어려움.
  그래서 2차원 그래프에서 gamut값을 나타내는 것.
  
  *NTSC : 가장 일반적으로 알려져있는 색역값. 하지만 기준값은 아님
   sRGB : IEC에서 1999년에 만들어진 색역값의 표준. 표준으로 사용되는 이유는 color reproduction(색 재현율)을 보다 쉽게 나타낼 수 있었기 때문
   (https://www.benq.com/en-me/knowledge-center/knowledge/color-gamut-monitor.html)
   
   -ACES
    ACES? The Acadmey Color Encoding System의 약자. 많은 스튜디오에서 현재 사용하고 있는 color space. 표현할 수 있는 색상의 범위가 넓음.
    현재 UHD 화질의 영상까지도 커버 가능 함. 
    
    (https://docs.arnoldrenderer.com/display/A5KTN/ACES+Workflow)
