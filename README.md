> [만들면서 배우는 svelte](https://freeseamew.gitbook.io/svelte/)

> [2-5강 까지의 예제](https://github.com/freeseamew/svelte-tutoral-basic-example)

> [todo 기본 예제](https://github.com/freeseamew/todo-svelte-basic)

> [todo 리팩토링 + routift + ajax](https://github.com/freeseamew/todo-svelte-store)

===

# Install

```bash
C:\MoonDev\withTool\inSvelte\svelteLearning> bootapp -u mooninlearn -n learn-svelte-web-freeseamew -d "만들면서 배우는 svelte(https://freeseamew.gitbook.io/svelte/)" -t svelte-web-template-js
```

===

# 1. svelte 소개 - 만들면서 배우는 svelte
svelte는 2016년경 만들어진 매우 젋은 프레임워크 입니다. 2019년도에 관심도가 급격히 상승했는데요, 저도 이때즘 svelte를 접하게 되었습니다.

svelte 홈페이지를 보시면 첫 페이지에 다음과 같은 3가지를 중요한 특징으로 말하고 있습니다.

-   write less code (보다 적은 코드로)
    

이 특징들 중에서 코드를 조금만 다뤄 봐도 체감이 가능한 부분은 write less code, 그리고 Truly reactiv 즉 보다적은 코드로 reactivity 적인 결과물을 낼 수 있는 부분입니다.

다음 코드를 봐주시기 바랍니다. state를 정의하는 부분을 다른 프레임워크들과 비교한 부분인데요. 코드의 양이 확연히 차이가 나는 것을 알 수 있습니다. 보다 적은양의 코드로 결과물을 만들 수 있다는 것이고 이것은 높은 생산성이 보장됨을 말하는 부분이기도 합니다.

![](https://2117807434-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MFoRG7N_kopXKHrUIam%2F-MGREo3lPl93CZJeFtnQ%2F-MGRFPu5vXPg3sjHDTBg%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-09-03%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%203.13.38.png?alt=media&token=4802c80f-d45d-4333-98c9-e45af1adcb9c)

그리고 지금 이 코드는 리엑티비티 즉 반응성을 테스트 하는 코드 인데요.

alert('카운트가 10을 넘었습니다. ')

<button on:click={handleClick}>

클릭수 { count } {count === 1 ? 'time' : 'times'}

<p>{count} 두배는 {doubled} </p>

몇몇 선언 만으로 특별한 호출 없이 다양한 기능이 작동하는 것을 볼 수 있습니다. 실제로 프론트앤드를 개발하는 과정에서 화면의 다양한 부분들이 유기적으로 연동되어야 할 경우가 많습니다. 이때 필요한 부분들을 계속해서 개발자가 호출하는 것이 아니라 특정 상태를 바라보도록만 해주만 그 상태가 되었을 때 자동적으로 호출이 발생하는 것입니다. 이부분은 정말로 편리한 기능이라고 생각합니다

또한 다른 특징으로 기존 프론트엔드 프레임워크와는 다르게 svelte는 빌드시 svelte소스는 최소한 으로 하고 순수한 자바스크립트 형태로 컴파일이 됩니다. 이 때문에 빌드 결과물의 사이즈도 작아지고 당연히 사용되는 메모리량도 적을 수 밖에 없습니다.

저도 이런 특징들 때문에 svelte를 본격적으로 사용하게 되었습니다.

저는 svelte를 이용해서 todo 서비스를 만들어 볼 예정입니다.

![](https://2117807434-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MFoRG7N_kopXKHrUIam%2F-MGREo3lPl93CZJeFtnQ%2F-MGRF7PrzjS6IxtdvPJb%2Ftodo%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2.2020-09-05%2011_08_53.gif?alt=media&token=577c6293-73d9-44c7-a328-64371f425ca3)

svelte를 다루는 기초적인 방법부터, router, ajax 등 프론트앤드 개발에 필수가 되는 부분들을 함께 배워가 보도록 하겠습니다.

이를 과정을 통해서 여러분들이 svelte의 매력을 조금이라도 느껴보셨으면 좋겠습니다.

![](https://2117807434-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MFoRG7N_kopXKHrUIam%2F-MGqndftNeXvP53tyaae%2F-MGqwZuQK1aEaE5Bp21i%2F%E1%84%86%E1%85%A1%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%86%E1%85%A7%E1%86%AB%E1%84%89%E1%85%A5%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%84%82%E1%85%B3%E1%86%AB%20svelte%20small.png?alt=media&token=e769cba7-bb5e-40a9-89c6-2879e60242bf)