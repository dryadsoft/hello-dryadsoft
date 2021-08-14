# Hello Dryad

## npm 패키지 배포하기

1. npm에 로그인 한다.

   ```shell
   $ npm login 또는 yarn login
   ```

2. npm 패키지명 정하기

   > 중복된 이름은 사용 할 수 없기때문에 내가 정한 이름이
   > 존재하는지 확인해본다.

   ```shell
   # npm 사용할때
   $ npm info hello-dryad

   npm ERR! code E404
   npm ERR! 404 'hello-dryad' is not in the npm registry.
   npm ERR! 404 You should bug the author to publish it
   npm ERR! 404 (or use the name yourself!)
   npm ERR! 404
   npm ERR! 404 Note that you can also install from a
   npm ERR! 404 tarball, folder, http url, or git url.
   npm ERR! 404
   npm ERR! 404  'hello-dryad@latest' is not in the npm registry.
   npm ERR! 404 You should bug the author to publish it (or use the name yourself!)
   ...

   # yarn 사용할때
   $ yarn info hello-dryad

   yarn info v1.22.10
   error Received invalid response from npm.
   Done in 0.89s.
   ```

3. 패키지 생성하기

   > 새로 생성할 패키지명과 같은 폴더명을 만든다.<br>
   > 생성된 폴더안에서 npm 또는 yarn을 사용하여 package.json 파일을 만들어준다.

   ```shell
   $ mkdir hellow-dryad
   $ cd hello-dryad
   $ yarn init 또는 npm init
   ```

4. package.json 파일 필수정보 입력하기

   - name: 패키지명(필수)
   - version: 패키지버전(필수)

5. 패키지 배포

   ```shell
   $ npm publish 또는 yarn publish
   ```

6. 패키지 재배포

   > npm 패키지는 패키지명뿐만 아니라 버전도 중복을 허용하지 않는다.<br>
   > 그래서 재배포를 위해서는 버전을 변경해줘야한다.

   - 패키지 버전 변경방법 1 - 명령어 사용

   ```shell
   $ npm version major     # package.json파일 version 의 첫번째 숫자
   $ npm version minor     # package.json파일 version 의 두번째 숫자
   $ npm version patch     # package.json파일 version 의 세전째 숫자
   ```

   - 패키지 버전 변경방법 2 - 직접 변경

   > package.json 파일의 version의 버전을 직접 변경한 후 저장한다.

7. 배포한 패키지 삭제하기

   > 배포한 패키지는 72시간이 지나면 삭제가불가능합니다.

   ```shell
   $ npm unpublish 패키지명 --force 또는 yarn unpublish 패키지명 --force
   ```

   > 특정버전 삭제하기

   ```shell
   $ npm unpublish 패키지명@0.0.1 또는 yarn unpublish 패키지명@0.0.1
   ```

8. 등록한 패키지 사용하기

```shell
$ npm install hello-dryad 또는 yarn add hello-dryad
```

9. npm 패키지 배포시 오류 해결방법
   > 만약 npm에 방금가입하고 패키지를 올리려고한다면 아래와 같은 오류가 발생 할 수 있다.

```shell
$ npm publish
...
npm ERR! code E403
npm ERR! 403 403 Forbidden - PUT https://registry.npmjs.org/hello-dryad - Forbidden
npm ERR! 403 In most cases, you or one of your dependencies are requesting
npm ERR! 403 a package version that is forbidden by your security policy.

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\antnf\AppData\Roaming\npm-cache\_logs\2021-08-14T04_47_31_517Z-debug.log
```
