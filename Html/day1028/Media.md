# Media 재생태그
- 동영상(브라우저에서 codec을 지원하지 않으면 재생할 수 없다.)이나 음악을 재생할 때 사용하는 태그
- 브라우저는 음악을 재생할 수 있다.
- HTML 4.01까지는 `<embed>`로 동영상이나 음악을 모두 재생했으나 HTML 5부터는 동영상은 `<video>`로 음악은 `<audio>`로 구분하여 재생한다.

`<embed>` 사용법)
``<embed src="미디어 파일 경로" width="넓이" height="높이" controller="true"/>``

`<audio>` 사용법)
- 음악 재생할 때 사용<br>
```HTML
<audio src="음악파일의 경로" controls="controls">당신의 브라우저는 audio 태그를 지원하지 않습니다.
</audio>
``

- audio 태그는 지원하나 mp3를 지원하지 않는 웹 브라우저로 접속한 경우
```HTML
<audio controls="controls">
	<source src="음악파일의 경로"/>
	<source src="음악파일의 경로"/>
</audio>
```

`<video>` 사용법)
- 동영상을 재생할 때 사용<br>
```HTML
<video src="동영상 파일의 경로" controls="controls" width="넓이" height="높이" poster="thumbnail이미지의 경로">
당신의 브라우저는 이 태그를 지원하지 않습니다.
</video>
```

- video 태그는 지원하나 codec을 지원하지 않는 웹 브라우저로 접속한 경우
```HTML
<video controls="controls" width="넓이" heigth="높이" poster="thumbnail 이미지의 경로">

<source src="동영상파일의경로"/>
<source src="동영상파일의경로"/>
</video>
```