
# 변수에 대해

c에서 변수를 저장할 떄

```C
int x = 3;
```

이런식으로 저장한다. 이때, x라는 값은 사람이 쓰기 편한 이름이다.

이는 컴파일러를 지나고 실행파일이 되는 시점에서 없어지는 이름이다.

컴파일러가 이 x라는 이름과 나중에 매치될 주소값을 테이블로 가지고 있다가, 실행파일로 만들 때 알맞는 가상주소로 맵핑해준다.

이 과정에서, x라는 사람이 지어준 이름은 사라지게 된다.

  

# 포인터

포인터는 위에서 언급된 주소값을 유저(프로그래머)단에서 사용하기 위해 만들어졌다

```C
int x=3;
int* p = &x;
```

이런식으로 보면, p라는 값은 x라는 이름의 변수가 실행파일에서 가질 주소를 가지고 있다.

이 주소는 보통의 데스크탑형 운형체제에서 가상메모리의 주소값을 준다. (실제 메모리 주소를 주는 경우도 있긴 할 것이다. 가상주소가 없는 운영체제라면 실제 메모리 주소를 줄 듯 하다.)

컴파일 이후 이 x가 가지는 메모리에서의 주소는 & 를 사용하면 알 수 있다. (위의 &x 이런 식으로)

이 값을 코딩하는 과정에서 사용하고 싶은 경우, 포인터라는 키워드(자료형 옆에 별붙이는 모양 ex] int* )를 이용하여 사용자 단에서 편한 이름으로 저장하여 사용이 가능하다.

  

## 배열

대표적이면서 쉬운 포인터 연산이 배열 연산이다.

배열은 선언시에 인접한 메모리에 연속적으로 할당되므로 포인터를 통해 주소값으로 내부를 볼 수 있다.

```C

#include  <iostream>

int  main(){
int x[5];
int *xp = x;
*xp = 1;
*(xp + 1) = 2;
cout << x[0] << x[1] << endl;
}

```

  

이중 배열도 주소값을 보면 어떤식으로 메모리가 할당되는지 볼 수 있다.

```C
int  y[3][3];
y[0][0] = 1;
cout << "y : " << &y[0][4] << " and "<< &y[1] <<endl;
```

위의 결과값을 보면 int 만큼(4byte)의 차이가 나는 것을 볼 수 있고 이를 통해

012,012,012 이런식의 메모리할당이 된 것을 알 수 있다.

  
  

## 이중 포인터

```C
int a = 5;
int* p = &a;
int** pp = &p;
```

포인터 변수의 주소값을 어딘가 저장하려면 포인터의 포인터 변수를 선언해야 한다. 그러지 않을 경우 컴파일러 단에서 에러가 난다.

이중 포인터인 pp를 예로 들면

>    pp   : p의 주소값을 가짐
>   *pp  : p의 실제 값을 가짐. 여기서는 a의 주소값을 가짐.
>  **pp  : p의 실제값이 주소값이므로, 이 값을 다시 찾아가면 a의 원래 값이 나온다. 여기서는 5이다.

  

비슷한 방식으로 겹겹으로 포인터를 사용이 가능하다.

  

쓰기 편하게 나름의 해석을 붙이면, *을 선언시에 타입 뒤에 붙는건 나중에 그 변수에 몇번 *이 사용가능한 지를 보여주는 것이고,

변수 앞에 *을 붙이는 것은 지금 변수값이 주소값이고 그 주소값에 저장된 값을 확인하겠다 라는 뜻으로 이해하면 좋을 듯 하다.
