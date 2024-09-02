# FOSS-2024-1-FINAL

## 빌드하면서 발생하는 각종 에러에 대처하기

### 이 문서를 들어가기 전에
- [여기에서](https://developer.gimp.org/core/debug/problems_and_solutions/#build) 대부분의 에러를 찾을 수 있습니다.
- `Dependency ~ not found`는 지칭하는 패키지가 없는 경우가 대부분으로, 설치해주면 보통 해결됩니다.
- 에러 메시지에 해당하는 부분을 구글에 검색하면 보통 유사한 에러를 겪은 사람들이 남긴 이슈를 찾을 수 있습니다.
- 아래에는 필자가 빌드 과정에서 구글링해도 잘 나오지 않았던 에러와 그에 대한 해결 방법 등이 있습니다.


### ERROR: Unhandled python exception while building babl
- [Meson 깃헙 레포지토리](https://github.com/mesonbuild/meson/discussions/13261#discussioncomment-9572300)에 직접 이슈를 남겨 meson 개발자에게 친절한 답변을 들을 수 있었습니다.
- GIMP를 빌드할 때 필요한 meson은 버젼이 `0.61.0`으로, 시스템에 다른 버젼의 meson도 설치되어 충돌이 일어난 것이었습니다.
- 여러분이 위와 유사한 에러를 보시면 `meson -v`와 `sudo apt install meson`을 통해 다른 버젼의 meson이 설치되어 있는지 확인 후, 불필요한 버젼을 제거하시면 됩니다.

### ninja: build stopped와 엄청난 양의 python exception이 뜨는 경우
- 보통 에러 메시지가 잘 보이지 않지만, 찾으면 에러 메시지가 분명하여 해당 에러를 구글에 검색하면 해결법이 나옵니다.
- [이 경우는](https://gitlab.gnome.org/GNOME/gimp/-/issues/11369) 저도 빌드 환경 테스트 중에 처음 목격한 에러였습니다.
- 해당 에러의 해결은 크게 두 가지로 할 수 있는데,
1. 환경 변수 `GI_TYPELIB_PATH`를 알맞게 설정하기. 우분투의 경우 `export GI_TYPELIB_PATH=/usr/local/lib/x86_64-linux-gnu/girepository-1.0:/usr/local/lib/girepository-1.0` 로 해주면 됩니다.
2. `apt install libgegl-dev`로 패키지 설치 과정에서 위 환경 변수가 자동으로 설정되게 할 수 있다고도 합니다.
