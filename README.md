# backquote_highlight


글을 작성할 때 highlighting처리 하고 싶은 부분을 markdown처럼 \`\`\`*로 감싸면 본문에서 이를 인식해 `<div><pre><code class="language-*>`로 치환해준다.  
highlight plugin을 사용할 때 매번 HTML을 작성하기 귀찮아서 만들었기 때문에 단순히 치환하는 기능만 있고 자체 highlighting 기능은 없다.  
따라서, highlightjs나 prismjs 등 HTML5 표준 문법을 지키는 highlight plugin과 함께 사용해야 한다.  
inline highlighting도 지원하며 \`를 사용해야 하는 경우가 있어 \`\`로 지정했다. `<code class="language-*>`로 치환해준다.  
\`\`code1 code2\`\` 처럼 붙여 쓰는 경우 이를 lang으로 인식하므로, \`\` code1 code2\`\`로 처음에 공백을 넣어주어야 한다.

### Usage
티스토리에 파일을 업로드 하고 다음 코드를 HTML에 추가하면 알아서 돌아간다.  
jQuery를 사용했기 때문에, jQuery를 불러오는 부분보다 더 아래에 위치하도록 추가해야 한다.  
```
script src=jQuery
...
<script defer src="./images/backquote_highlight.min.js" onload="bq_highlight()"></script>
```

### Block highlighting
\`\`\`python  
def foo:
    bar = 1  
\`\`\`  
=>  
```python
def foo:
    bar = 1
```

### Inline highlighting
\`\`python code\`\`  
=>  `code`  
