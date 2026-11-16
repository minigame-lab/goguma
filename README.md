# 고구마 깎기 3D

고구마 10,000개를 깎고, 쪄서, 파는 1인칭 3D 웹 게임입니다.

| 구분 | 주소 | 나오는 곳 |
|---|---|---|
| 실제 게임 | https://minigame-lab.github.io/goguma/ | `main` 브랜치 |
| 테스트 | https://minigame-lab.github.io/goguma/test/ | `test` 브랜치 |

올리면 1~3분 뒤 자동으로 반영됩니다. 테스트 주소에는 화면 오른쪽 아래에 "테스트 버전" 표시가 붙고, 저장 데이터도 실제 게임과 따로 씁니다.

## 같이 수정하는 순서

1. **최신 파일부터 받기.** 고치기 전에 항상 저장소의 최신 `main`을 받습니다. 예전 파일로 작업하면 다른 사람이 넣은 기능이 사라집니다.
2. **`test` 브랜치에 올리기.** 고친 내용은 `main`이 아니라 `test`에 올립니다.
3. **테스트 주소에서 확인하기.** 게임이 뜨는지, 다른 사람이 넣은 기능이 그대로 있는지 봅니다.
4. **`main`에 합치기.** GitHub에서 `test` → `main` Pull request를 만들고 Merge를 누르면 실제 게임에 반영됩니다.

## 지킬 것

- `main`에 예전 파일을 통째로 덮어쓰지 않습니다.
- 같은 시간에 같은 파일을 고치지 않도록 "지금 내가 고친다"고 서로 알립니다.
- 저장 데이터 키(`goguma3d_v1`)와 항목 이름은 유지합니다. 바꾸면 하던 사람들의 진행이 사라집니다.
- `.github/workflows/pages.yml`은 자동으로 올려 주는 설정이라 건드리지 않습니다.

## git 명령 예시

```bash
git clone https://github.com/minigame-lab/goguma.git
cd goguma
git checkout test
git pull origin main          # test를 최신 main에 맞추기
# ... 수정 ...
git add -A
git commit -m "무엇을 바꿨는지"
git push origin test          # 테스트 주소에 반영
```

## 파일 구성

- `index.html`: 게임 전체 (규칙, 화면, 조작)
- `assets/`: 텍스처와 3D 모델. 모두 Poly Haven의 CC0 자료이며 목록은 `assets/CREDITS.md`에 있습니다.
- `.github/workflows/pages.yml`: 자동 올리기 설정
