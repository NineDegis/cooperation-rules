## 요구사항

#### 확정

-   여기서 배제한다고 명시하지 않은 이상 omz가 갖고 있는 기능은 100% 구현한다.
-   omz는 100% shell 스크립트다. Python이나 C를 이용해서 캐싱 등의 고오급 기술로 성능을 향상시키자.
-   omz를 설치하면 바로 테마가 적용되지 않고 환경설정을 해줘야된다. 설치 직후 바로 테마가 적용되게 하자.
-   omz의 테마를 적용시킨 상태에서 깃을 쓰면 브랜치 정보 등 여러가지가 깔끔하게 잘 나온다. 이를 게릿 등 다른 개발도구에도 적용시키자.
    -   포함시킬 개발도구 목록
        -   gerrit
        -   Trello
    -   각 개발도구가 연동/자동화 되게끔
        -   트렐로 오토네이밍
            -   설정파일이 있어서 수정 가능하게끔
        -   게릿 - 트렐로 연동
            -   게릿에서 코드리뷰 통과시 트렐로에서 Progress 항목으로부터 Done 항목으로 이동

#### 미확정

-   ?





## 일정

#### 1학기 중간고사 전 (1term)

-   협업규칙 설정
-   oh-my-zsh 코드 분석
-   언어~~, 라이브러리, 프레임워크~~ 결정
-   개략적인 설계
-   개발 환경 설정
-   상기 모든 사항에 대한 팀원간 이해도 확인

#### 1학기 기말고사 전 (2term)

-   개발
    -   시행착오
    -   다른 언어로의 수정 (불필요한 기능은 삭제)
-   문서 업데이트

#### 여름방학 (3term)

-   개발
    -   새로운 feature 추가
-   문서 업데이트

#### 2학기 중간고사 전 (4term)

-   계획이란 원래 뜻대로 되지 않기 마련이다.

#### 마무리 (5term)

-   시각화
-   retrospect





## 컨벤션



### 커뮤니케이션

-   1term 이후로는 팀원을 챙기지 않는 것을 원칙으로 한다. 2term부터는 지식의 공유는 100% 문서와 협업도구를 통해 이루어지고 이를 읽지 않는 것은 본인의 책임이다. 공유된 사항을 모두 읽고도 여전히 모르는 것은 직접 물어보거나 공부한다.
-   다른 라이브러리나 모듈을 사용할 때는 반드시 간략한 설명과 사용법을 문서로 남겨야 한다.
-   커밋 전에 업데이트할 문서가 없는지 회고한다.



### Cooperation Rules

-   현재 당신이 보고 있는 바로 이 문서!


-   추가 또는 수정하고 싶은 내용이 있으면 깃헙에 이슈로 남긴다.
-   이 문서를 직접 수정하는 것은 전세진 한 명으로 제한하는 것을 원칙으로 한다.



### README.md

-   이슈 하나를 완료할 때마다 



### Git

#### 커밋메시지

-   영어로 작성한다.


-   다음의 형식을 따른다.

    ```
    Commit message title

    Details will be here.
    If you have more details, you can write them in multi lines.
    ```

```
*   첫 줄에는 제목을 적는다.
    *   첫 글자는 대문자로 적는다.
    *   마침표를 찍지 않는다.
    *   50자 이하로 적는다.  // 보통 Git에서 열어준 vim이 알아서 50자 넘어가면 경고를 표시한다.
    *   명령문으로 작성한다.
*   세부내용이 있을 경우 두 번째 줄은 비우고 세 번째 줄부터 세부내용을 적는다.
    *   세부내용은 꼭 필요하다고 판단되는 경우에만 적는다.
    *   72자 이상이 되면 개행한다.  // 보통 Git에서 열어준 vim이 알아서 72자 넘어가면 알아서 개행해준다.
    *   어떻게 바꿨는지는 쓰지 않는다.
    *   무엇을 바꿨는지와 왜 바꿨는지를 쓴다.
```

-   예시

    ```
    Split theme_applier.py

    Split theme_applier.py into zsh_theme_applier.py and
    plugin_theme_applier.py

    It is originally designed to apply zsh theme, but now it also controls
    theme of plugins like Git or Gerrit. These two features looks similar at
    the first glance, but they works so different internally.
    ```

-   여기서 시키는대로 하면 된다 : [https://item4.github.io/2016-11-01/How-to-Write-a-Git-Commit-Message/](https://item4.github.io/2016-11-01/How-to-Write-a-Git-Commit-Message/)

#### Push

-   편의상 PR은 없다. 
-   push하여 conflict가 있다면 서버 코드를 fetch하여 conflict를 핸들링한 후 다시 push한다.
    -   conflict는 rebase로 해결한다. 커밋이력을 깨끗하게!
-   이슈를 완전히 해결한 시점에 push한다.

#### Issue

-   새로이 구현할 기능이 있거나 수정해야 할 버그가 있으면 깃헙 이슈를 남긴다.
    -   깃헙에 이슈를 남겼으면 트렐로의 ToDo에도 같은 이름의 카드를 남긴다. 자세한 것은 [Trello](#Trello) 항목 참조.
-   완료되면 이슈를 닫는다.



### Code

#### ?

-   사용언어 확정 후 결정
-   어떤 언어든 간에 구글 스타일 가이드를 따르는 것을 원칙으로 한다.

#### 주석

-   사용 언어
    -   영어로 작성한다.
    -   모르겠으면 번역기 돌린다.
-   한 줄 주석 (//, #)
    -   코드에 부연설명이 필요한 경우 작성한다.
    -   코드를 설명하기 보다는 그 코드가 왜 필요한지에 대해 주석을 단다.
    -   주석이 많다고 마냥 좋은 게 아니다. 코드만으로 이해할 수 있게 짜는 게 최선이다.
    -   참고 : [http://www.gpgstudy.com/forum/viewtopic.php?t=14207](http://www.gpgstudy.com/forum/viewtopic.php?t=14207)
-   여러 줄 주석 (/* */, ''' ''')
    -   public function에는 반드시 달아야 한다.
    -   자세한 내용은 사용언어 확정 후 결정



### Trello

-   깃헙에서 남긴 이슈는 트렐로의 ToDo에도 남긴다.
    -   깃헙의 이슈제목과 카드의 이름을 같게 한다.
    -   깃헙의 이슈내용을 그대로 트렐로의 description에 쓴다.
    -   깃헙의 이슈번호가 12번이라면 트렐로 카드에 ISSUE_12라는 태그를 남긴다.
-   이슈에 대한 논쟁은 트렐로 댓글이 아닌 깃헙 쪽에 남긴다.
    -   이는 트렐로의 알림기능이 좀 더 불편하기 때문이다.
-   각자 자신이 구현할 수 있겠다고 판단되는 이슈에는 자신을 할당하고 해당 카드를 Progress로 옮긴다.
-   기능 구현이 완료되었다고 생각되면 Done으로 카드를 옮기고 Github에서도 이슈를 닫는다.