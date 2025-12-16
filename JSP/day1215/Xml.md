# XML(eXtensible Markup Language)
- 프로그램의 환경 설정용(server.xml, web.xml), 이종언어간의 데이터 전달용(C언어와 java언어 간에 데이터 전달)
- HTML과 다르게 태그가 정해져 있지 않다.(개발자가 상황에 맞게 태그를 정의해서 사용)
- SGML에서 생성되었고, node(태그)를 사용자가 마음대로 선언할 수 있다.
- 연산의 기능이 없다.
- 작성 규칙을 준수하지 않으면 error가 발생
- XML(Well-formed 문서), DTD(valid 문서), XSLT(XML용 stylesheet)로 구성될 수 있다.

## XML 작성 규칙
- 대,소문자를 구분
- 시작 노드와 끝 노드는 반드시 짝으로 나와야한다.
- 최상위 부모 노드(root node, 근 노드)는 반드시 하나만 존재
- 속성은 반드시 공백으로 구분되어야 한다.
- 선언부는 공백 없이 첫 줄에서만 작성되어야 한다.

## XML 문서 형식

```
<?xml version="1.0" encoding="UTF-8" standalone="DTD사용 여부"?>
<최상위부모노드>
	<자식 노드들.../>
</최상위부모노드>
```

## XML Parser
- XML 문서를 자르거나, 생성할 수 있는 도구
- SAX(Simple API XML)방식, DOM(Document Object Model)방식 Parser 존재
	- SAX 방식: SUN사에서 표준을 제정한 방식, 노드를 한 줄 씩 읽어들여 Parsing 하는 방식, 대용량의 XML 파일을 Parsing할 때 효율이 좋다.
	- DOM 방식: IBM사에서 제정한 방식, 노드를 객체로 만들고 Parsing 하는 방식, 대용량의 XML 파일을 PArsing할 때 효율이 좋지 않다.
	
## Parser를 사용한 XML 생성
1. XML 문서 생성
``Document doc=new Document();``

2. 최상위 부모노드를 생성
``Element rootNode=new Element("노드명");``
``Element rootNode=new Element("root");``

3. 부모노드를 XML 문서 객체에 추가
``doc.addContent(rootNode);``

4. 자식 노드를 생성
``Element subNode= new Element("자식 노드명");``
자식 노드의 값 설정
``subNode.setText("값");``

```
Element subNode=new Element("hello");
subNode.setText("안녕하세요");
```

5. 부모 노드의 자식 노드 추가
``doc.addContent(자식노드);``

6. 생성된 XML 문서 객체를 출력

```
XMLOutputter xOut=new XMLOutputter(Format.getPrettyFormat);
xOut.output(문서객체, 출력스트림);
``

