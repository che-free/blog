---
title: "HTML 폰트 크기 변경"
---

## HTML 기본 폰트 크기 변경

```css
html {
    font-size: 16px;
}
```

<div class="text-center">
    현재 폰트 크기 : <span id="html-font-size">-</span>
    <hr>
    <button id="decrease-font-size" type="button" class="btn btn-outline-primary btn-lg m-3">줄이기(-)</button>
    <button id="increase-font-size" type="button" class="btn btn-outline-primary btn-lg m-3">키우기(+)</button>
</div>

<script>
    (function() {
        function getHtmlFontSize() {
            //return window.getComputedStyle(document.getElementsByTagName("html")[0]).getPropertyValue('font-size');
            return $("html").css("font-size");
        }

        function getHtmlFontSizeValue() {
            return parseFloat(getHtmlFontSize().replace("px", ""));
        }

        function decreaseFontSize() {
            var fontSize = getHtmlFontSizeValue();

            if (fontSize > 5) {
                fontSize--;

                $("html").css("font-size", fontSize + "px");
                $("#html-font-size").text(getHtmlFontSize());
            }
        }

        function increaseFontSize() {
            var fontSize = getHtmlFontSizeValue();

            if (fontSize < 32) {
                fontSize++;

                $("html").css("font-size", fontSize + "px");
                $("#html-font-size").text(getHtmlFontSize());
            }
        }

        $("#html-font-size").text(getHtmlFontSize());

        $("#decrease-font-size").on("click", function() {
            decreaseFontSize();
        });

        $("#increase-font-size").on("click", function() {
            increaseFontSize();
        });

        $(window).keypress(function( event ) {
            if (event.which == 45) {
                // "-"
                decreaseFontSize();
            } else if(event.which == 43) {
                // "+"
                increaseFontSize();
            }
        });
    })();
</script>
