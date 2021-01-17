리눅스 명령어로 자동 배포 쉘 스크립트를 아무 생각없이(?) 짜면서 몰랐던 명령어들을 정리해볼건데 먼저 **kill**이다.

- kill은 프로세스에 시그널을 보내는 명령어로 default 값은 SIGTERM이다. (프로그램 정상 종료)
- `kill -l`로 시그널 목록을 확인할 수 있음. </br>
![kill](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=http%3A%2F%2Fcfile23.uf.tistory.com%2Fimage%2F220FA846565B0BA82E1D6F) </br>
[출처: Crocus님의 블로그](https://www.crocus.co.kr/245)

- kill을 사용할 때에는 `kill -(보낼 시그널) PID` 이렇게 사용한다. 이때 보낼 시그널은 숫자로 지정해도 되고 SIG를 빼고 이름을 넣어도 된다.
```
kill -TERM PID
or
kill -15 PID
```
- 프로그램을 종료 시킬때는 강제 종료시키는 SIGKILL은 권장되지 않는다!
- 둘의 차이를 잘 설명해준 짤 </br>
![sigterm sigkill](https://i.imgur.com/Zk0uRIb.png?1)


[출처: https://opensourceinside.blogspot.com/2015/06/how-to-kill-linux-processesunresponsive.html](https://opensourceinside.blogspot.com/2015/06/how-to-kill-linux-processesunresponsive.html)

