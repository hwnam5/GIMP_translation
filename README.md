# FOSS-2024-1-final
## GIMP 번역 프로젝트 진행 보고서 :memo:
## Other files
- `HOWTO.md`에는 빌드하는 과정을 정리하였습니다.
- `HELPME.md`에는 빌드하는 과정에서 가장 자주 마주치는 에러들과 대처 방법에 대해서 정리하였습니다.
- `ko.po`는 원 번역본 파일이고, `ko_ajou.po`는 저희 팀에서 제안하는 번역 내용이 담긴 번역본 파일입니다.
## gimp란?
김프는 그림을 편집하는 데 쓰이는 free software이다. 1995년 스펜서 킴벨과 피터 마티스가 제작하기 시작하였으며, GNU GPL 라이선스를 따른다. 
## 활동 내역 :clipboard:
[notion : https://www.notion.so/Open-sw-team-cd366ae2dfc2407aa1addf2606838bcd?pvs=4]
### 노션에 정리한 내역
1. 빌드하는 방법 정리
    - "sudo apt install"을 통해 필요한 환경 만들기
    - git 에서 소스 클론 (git clone)
    - babl, gegl, gimp 빌드 (by meson or ninja)
2. 번역 필요한 부분 (영어 => 한글일
    - 영어로 되어있는 부분 최대한 한글로 번역
3. 오번역 수정 (한글 => 한글)
    - 실제 기능과 맞지 않게 번역된 부분 수정  
        ex. 이미지 평탄화 => 배경 레이어에 합치기  
자세한 번역 및 수정 내용과 빌드 과정은 위에 올라와 있는 노션에 정리
## 팀 명단 :busts_in_silhouette:
|  이름(학번)        |   기여 내용     |
| ------------------|:---------------:|
| 강전찬(202020711)  | 미번역된 부분 번역      |
| 공종혁(202020709)  | 어색한 번역 수정      |
| 남현원(202020820)  | 미번역된 부분 번역|
| 한동엽(202020778)  | GIMP 빌드, 어색한 번역 수정, 번역 최종 검수 |

## 팀프로젝트 일정 :calendar:
5월 31일 : 주제 선정  
6월 2일 : 빌드 시도 및 빌드 환경 설정  
6월 6일 : 빌드 성공 및 빌드 방법 정리  
6월 7일 ~ 6월 16일 : GIMP 번역 및 오번역 수정  
6월 21일 ~ 6월 23일 : 보고서 및 최종 제출 자료 작성 + 빌드 과정 영상 촬영  

## 과제 선정 동기 :bulb:
 우리 팀원들은 2024년도 1학기에 영상처리 강의를 수강하면서 처음 포토샵을 접하게 되었다. 정말 좋은 프로그램인것은 부정할 수 없으나 유료라는 
 점이 큰 걸림돌로 다가왔다. 이때 gimp라는 프로그램을 접하게 되었는데 기본적인 필터를 사용하는데 있어서 포토샵과 비교해도 뒤쳐지지 않을정도로 
 성능이 좋아서 자주 애용하게 되었다. 하지만 세부 기능에 대한 이름과 설명이 실제 기능과 맵핑이 되지 않는 영어로 되어 있거나 번역기에 돌린 내용 그대로 복사 붙여넣기한 오번역 부분이 많이 보였었다. 그래서 이러한 이유로 어려움을 겪은 경험이 적지 않게 있었다. 그렇기에 김프의 번역에 도움을 주어 우리와 같은 문제점을 겪은 다른 학생들에게 더 효율적으로 김프를 사용할 수 있게 하고 다른 포토샵 기능을 사용하는 학생들에게 포토샵뿐만 아니라 김프라는 좋은 프로그램이 있다는 것을 알리고 싶고 접근성을 쉽게 하고 싶어서 팀원들과 GIMP 번역 팀프로젝트를 과제로 선정하게 되었다. 

## 과제 진행 과정에 대한 총평 :thinking:
 공종혁 :이번 프로젝트에서 어색한 번역 수정 부분을 담당했다. 처음에는 되게 가벼운 마음으로 프로젝트에 참여하였다. 단순히 이상하게 번역된 한국어를
 그럴싸하게 바꾸고 영어는 번역기에 돌리면 될 줄 알았다. 하지만 프로그램을 build 하는 부분부터 문제가 발생했다. 빌드 해야하는 부분은 babl, gegl, gimp였는데 어느 하나 쉬운 게 없었다. mac을 사용 중인 필자는 babl 빌드시에 ninja라는 친구가 mac과 충돌을 일으켜 어느 방법을
사용해도 환경을 구축할 수 없었다. 내 문제라고 생각하고 며칠을 빌드에 달라붙었지만 결국 실패하였고, 나중에 다른 교수님의 지나가는 말씀으로 mac은 gimp를 일반적인 방법으로 빌드는 불가능하다고 하셨다.
 어쩔 수 없이 빌드는 포기하고, 번역을 시작했다. 이전 번역한 사람이 단순히 번역기에 돌려서 올려놓은 메뉴들은 간단하게 바꾸었다. 하지만 문제는 영어를 한국어로 바꾸기 어려운 고유명사들이었다. 좀 더 좋은 명칭이 있을까 같이 번역 수정을 담당한 한동엽 팀원과 머리를 싸매고 고민했다. 예를 들어 "지능적으로 잘라내기"는 누가봐도 잘못된 번역임을 알 수 있다. 하지만 "이미지 평탄화"같은 경우에는 code에 들어가서 원형 영어를 찾아서 gimp 탬플릿에 들어가 해당 명칭을 검색해서 기능을 찾아봐야한다. 또한 변경된 내용을 수정할때는 파일에 내용들이 ui와 같은 카테고리로 이루어져 있지 않아서 찾는데 고생을 했다.
꽤 어려운 여정이었지만 다른 사람들이 이 번역을 보며 조금 더 편하게 사용했으면 좋겠다고 생각했고, 분명 빌드하다 어려운 점이 많을 거 같아서 팀원들과 영상도 만들자고 건의하였다. 다들 흔쾌히 동의해 주었고 만들어진 영상을 보니 간단히 따라 할 수 있을 거 같아서 뿌듯하였다.

 강전찬 : 이번 번역 프로젝트를 수행하면서 영어로 표현된 부분을 번역하는 역할을 맡았다. 번역을 하는데, 최대한 한글로 바꾸려고 시도를 해 보았다. 하지만 아무리 생각해도 영어 발음이 아닌 순수 한글로 바꾸었을 때 더 어색한 부분이 많았다. 예를 들어 'motion blur' 같은 부분이다. 이를 '움직임 흐림처리'라고 해석할 수도 있었지만 이럴 경우 오히려 사용자가 이용하는 데에 불편함을 더 발생시킬 수 있다고 판단했다. 이 부분 같은 경우 영어 발음 그대로 작성함으로써 오히려 익숙한 영어 발음을 그대로 유지했다. 또한 마우스를 오버했을 때 설명이 영어로 된 부분이 많이 있어 이 부분 또한 번역을 진행했다. 전문적인 단어가 많이 포함되어 있어 그 만큼 번역에 어려움이 있었지만, 그 단어의 의미와 해당 기능의 역할을 검색 해보면서 새로운 개념과 기술을 배우는 기회가 됐다.
 번역보다 어려웠던 과정은 gimp를 build하는 과정이었다. git에서 clone하여 build를 시도했지만 사소한 에러가 build 과정에 계속 발생함에 따라 build에 실패하게 됐다. 다행히 팀원 중 성공한 팀원이 있어 build하는 과정을 영상으로 남길 수 있었다. 
 이번 프로젝트를 통해 gimp 한글 버전을 사용하는 사용자들이 좀 더 편하게 gimp를 이용할 수 있는 계기가 됐으면 하는 바람에 이번 프로젝트를 진행했다. 물론 진행 과정에서 많은 어려움들이 있었지만 유용한 결과물을 도출해 낼 수 있어서 좋았다. 이번 프로젝트로 많은 사람들이 편리하게 gimp를 이용할 수 있는 기회가 됐으면 좋겠다.

 남현원 : 김프 번역 프로젝트를 맡았지만, 번역하기 전 빌드할 때 부터 많은 문제가 있었다. 먼저 빌드하는 과정은 git에서 소스를 클론하여 gimp 빌드하는데 필요한 babl, gegl, gimp파일을 meson이나 ninja를 통해 빌드하고 실행을 하면된다. 이렇게 보면 빌드해보이는 과정이 단순해보일 수 있지만 하지만 아니였다. 빌드하는데 요구하는 리눅스 환경이 많았고, 요구하는 환경을 sudo apt install을 통해 가져오더라도 파일 안에서 파일 경로가 잘 못 되어 있는경우도 있어서 vim을 통해 install한 파일의 코드를 수정하는 경우도 있었다. 처음에 번역프로젝트를 동기들과 맡기로 했었을 때, 김프 오픈 소스 프로그램의 전반적인 이해와 번역이 주된 작업요소일 줄 알았는데 그것을 수정할 수 있는 환경을 만들어주는 빌드 작업도 중요하고 쉽지 않다는 것을 느낄 수 있었다. 그래서 이러한 느낀점을 통해 동기들과 같이 다른 사람들이 김프에 대한 추가 번역이나 수정을 하고 싶을 때 빌드를 쉽게 할 수 있게 해주기 위한 가이드를 만들어주기로 하였다. 김프는 오픈 소스 그래픽 편집 프로그램으로 이미지 편집이나 그래픽 디자인이나 여러 편집 기능이 풍부한 만큼 많은 메뉴와 설정하는 부분이 있다. 하지만 김프에서 한국어로 변역하기엔 양이 많고 전문적인 용어가 많다 보니 번역이 안되어 있는 부분도 많았고 그냥 번역기에 돌려버린 부자연스러운 번역본이 많았다. 이러면 아무리 좋은 기능이 있고 여러 세부적인 설정이 있다고 해도 잘 못된 해석으로 기능을 사용하지 못한다면 의미가 없을 것 같다는 생각이 들었다. 물론 나는 영어로 되어 있는 부분을 한국어로 번역하는 부분을 담당하였지만 해석되어있는 부분을 보고 무슨 기능인지 알 수 없는 부분이 있었다. 그러다가 커서를 올렸을 때 자세한 설명이 뜨는 기능이 GIMP에 있었는데 번역된 내용과 영어로 되어 있는 기능의 자세한 설명이 매핑이 잘 되어 있지 않은 부분이 있었다. 이를 통해 영어로 되어 있는 자세한 부분까지 한글로 해석하여 한국인들이 기능을 자세히 이해하고 사용할 수 있게 해주고 싶었다. 이 프로젝트를 하면서 과장된 생각일 수 있지만 이러한 번역 활동이 다른 한국 GIMP를 사용하는 편집 프로그래머들의 GIMP의 기능을 더 자세히 이해하여 가지고 있는 능력이 크게 발현되었으면 하는 생각을 하니 단순히 오픈소스입문 수업의 과제로 느껴지지 않고, 책임감을 가지고 하게 되었다.

 한동엽 : 이번 학기에 <영상처리> 수업을 수강하면서 배웠던 여러 가지 필터들이 실제로 프로그램에서 적용되는 것을 보는 것이 신기했다. 그래서 이번에 GIMP를 번역하는 주제를
 <영상처리> 수업을 같이 수강하는 팀원들과 함께 하자고 제안하게 되었다. GIMP를 빌드하는 데 과정을 파악하는 것이 어려웠고, 제대로 된 튜토리얼이 제공되지 않아 하나하나 바닥부터 해야만 했다.
 그 과정에서 meson 커뮤니티에 직접 이슈를 남겨 개발자로부터 직접 [답변](https://github.com/mesonbuild/meson/discussions/13261#discussioncomment-9572300)을 들어보기도 했고, git과 bash 명령어 뿐 아니라
 오픈소스 커뮤니티 활동에 대해 전반적으로 많은 경험을 얻는 귀중한 시간이었다. GIMP documentation과 Digital Image Processing (Gonzalez, Woods) 책 등을 참고하면서 기존 번역의 부자연스러움을 최대한 없애려고 했고,
 기존 번역에서 직역한 부분들 대신 이미 상용화된 용어들에 대해서는 그대로 차용해서 혼동이 없도록 했다. 위에서 팀원들이 설명한 사례들 말고도 많은 부분에서, 영상처리와 관련된 배경지식이 없는 상태로 직역하거나 오역한 부분이 많았다. 이것을 최대한 줄이고 더 많은 사람들이 공통적으로 이해하고 사용하는 용어로 최대한 바꿔주고자 했다. 이번 프로젝트를 계기로 이후에 더 많은 사람들이 GIMP에 관심을 가져 주었으면 좋겠다.