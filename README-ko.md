<p align="right">
  [한국어]
  [<a href="README.md">English</a>]
</p>

# YTDClip

YTDClip은 다양한 형식과 품질 옵션을 제공하여 YouTube 동영상을 쉽게 다운로드할 수 있는 도구입니다. 이 프로젝트는 Python의 yt-dlp 라이브러리를 사용하여 만들어졌습니다.

> 정기적으로 업데이트되는 컨텐츠를 하나씩 찾아서 다운로드하는 번거로움을 줄이기 위해 YTDClip을 만들었습니다. 즐겨찾는 리스트에 등록하고 번호만 지정하면 YTDClip은 이미 받은 컨텐츠는 건너뛰고 새로 업데이트된 컨텐츠만 다운로드해 줄 것입니다.

### 기능

- YouTube 동영상 다운로드 (`Videos`, `Shorts`, `Playlists`)
- 다양한 형식(`mp4`, `webm`, `mp3`, `m4a` etc.)으로 변환
- 다양한 퀄리티 옵션 제공 (최고 `비디오+오디오`, `비디오`, `오디오`, `일반`)
- 파일에서 URL 목록을 불러와 일괄 다운로드 (`txt`)
- 인터랙티브 모드 지원 (대화형으로 쉬운 진행)

<img width="682" alt="ss" src="https://github.com/micronzone/YTDClip/assets/47780105/55f09620-cdc6-4c47-93bb-ef2ba674b0ad">

### 설치

프로젝트를 클론합니다:

```bash
git clone https://github.com/micronzone/YTDClip.git
cd YTDClip
```

실행 권한 부여:
```bash
chmod +x ytdclip
```

(선택 사항) 가상 환경을 생성하고 활성화합니다:
```sh
python3 -m venv .venv
source .venv/bin/activate  # Linux 또는 macOS
.\.venv\Scripts\activate   # Windows
```

pip를 사용하여 필요한 라이브러리를 설치합니다:
```bash
pip3 install -r requirements.txt
```

또는 `yt-dlp>=2023.05.18` 이상을 설치할 수 있습니다:

```bash
pip3 install yt-dlp
```

별칭 추가 (선택 사항):

```bash
nano ~/.zshrc   # macOS ~/.zshrc, Linux `~/.bashrc` or `~/.zshrc`
alias ytdclip='/path/to/ytdclip'
```

```bash
source ~/.zshrc
```

### 사용법

YTDClip은 명령줄 인터페이스(CLI)를 통해 사용하거나, 인터랙티브 모드를 통해 사용할 수 있습니다.

### 옵션

- `-a`: 대화형으로 실행
- `-l` `FILE`: `txt`파일에 있는 YouTube 동영상의 URL `Videos`, `Shorts`, `Playlists` 등을 불러오는 기능
- `-e`, `--extension` {`mp4`, `webm`, `mp3`, `m4a`, etc.}: 다운로드할 파일의 확장자 지정 (기본값: `mp4`)
- `-f`, `--format` {`b`, `bv`, `ba`, `bb`}: 다운로드 퀄리티 지정 (b=일반 비디오+오디오, bv=최상 비디오, ba=최상 오디오, bb=최상 비디오+오디오 중 선택, 기본값: `b`)
- `-o`, `--output` `PATH`: 다운로드 디렉토리 지정
- `--debug`: 디버그 로깅 활성화

### 명령줄 인터페이스 (CLI) 사용법

기본적인 사용법은 다음과 같습니다:

```bash
# ytdclip을 별칭에 추가한 실행 방법입니다(설치 참고) 또는 YTDClip 디렉토리에서 ./ytdclip 실행
ytdclip
ytdclip [YouTube URL]
ytdclip [options] [YouTube URL]
```

YouTube URL 목록 사용
```bash
ytdclip [options] [Favorites.txt]
```

```bash
# [YouTube URL], [Comment]
https://www.youtube.com/watch?v=example, 유익한 영상
https://www.youtube.com/@example, 그리즐리 베어
https://www.youtube.com/@example/shorts, 댄스 쇼츠
https://www.youtube.com/@example/playlists, 즐겨찾는 재생목록
```

## 예제

YouTube 동영상을 다운로드하는 간단한 예제입니다:

대화형 다운로드 실행
```bash
ytdclip -a
```

옵션을 지정하여 대화형 다운로드 실행
```bash
ytdclip -a -o ~/Downloads
ytdclip -a -o ~/Downloads -e mp4
ytdclip -a -o ~/Downloads -e mp4 -f b
ytdclip -a -o ~/Downloads -e mp4 -f b -l favorites.txt
```

명령줄에서 다운로드 실행

```bash
ytdclip -o ~/Downloads -e mp4 -f b https://www.youtube.com/watch?v=YOUR_VIDEO_ID
```

명령줄에서 YouTube URL 목록 실행
```bash
ytdclip -o ~/Downloads -e mp4 -f b -l favorites.txt
```

### 업데이트

YTDClip 리포지토리 업데이트를 확인하는 것이 좋습니다!

```sh
cd YTDClip
git status
```

변경 사항 가져오기:

```sh
git pull origin main
```

### 기여 방법

기여해주셔서 감사합니다! 이 프로젝트에 기여하시려면 아래 단계를 따라 주세요:

1. 이 리포지토리를 포크하세요
2. 기능 브랜치(micronzone 브랜치)를 생성하세요 (`git checkout -b micronzone/YTDClip`)
3. 변경 사항을 커밋하세요 (`git commit -m 'Add some YTDClip'`)
4. 브랜치에 푸시하세요 (`git push origin micronzone/YTDClip`)
5. 풀 리퀘스트를 여세요

### 라이센스

이 프로젝트는 MIT 라이센스 하에 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참고하세요.