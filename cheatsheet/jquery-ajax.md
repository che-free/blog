---
title: "jQuery - ajax"
---

jQuery에서 ajax 사용 정리.


## done, fail, always 콜백을 이용하는 방법
```
$.ajax("https://httpbin.org/get")
    .done(function(data, textStatus, jqXHR) {
        console.log("done", data);
    })
    .fail(function(jqXHR, textStatus, errorThrown) {
        console.log("fail", jqXHR);
    })
    .always(function() {
        console.log("always");
    });
```

## success, error, complete 콜백을 이용하는 방법
> Deprecation Notice: The jqXHR.success(), jqXHR.error(), and jqXHR.complete() callbacks are removed as of jQuery 3.0. You can use jqXHR.done(), jqXHR.fail(), and jqXHR.always() instead.

```
$.ajax({
    url     : "https://httpbin.org/get",
    success : function(data, textStatus, jqXHR) {
        console.log("success", data);
    },
    error : function(jqXHR, textStatus, errorThrown) {
        console.log("error", jqXHR);
    },
    complete : function(jqXHR, textStatus) {
        console.log("complete", jqXHR);
    }
});
```

<script>
</script>

## POST, JSON 데이터 전송
```
$.ajax({
    url     : "https://httpbin.org/post",
    type    : "POST",
    contentType: "application/json",
    data    : JSON.stringify({"p1":"v1", "p2":"v2"}),
    dataType: "json",
    success : function(data, textStatus, jqXHR) {
        console.log("success", data);
    },
    error : function(jqXHR, textStatus, errorThrown) {
        console.log("error", jqXHR);
    },
    complete : function(jqXHR, textStatus) {
        console.log("complete", jqXHR);
    }
});
```

<script>
</script>


## 참고 사이트
- [jQuery.ajax()](https://api.jquery.com/jquery.ajax/){: target="_blank"}
- [REST test test...](https://resttesttest.com/){: target="_blank"}
- [httpbin.org](https://httpbin.org/){: target="_blank"}
