# 2Ddigital

 1. Tracker
 
   3D 그래픽으로 만들어낸 또는 현실적으로 존재하지 않는 가상의 물체들을 실사 촬영에 의해 얻어진 영상물에 매칭 시키는 작업을 매치무빙(Match Moving)이라 하고
   
   촬영 된 영상의 카메라 움직임을 데이터화 시키는 도구가 Tracker이다. 
   
   Tracker를 통해 얻어 낸 데이터를 이용해 자연스러운 매치 무빙이 가능해 지는 것
   
   이 작업이 원할이 이루어지지 않는다면 사실감을 급격히 저하시키고 영상의 완성도를 저하시킬 수 있다.
   
   누크에서는 이를 Tracker 노드를 통해 사용할 수 있다.
   
   얻는 데이터의 양에 따라 2D tracking, 3D tracking으로 구별 될 수 있다.
   
   트래킹 작업 시 추출해 낸 Footage를 적용시키 전에 돌려보며 제대로 트래킹이 원하는 방향대로 가는지 확인 하는 작업을 거쳐야만 한다.
   
   (https://learn.foundry.com/nuke/content/tutorials/written_tutorials/tutorial2/tracking_stabilizing.html)
   
   
   ![tracker](https://user-images.githubusercontent.com/90597842/146631247-6f89a842-2918-4eb1-bb77-c54f71a4c1dd.png)
   

   1) One-Point Tracking
     
     - 한가지 포인트만 사용해 트래킹을 진행, 대상의 X축(수평)와 Y축(수직)만을 추적하게 된다. 이미지에 대해서 시점적인 변화는 적용할 수 없다. 
       주로 이미지를 카메라 움직임에 마춰 움직이거나 안정시키는데 사용 된다.
       
   2) Two-Point Tracking
       
     - 두개의 포인트를 사용해 트래킹을 진행, 두 개의 점의 X와 Y축을 추적한다.
       One point와 다른 점은 한 개의 Point를 추가로 사용해 이미지가 시계 방향이나 시계 반대 방향으로 돌아가는지를 Z축을 통해 나타낸다.
       대부분 Two-Point 트래킹 만으로도 자연스로운 Footage를 만들어 낼 수 있다.
     
   3) Three-Point Tracking
     
     - 3가지 포인트에서 X축과 Y축 정보를 추적한다. 
       Two-Point에서 얻을 수 있는 정보와 함깨 더욱 정교한 Z축 정보와 크기 변화 정보를 추출한다.
   ![tracker_3](https://user-images.githubusercontent.com/90597842/146633249-c4d11e59-5ae9-49e3-8e88-cb1f93d9dc8d.png)

   (https://learn.foundry.com/nuke/content/tutorials/written_tutorials/tutorial2/1_2_3_4_point_tracks.html)

   4) Planar Tracking 
   
    - 움직이지 않는 평면을 트래킹할 때 주로 사용된다. (벽이나 천장, 차의 옆면 등)
      평면이 아닌 사람의 얼굴을 트래킹 할 때도 사용할 수 있지만 효과적이진 않다.
      
      
    (https://learn.foundry.com/nuke/11.1/content/tutorials/planar_tracking.html)
    
   5) Camera tracking

  - 카메라 트래킹 노드는 2D상의 이미지에서 특징이 되는 포인트들을 지정하고 움직임을 추적해 촬영한 카메라의 무빙과 일치하는 
    가상의 카메라를 만들어 낼 수 있다.
    이를 통해 단순한 2D 이미지에 시점을 추가 하거나 3D오브젝트를 자연스럽게 합성 할 수 있다.
    
    ![cameratracker](https://user-images.githubusercontent.com/90597842/146678426-763f8a70-1dc2-4cc8-aea0-b45f44d4469c.png)
    
    ![CameraTracker_Tutorial1](https://user-images.githubusercontent.com/90597842/146678513-c1223d71-0ba8-4de8-88ec-eec0c268bd07.png)
     
    
     
      
      

