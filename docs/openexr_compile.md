# OpenEXR 컴파일하기.

- git을 이용해서 OpenEXR 소스코드를 다운로드 합니다.
```
$ git clone https://github.com/openexr/openexr openexr_src
```

#### IlmBase 컴파일
- 먼저 IlmBase 라이브러리를 컴파일 하겠습니다. IlmBase 폴더로 이동합니다.
```
$ cd openexr_src/IlmBase
```

- configure 파일을 생성하기 위해서 bootstrap을 타이핑합니다.
```
$ ./bootstrap
```
- bootstrap이 잘 실행되었다면, configure 파일이 생성됩니다.
- configure 파일을 실행합니다. --prefix 옵션을 달아서 어디로 컴파일 할것인지 옵션을 설정하세요.
```
$ scl enable devtoolset-6 bash
$ ./configure --prefix=$HOME/app/IlmBase
```
- make 명령을 이용해서 컴파일 합니다.
```
$ make
```
- make 컴파일된 명령어를 prefix 경로로 배포합니다.
```
$ make install
```

- 잘 배포되면 prefix 경로에 include, lib 폴더가 생성되어 있습니다.
- 위 prefix경로는 다른 라이브러리 또는 프로그램 컴파일시 `--with-ilmbase-prefix`, `ILMBASE_HOME`등 키값에 대한 변수로 사용할 수 있습니다.

#### OpenEXR 컴파일
- 위와 같은 방식으로 똑같이 OpenEXR 컴파일을 진행합니다.
- prefix경로는 `~/app/OpenEXR`로 변경했습니다.
```
$ cd openexr/OpenEXR
$ ./bootstrap
$ ./configure --prefix=$HOME/app/OpenEXR
$ make
$ make install
```

- prefix경로에 bin, include, lib, share 경로가 생성됩니다.
