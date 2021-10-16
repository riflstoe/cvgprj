# Disintegration
Mountain으로 노이즈를 준 sphere를 내가 이펙팅하고싶은 geo에 지나가게 해주고, Attribute transfer을 이용해 Cd값을 건져내면 폴리곤이 사라지는 경계면을 만들 수 있다
이런 방식으로 blast나 delete를 쓴 것이 아닌 랜덤하게 노이즈가 낀 절단면을 만들어 낼 수가 있는데, 아마 다양하게 활용할 수 있을 것 같다.
파티클이 점점 사라지게 하고 싶어서 Wrangle을 통해 알파값을 파라미터로 만드는 시도를 몇 번 했었는데 이번에는 실패했다. 
VEX가 잘못된건지 노드가 꼬인건지 잘 모르겠다.
f@Alpha = 
