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
## Cross Vector 
정말 많이 써서 머리로는 이해하는데 말로 설명하려니 너무 어렵다.     
엄지 검지 중지를 쫙 펴서 설명하는 그 방법이 제일 이해하기 쉬울 것 같다.    
Cross Product는 두 벡터의 수직인 벡터를 구해준다. 이를 이용해 회전하거나, 밖으로 튕겨나가는 벡터값이 필요로 할때 정말 요긴하게 쓴다.    
외적이라고도 하는데, 수학을 잘 몰라서...    
Dot Product는 내적이다. 아직 나에게는 많이 쓰이지 않는 것 같다.

# Popcurveforce
몰랐다. 커브를 그대로 벡터로 사용할 수 있다. 방향이 중요하다 안된다면 reverse로 u를 뒤집어주자    

int myprim;
vector myuv;
xyzdist(1, @P, myprim, myuv);
vector direction = primuv(1, "N", myprim, myuv);
vector pos = primuv(1, "P", myprim, myuv);
float curveu = primuv(1, "curveu", myprim, myuv);
vector cd = primuv(1, "Cd", myprim, myuv);

if (curveu < //n ) removepoint(0, @ptnum);

vector suction = ( @P - pos ) * -1 * chf('suction');
suction *= chramp("suctionramp", curveu);
direction *= chf('speed');

v@force += suction + direction;

유튜브에서 찾은 popcurveforce보다 개선된 vex wrangle 코드다.   
포인트 어트리뷰트 U와 탄젠트에 노말이 들어가야 하는 것 같다.   
진짜 세세히 분석해보면 뜯어고칠 수 있을 것 같은데 더 연구해봐야 내가 수정해서 쓸 수 있을 것 같다. 지금은 크게 수정할 수 없다.


# VDB를 통한 노이즈
폴리곤에 VDB와 노이즈가 들어있는 Volume VOP을 사용하면 아주 신기하게 뱅글뱅글 도는 벡터를 만들어 낼 수 있다.    
사용 방법은 매우 다양한 것 같다. Trail을 사용해 정말 벡터를 뽑아내 특이한 움직임을 만들어 낼 수도 있고,   
정말 형태만 보자면 러그처럼 생겼다. 활용하자면 Fur 시뮬레이션에도 사용할 수 있지 않을까? 아예 해본적이 없어서 감은 오지 않는다. 안 될수도 있겠지   
공간에 놓고 그곳을 지나가는 벡터의 노이즈로도 쓸 수 있다.
이걸 활용한 이펙트 튜토리얼 영상이 조금 많이 있는것 같다. 간편하게 노이즈를 얻을 수 있어서 많이 쓰이는 기법인 듯

