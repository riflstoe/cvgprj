# RBD with Fluid
우선 Flat Tank로 시작했다. 파도를 만들기 위해 grid에 oceanwaves, oceanvaluate 노드를 이어준다.         

mountain에 Flow나 Periodic FLow를 적용시켜줘도 바다를 만들 수 있지만, ocean 계열 노드가 볼륨까지 만들어주기에 작업하기에는 조금 더 편리한것 같다.  

Volume VOP를 이용해 파도를 다듬어줬다. Vortex를 사용해 파도에 회전을 더 줄 수 있는것 같다. 이 부분은 어떤 원리인지 잘 모르겠다. 

Viscosity를 확인해가며 시뮬레이션을 해야 하는 것 같다. 점도와 파도 파티클을 조금만 수정하면 기름이 떠 있는 바다 등을 표현할 수 있을 것 같다.    

Flip Solver 옆에 Static Object로 암초를 하나 만들어 줬다. 파도가 암초에 부딛히는 시뮬레이션은 완성했다.          

암초를 RBD Fracture로 부수고 RBD 시뮬레이션을 통해 파도가 부딛혀 부서지는 암초를 만들려고 했는데,        

문제점 1. Voronoi나 RBD Fracture로 "부서진 암초" 를 어떻게 표현하는가?

          - ?
          
문제점 2. Static Object가 아니라면 제 자리에 있다가 부서졌을 때 부서지는 파츠들만 날아가도록 어떻게 시뮬레이션 하는가?

          - Gravity Force와 Velocity에 키값을 줘서 필요할 때 부서지도록 한다.
          
문제점 3. 날아가는 암초 조각들과 데브리스들과 파도가 상호작용을 어떻게 하게 하는가?

          - RBD 오브젝트를 Flip Solver랑 Merge 시켜서 확인


몇가지 문제점이 더 있겠지만, 10월 마지막주에는 이 부분들을 중점으로 연구해봐야 할것 같다.
