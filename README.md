# spring-fileupload

request 전체 파라미터 값 보는 셋팅

```
application.properties
logging.level.org.apache.coyote.http11=trace
```

업로드 사이즈 제한
```
spring.servlet.multipart.max-file-size=1MB
spring.servlet.multipart.max-request-size=10MB
```

파일 업로드 관련 셋팅 값(기본 true)
```
spring.servlet.multipart.enabled=false
```

파일 업로드 경로 설정
```
application.properties
file.dir=파일 업로드 경로 설정(예): /Users/kimyounghan/study/file/
```
@Value 애노테이션
```
@Value("${file.dir}")
private String fileDir;
application.properties 에서 설정한 file.dir 의 값을 주입한다
```

Part 주요 메서드
```
part.getSubmittedFileName() : 클라이언트가 전달한 파일명
part.getInputStream(): Part의 전송 데이터를 읽을 수 있다.
part.write(...): Part를 통해 전송된 데이터를 저장할 수 있다
```

MultipartFile 주요 메서드
```
file.getOriginalFilename() : 업로드 파일 명
file.transferTo(...) : 파일 저장
```