# 용도

특정 사이트의 상품 상세페이지를 일일히 수정할 필요 없이, github의 html 파일만 수정하면 동기화됩니다.


**Q. 다른 안내사항도 이 방식을 쓰면 편하잖아요. 왜 배송비 추가지역만 해요?**

1. github의 트래픽 제한
2. 배송비 추가지역은 자주 변동되지만, 그 외 안내사항은 잘 안 바뀔 것이라는 안이한 생각




# 사용방법

상세페이지의 html 에디터의 다음 코드를 삽입합니다.

```
    <div id="delivery-info"></div>
    <script>
    fetch('https://best15993232-sudo.github.io/notice/파일명.html')
      .then(function(r) { return r.text(); })
      .then(function(html) {
        document.getElementById('delivery-info').innerHTML = html;
      });
    </script>
```

