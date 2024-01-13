# StreamEditor
### 1번 : newyork 에 있던 ACCOUNTING 부서가 LA로 이전하였습니다. dept.txt를 수정하고 저장해주세요
`sed -i 's/NEWYORK/LA/' dept.txt`



### 2번 : emp.txt의 hiredate 칸의 포맷을 변경하려고 합니다. YYYY-mm-dd포맷을 yy/mm/dd로 바꾸고 그대로 저장해주세요
`sed -i -E 's/([0-9]{2})([0-9]{2})-([0-9]{2})-([0-9]{2})/\2\/\3\/\4/' emp.txt`


### 3번 :  emp.txt 5번 라인을 복사해서 새로 추가해 주세요. 
`sed '5s/.*/&\n&/' emp.txt >> emp.txt`

### 4번:  중복되는 줄을 삭제 해주세요 (줄지정 삭제가 아닌 중복되는 줄을 삭제해야 합니다)



### 5번: name.txt를 이용해서 맨마지막 부분에 새로운 데이터를 넣어주세요. (줄 바꿈을 먼저 진행하시고 이름, 나이, 성별을 넣어주세요)
![image](https://github.com/JiJuOh/StreamEditor/assets/81970382/d4597ea3-f66f-4076-9616-1b3ba64e1e5f)
- `sed -i '$ s/$/\n김춘삼 10     남자/' name.txt`
- ` sed -i '$ s/$/\n여기에 넣을 데이터 값~/' name.txt`

### 6번: txt 파일에 1번째 줄의 내용을 제외하고 입력된 데이터값만 읽고 싶다면 이를 출력하는 명령어를 입력해주세요
- `sed -e '2d' emp.txt`
- `sed -e 'id' emp.txt`: 첫번째줄을 제외하고 나머지 값만 출력하는 명령어

### 7번 txt 파일 내에 선을 표시하는 것들을 지우고자 합니다. 이때 -+를 만나면 이는 모두 삭제하고 |를 만날 경우엔 이를 공백값으로 대체해주세요.
- `sed -e 's/-//g; s/+//g s/|/ /g'`


### 8번 : 4번째 줄 위에서부터 17번째 줄 위까지 "--------------------------------------------------------------" 를 출력해줘
![Untitled](https://github.com/JiJuOh/StreamEditor/assets/112544126/87a590d4-5ce4-4906-ac27-02d431f7fde2)

정답 : sed '4, 17 i\--------------------------------------------------------------' emp.txt

### 9번 : 7번(Martin), 10번(Scott) 라인 삭제해줘
정답 : sed '7, 10d' emp.txt

### 10번 : 기존의 데이터 전체를 “우분투~~^^”로 변경하고 각 줄번호가 표시되게 해줘
![Untitled2 (1)](https://github.com/JiJuOh/StreamEditor/assets/112544126/8d6f9bf4-daad-430c-8afe-d059e05d41b3)

정답 : sed 'c\\우분투~~^^' emp.txt | cat -n
