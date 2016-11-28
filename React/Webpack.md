##**Webpack**
> 웹팩은 Module Bundler이다. 하나의 큰 파일을, 여러 종속관계를 가진 모듈로 쪼개주고<br>
> 성능향상, CSS 전처리기 컴파일, Hot-Reloading을 지원하는 Asset 관리 전반적인 프로세스에 도움을 준다.<br>
> 쉽게말해, 의존성 관계를 가진 모듈들을 번들링하여 각자의 모듈 역할을 수행하는 'Statical Assets'들을 생성해낸다.<br>

###**Background**

웹 애플리케이션이 확장하게되면, 당연히 코드가 길어지고 코드의 모듈화가 필요해진다.<br>
이때 분리된 각 모듈들 간에는 의존성(Dependency)가 존재한다. 서버사이드에서는 Nodejs를 예로들면 require방식을 쓰지만<br>
**클라이언트 사이드의 JS에서는 기본적으로 모듈간의 import/include를 지원하지 않는다.**<br>
해당 과정에서, 각 모듈간의 종속관계를 해석하고, 번들링 해주는 웹팩이 필요 한 것이다.<br>
* 참고로 최초의 모듈 번들러는 RequireJS, Browserify등이 있긴 하지만..

###**Role**
1. Code Splitting

2. JS/CSS Preprocessing

3. Long Term Caching

4. Hot Reloading

5. More Things..
