# Disintegration
Mountain으로 노이즈를 준 sphere를 내가 이펙팅하고싶은 geo에 지나가게 해주고, Attribute transfer을 이용해 Cd값을 건져내면 폴리곤이 사라지는 경계면을 만들 수 있다
이런 방식으로 blast나 delete를 쓴 것이 아닌 랜덤하게 노이즈가 낀 절단면을 만들어 낼 수가 있는데, 아마 다양하게 활용할 수 있을 것 같다.
파티클이 점점 사라지게 하고 싶어서 Wrangle을 통해 알파값을 파라미터로 만드는 시도를 몇 번 했었는데 이번에는 실패했다. 
VEX가 잘못된건지 노드가 꼬인건지 잘 모르겠다. 
f@Alpha = chramp("AlphaByAge", f@nage);
@age는 파티클이 생성된 시간이다
@nage는 @age를 @life로 나눈 값이다. @nage를 쓰는 것이 파티클을 페이드아웃 시키는데에 어울리는 것 같다.
@Cd나 @Alpha 이외에도 다양한 어트리뷰트를 램프 파라미터로 조절해서 쓸 수 있을 것 같다.

# Vector
## Add / Subtract Vector
(0, 1, 0) + (1, 4, 5) = (1, 5, 5)
(0, 1, 0) - (0, 6, 1) = (0, -5, -1)
벡터를 더하거나 뺄 때는 벡터의 x, y, z를 그대로 합연산하면 된다. 노말에 적용해 벡터로 변환할 때에도 매우 용이하다.
## Dot / Cross Vector
