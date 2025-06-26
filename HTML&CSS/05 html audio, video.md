# audio, video

### 오디오 태그

---

`<audio>` 태그는 HTML 문서에 소리 콘텐츠를 넣을 때 사용한다.

MP3, WAV, Ogg 세 가지 포맷의 파일을 지원한다.

```html
<audio controls>
	<source src="url" type="audio/mpeg">
	<source src="url" type="audio/ogg">
</audio>
```

**속성**

- **controls** : 화면에 컨트롤 바(재생막대)를 표시
- **autoplay** : 자동 재생 설정(크롬에서는 정책적으로 오디오와 자동 재생을 허용하지 않음)
- **loop** : 반복 재생 설정
- **muted** : 음소거
- **preload** : 페이지를 불러올 때 파일을 어떻게 로딩할 것인지 지정
    
    **속성값** : auto, meradata, none(기본값 auto)
    
- **width, height** : 너비와 높이를 지정

## 비디오 태그

---

`<video>` 태그는 영상 콘텐츠를 HTML 문서에 삽입할 때 사용한다.

mp4, ogg 두 가지 포맷의 파일을 지원한다.

```html
<video width="320" height="240" controls>
	<source src="url" type="video/mp4">
</video>
```

**속성**

- **controls** : 화면에 컨트롤 바(재생막대)를 표시
- **autoplay** : 자동 재생 설정(크롬에서는 정책적으로 오디오와 자동 재생을 허용하지 않음)
- **loop** : 반복 재생 설정
- **muted** : 음소거
- **preload** : 페이지를 불러올 때 파일을 어떻게 로딩할 것인지 지정
    
    속성값 : auto, meradata, none(기본값 auto)
    
- **width, height** : 너비와 높이를 지정
- **poster**=”파일이름” : 비디오가 재생되기 전까지 화면에 표시될 포스터 이미지 지정