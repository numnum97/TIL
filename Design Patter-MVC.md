# MVC 패턴

Design Pattern 중 하나로 Model, View, Controller의 약자 </br>
하나의 어플리케이션, 프로젝트를 구성할 때 그 구성요소가 이 세가지의 역할로 구분됨

![image](http://xecenter.com/xe/files/attach/images/19480/039/041/77bf7303fceccd154fc0117fd1c4bfed.png)
[출처:XESCHOOL]

위와 같이 user가 controller를 조작하면 controller는 model을 통해 데이터를 가져오고 그것을 바탕으로 view를 제어해 user에게 전달

### 각자의 역할

#### Model

- 사용자가 편집하길 원하는 모든 데이터를 갖고 있어야 함 </br>
ex) 화면에 네모박스를 표현한다면, 네모박스의 화면 위치 정보, 크기 정보 등을 갖고 있어야 함
- view나 controller에 대해 어떤 정보도 알지 말아야 함 </br>
ex) 데이터 변경이 일어났을 때 모델에서 화면 UI를 직접 수정할 수 있도록 view를 참조하는 값이 없어야 함 
-  변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야 함</br>
ex) 어떤 정보가 변경된다면, 누군가에게 그것을 전달하여 수신할 수 있느 처리 방법을 구현해야 함 

#### View

- model이 갖고 있는 정보를 따로 저장해서는 안됨 </br>
ex) 화면에 무언가를 표시하기 위해 model의 정보를 전달받게 되는데, 그것을 뷰 내부에 저장하면 안됨
- model이나 controller를 몰라야 함
ex) 데이터만 받고 화면에 표시함
- 변경이 일어나면 변경 통지에 대한 처리방법을 구현해야함

#### Controller

- model이나 view에 대해 알고 있어야 함
- model이나 view의 변경을 모니터링 해야함
ex) 얘가 model이나 view의 변경 통지를 받아 서로에게 통지해주는 역할

### why MVC?

- 우선 3가지로 나누어져서 각자의 역할에 집중을 하여 효율적인 처리가 가능함
- 그것으로 인해 유지보수성, 확장성, 대처 능력이 증가함
