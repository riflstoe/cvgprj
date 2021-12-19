# Pyro
Pyro Configure GPU Explosion
Pyroburstsource가 필요한 attribute들과 시뮬레이션에 필요한 파라미터들을 만들어준다, burn density temperature
Attribute Adjust Float : 스타트 프레임에 노이즈 + 랜더마이즈
## Temperature
Buoyancy Scale : 상승 속도, 온도 기반
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

다 중요하겠지만 Cooling Rate, Buoyancy, Dissipation이 제일 중요한 것 같다 야매라 확실하진 않지만 쉐이핑에 있어서 저거 세개를 제일 많이 건드렸다
