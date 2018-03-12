
# 협업 규칙



## 커뮤니케이션

-   [1term](#1학기-중간고사-전-(1term)) 이후로는 팀원을 챙기지 않는 것을 원칙으로 한다. [2term](#1학기-기말고사-전-(2term))부터는 지식의 공유는 100% 문서와 협업도구를 통해 이루어지고 이를 읽지 않는 것은 본인의 책임이다. 공유된 사항을 모두 읽고도 여전히 모르는 것은 직접 물어보거나 공부한다.
-   다른 라이브러리나 모듈을 사용할 때는 반드시 간략한 설명과 사용법을 문서로 남겨야 한다.




## Cooperation Rules

-   현재 당신이 보고 있는 바로 이 문서!
-   추가 또는 수정하고 싶은 내용이 있으면 깃헙에 이슈로 남긴다.
-   이 문서를 직접 수정하는 것은 [42desix](https://github.com/42desix) 한 명으로 제한하는 것을 원칙으로 한다.




## Wiki

-   이슈 하나를 완료할 때마다 수정하는 것을 원칙으로 한다.




## Git

### 커밋메시지

-   영어로 작성한다.


-   다음의 형식을 따른다.

    ```bash
    Commit message title

    Details will be here.
    If you have more details, you can write them in multi lines.
    ```

-   첫 줄에는 제목을 적는다.
    -   첫 글자는 대문자로 적는다.
    -   마침표를 찍지 않는다.
    -   50자 이하로 적는다.  // 보통 Git에서 열어준 vim이 알아서 50자 넘어가면 경고를 표시한다.
    -   명령문으로 작성한다.
    -   관련된 이슈가 있으면 :#nn 과 같은 형태로 제목 맨 뒤에 이슈번호를 적어 링크를 생성한다.
-   세부내용이 있을 경우 두 번째 줄은 비우고 세 번째 줄부터 세부내용을 적는다.
    -   세부내용은 꼭 필요하다고 판단되는 경우에만 적는다.

    -   72자 이상이 되면 개행한다.  // 보통 Git에서 열어준 vim이 알아서 72자 넘어가면 알아서 개행해준다.

    -   어떻게 바꿨는지는 쓰지 않는다.

    -   무엇을 바꿨는지와 왜 바꿨는지를 쓴다.

    -   한 커밋에 들어가는 수정 내역이 여러 항목일 경우 하이픈(-)을 이용하여 구분한다.
-   예시1

    ```
    Split theme_applier.py

    Split theme_applier.py into zsh_theme_applier.py and
    plugin_theme_applier.py

    It is originally designed to apply zsh theme, but now it also controls
    theme of plugins like Git or Gerrit. These two features looks similar at
    the first glance, but they works so different internally.
    ```

-   예시2

    ```
    Change the design :#12

    - Removed the navigation bar.
    - Changed the font.
    ```

-   참고 : [https://item4.github.io/2016-11-01/How-to-Write-a-Git-Commit-Message/](https://item4.github.io/2016-11-01/How-to-Write-a-Git-Commit-Message/)
### Push

-   편의상 PR은 없다. 
-   push하여 conflict가 있다면 서버 코드를 fetch하여 conflict를 핸들링한 후 다시 push한다.
    -   conflict는 rebase로 해결한다. 커밋이력을 깨끗하게!
-   1커밋당 1푸시.
    -   [트렐로](#trello) 카드 하나를 완전히 해결한 시점에 commit한다.

### Issue

-   새로이 구현할 기능이 있거나 수정해야 할 버그가 있는데 자신이 이를 바로 해결할 여건이 되지 않으면 깃헙 이슈를 남긴다.
-   완료되면 완료한 사람이 이슈를 닫는다.




## Code

### ?

-   사용언어 확정 후 결정
-   어떤 언어든 간에 구글 스타일 가이드를 따르는 것을 원칙으로 한다.

### 주석

-   사용 언어
    -   영어로 작성한다.
    -   모르겠으면 번역기 돌린다.
-   한 줄 주석 (//, #)
    -   코드에 부연설명이 필요한 경우 작성한다.
    -   코드를 설명하기 보다는 그 코드가 왜 필요한지에 대해 주석을 단다.
    -   주석이 많다고 마냥 좋은 게 아니다. 코드만으로 이해할 수 있게 짜는 게 최선이다.
    -   참고 : [http://www.gpgstudy.com/forum/viewtopic.php?t=14207](http://www.gpgstudy.com/forum/viewtopic.php?t=14207)
-   여러 줄 주석 (/- */, ''' ''')
    -   자세한 내용은 사용언어 확정 후 결정





## Trello

-   구현사항이 생각 나면 Trello의 To Do 카테고리에 카드를 만든다.
-   깃헙의 이슈들 중에서 해결해야 하는 일 역시 To Do 카테고리 안에 하나 이상의 카드로 만든다.
    -   이슈 하나가 통째로 카드가 될 수도 있고 여러 task로 쪼개져도 된다.
    -   깃헙의 관련된 이슈 번호가 12번이라면 트렐로 카드에 ISSUE_12라는 태그를 남긴다.
-   이슈에 대한 논쟁은 트렐로 댓글이 아닌 깃헙 쪽에 남긴다.
    -   이는 트렐로의 알림기능이 좀 더 불편하기 때문이다.
-   각자 자신이 구현할 수 있겠다고 판단되는 이슈에는 자신을 할당하고 해당 카드를 Progress로 옮긴다.
    -   다른 사람이 스스로에게 할당해놓은 일은 건드리지 않는다.
-   기능 구현이 완료되었다고 생각되면 Done으로 카드를 옮기고 Github에서도 이슈를 닫는다.
    -   굵직한 내용은 남기지만 간단한 bug fix 등은 archive시킨다.







# 일정

### 1학기 중간고사 전 (1term)

-   협업규칙 설정
-   코드 분석
-   언어~~, 라이브러리, 프레임워크~~ 결정
-   개략적인 설계
-   개발 환경 설정
-   상기 모든 사항에 대한 팀원간 이해도 확인

### 1학기 기말고사 전 (2term)

-   개발
    -   시행착오
    -   다른 언어로의 수정 (불필요한 기능은 삭제)
-   문서 업데이트

### 여름방학 (3term)

-   개발
    -   새로운 feature 추가
-   문서 업데이트

### 2학기 중간고사 전 (4term)

-   계획이란 원래 뜻대로 되지 않기 마련이다.

### 마무리 (5term)

-   시각화
-   retrospect