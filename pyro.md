# Pyro
Pyro Configure GPU Explosion
Pyroburstsource가 필요한 attribute들과 시뮬레이션에 필요한 파라미터들을 만들어준다, burn density temperature
Attribute Adjust Float : 스타트 프레임에 노이즈 + 랜더마이즈\

## Temperature
Buoyancy Scale : 상승 속도, 온도 기반

## Volume Rasterize Attributes
파티클을 볼륨으로 바꿔 준다. Pyro sim에 필요한 어트리뷰트들이 있어야 한다 density v temperature  
Pyro solver 안에 Volume source 넣는 방식으로 많이 쓴다. 

## Pyrosolver
Gasturbulance : 잘 모르겠다. 이 노드를 끼우면 시뮬레이션이 너무 느려진다
Gasdisturb : 연기의 자글자글한 디테일을 추가해준다.     

Time Scale : 시뮬레이션의 빠르기, 전체적인 타임을 루즈하게 만들어주는게 아니라 뭔가가 일어나는 속도를 빠르게 해줌   
Temp. Diffusion : 냉각 속도라고 하는데 Cooling rate가 냉각 속도인것 같고 이건 잘 모르겠다. 값이 높을수록 볼륨이 빨리 사라진다  쓰기 어려운것 같다   
Cooling Rate : 냉각 속도, 1이면 작동을 안하는데 0.99999999만 해도 시뮬레이션이 확 바뀐다. 정말 제일 쓰기 어려운 파라미터   
Viscosity : Velocity의 세기
Buoyancy : 온도 기반의 볼륨 상승속도   


Dissipation : 볼륨이 사라지는 속도, 적절하게 사용해야지 안그러면 중구난방이 된다   
Disturbance : 볼륨에 그레인을 먹이는 듯 한 느낌이다   
Shredding : 말 그대로 볼륨을 흩뿌리는 듯하게 만들어준다. swirl이랑 비슷한듯?   
Sharpening : 볼륨의 경계가 선명해지는데 거의 사용하지 않았다   
Turbulence : 노이즈를 넣는 파라미터다. 거의 사용하지 않았다   
Confinement : 정말 모르겠다 뭐 하는 파라미터지?

다 중요하겠지만 Cooling Rate, Buoyancy, Dissipation이 제일 중요한 것 같다 야매라 확실하진 않지만 쉐이핑에 있어서 저거 세개를 제일 많이 건드렸다\

꼭 temperature에 temperature을 넣어야 하는건 아니다. density를 temperature 값으로 쓸 수도 있다

만질 수 있는 파라미터들이 정말 많지만 위에 있는 파라미터들과 velocity, vector 변환만 이용해 작업을 했다. 이후 세부적으로 더 공부해야 할 듯


## Sparse
스파스는 볼륨을 조금 더 효율적으로 계산한다. 볼륨 박스 안의 모든 복셀을 계산하지 않고 필요한 복셀만 계산한다    
딱 하루 써보고 다시 원래 solver로 돌아와서 자세히는 모르지만 일단 sparse는 gpu로 동작한다. 시뮬레이션 타임에 조금 이득을 볼 수 있을 것 같다.
구동 방식이 달라서 시간을 너무 쓰게 될것 같아 버렸다.
