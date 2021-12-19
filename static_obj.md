# Static - Collision
## RBD Solver
Division Size : Collision object의 복셀 크기를 조절한다. 잘못 조절하면 빈틈이 생겨 그 부분으로 무언가가 새게 될 것이다. 특히 볼륨   
Offset Surface : Collision object 겉표면의 크기를 조절한다. Scale 보다는 Extrude 느낌인듯   

## Bullet Data
Geometry Representation : Collision object의 형태를 만드는 방식이다.   
Convex hull이 디폴트고, 조금 더 디테일이 살아있는 형태를 원한다면 Concave 사용하면 될 것 같다.     
대신 concave는 엄청나게 무겁다.   
Sphere, Box 등은 이들보다 가볍지만 형태가 좋지 않다. 정말 가벼운 Collision 필요로 할 때 쓸 수 있을 듯.


Collision은 정말 별거 아니라 생각해서 RBD를 처음 할 때는 무시했었다. 그런데 볼륨으로 넘어와보니 생각보다 신경쓸게 매우 많다. 반성한다.
