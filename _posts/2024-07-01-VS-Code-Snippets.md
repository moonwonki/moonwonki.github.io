---
layout: single
title: "VS Code 스니펫 만들고 적용하기"
categories: IDE
tag: ["VS Code", "IDE"]
author_profile: false
classes: wide
toc: true
sidebar:
    nav: "counts"
---

**[공지사항]** [IDE 카테고리 포스트 살펴보기](https://moonwonki.github.io/categories/#ide)
{: .notice--warning}


# :rocket: 코드 스니펫이란?

스니펫이란 **미리 작성된 코드 조각**이다.
코딩을 하다보면 생각보다 반복된 코드 조각들을 굉장히 많이 사용하게 된다.

그것을 재사용할 수 있게 만들어 놓은 것을 코드 스니펫이라 한다. <br/><br/>

# :rocket: 사용하게 된 계기

깃허브 블로그를 만들면서 생각보다 난관에 많이 부딪혔다.

이 과정에서 포스트 작성 과정을 간소화하고 싶다는 생각이 많이 들었고, 이 과정에서 코드 스니펫을 활용하기로 했다.

어차피 나는 VS code로 md파일을 작성하기에, VS Code가 지원하는 스니펫 기능을 활용할 수 있을 것이라는 생각이 들었다.

참고로 VS Code는 스니펫을 지원하는 탁월한 에디터같다.<br/><br/>


# :rocket: 쓰는 방법

## :sparkles: 1. 스니펫 생성

스니펫을 적용할 때, 해당 스니펫을 어디에 활용할 것인지를 정해야 한다.

- VS Code로 작성하는 모든 파일에 적용할 것인가?
- 아니면 특정 폴더 밑에서 작성하는 모든 파일에 적용할 것인가?

위에 것은 Global 스니펫이고, 아래는 폴더에만 적용되는 스니펫이다.

정했다면 File -> Preferences -> Configure User Snippets를 클릭한다.

![alt text]({{ "../assets/images/2024-07-01-01/image.png" | relative_url }})

이러면 다음과 같은 창이 뜬다.

![alt text]({{ "../assets/images/2024-07-01-01/image-1.png" | relative_url }})

---

**new Global Snippets file** : 어디서나 사용할 수 있는 코드 스니펫을 만들 때 클릭. 
<br/>

**new Snippets file for 폴더명**: 해당 '폴더명' 하위 작업 파일에서 사용할 수 있는 코드 스니펫을 만들 때 클릭.
<br/>

**특정 언어 선택** : 각 언어별로 코드 스니펫을 만들 때 적용할 코드 스니펫. 해당 언어 이름.json 파일이 생성되어 적용된다.
<br/>

---

원하는 것을 클릭하면 된다. 코드 스니펫 파일의 이름을 정하고 엔터를 누르면 code-snippets 확장자의 스니펫 파일이 생성된다.

Global Snippets를 고르면 윈도우 기준 User/유저이름/AppData/Roaming/Code/User/snippets 안에 스니펫 파일이 생성된다.
<br/>

폴더명을 고르면 해당 폴더의 .vscode 폴더 밑에 해당 스니펫 파일이 생성된다.
<br/>

나는 블로그 포스트 md 파일을 작성할 때만 사용할 것이기 때문에 폴더명을 골랐다.<br/><br/>

## :sparkles: 2. 스니펫 작성

```json
{
    "이름": {
        "scope": "확장자",
        "prefix": "시동 텍스트",
        "body": [
            "작성될 텍스트"
        ],
        "description": "스니펫 설명"
    }
}

```

한글로 작성된 부분이 내가 채워넣을 부분이다. <br/>
**이름**에는 내가 원하는 스니펫의 이름을 자유롭게 적으면 된다. <br/>
**scope**는 해당 스니펫이 적용될 파일의 언어를 정해주는 것이다. 없어도 된다. <br/>
**prefix**는 시동 텍스트라고 이름 붙였는데, 해당 시동 텍스트를 작성하면 자동완성으로 코드 스니펫이 뜬다.<br/>
**body** 안에 자동완성으로 작성될 텍스트를 적어주면 된다.<br/>
**description**은 해당 스니펫에 대한 설명을 적어준다.<br/><br/>

예시를 적자면 다음과 같다.<br/>

![alt text]({{ "../assets/images/2024-07-01-01/image-2.png" | relative_url }})

<br/>
나 같은 경우는 scope가 굉장히 화려한데, 여러 에러를 처리하다가 그냥 대문자 소문자 다 가리지 않고 다 넣었다. <br/>

**뭐 굴러가니깐!** <br/><br/>


# :rocket: 사용하기

나는 희안하게 prefix에 적힌 텍스트를 적었는데도 자동완성이 뜨지 않았다.<br/>
VS Code의 문제일 수도 있고... 뭐 여러가지 있겠지만 그럴 때는 ctrl + 스페이스바를 눌렀더니 해당 스니펫이 자동완성으로 떴다.<br/><br/>

다만 이렇게 해도 안 뜨는 경우에는 vs code를 껐다가 키는 것을 추천한다. <br/>
사용환경에 따라 천차만별의 차이가 있겠지만 대체로 prefix에 적힌 텍스트를 입력하면 자동완성으로 뜨는 것 같았다.<br/>