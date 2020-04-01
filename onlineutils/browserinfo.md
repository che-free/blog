---
title: "Browser information"
---

## Browser information

| Attribute | Values |
|--|--|
| Screen size | <span id="screen-size">-</span> |
| Browser(window) size | <span id="browser-window-size">-</span> |
| Browser(document) size | <span id="browser-document-size">-</span> |
| Color depth | <span id="color-depth">-</span> |
| html font-size | <span id="html-font-size">-</span> |
| body font-size | <span id="body-font-size">-</span> |
| Browser Language | <span id="browser-language">-</span> |
| User-agent | <span id="user-agent">-</span> |
| IP address | <span id="ip-address">-</span> |

<script>
(function() {
    function getBrowserWidth() {
        return Math.max(
                document.body.scrollWidth,
                document.documentElement.scrollWidth,
                document.body.offsetWidth,
                document.documentElement.offsetWidth,
                document.documentElement.clientWidth
            );
    }

    function getBrowserHeight() {
        return Math.max(
                document.body.scrollHeight,
                document.documentElement.scrollHeight,
                document.body.offsetHeight,
                document.documentElement.offsetHeight,
                document.documentElement.clientHeight
            );
    }

    try {
        $("#body-font-size").text(window.getComputedStyle(document.body).getPropertyValue('font-size'));
        $("#html-font-size").text(window.getComputedStyle(document.getElementsByTagName("html")[0]).getPropertyValue('font-size'));
        $("#browser-size").text(getBrowserWidth() + " x " + getBrowserHeight());
        $("#browser-document-size").text($(window).width() + " x " + $(window).height());
        $("#browser-window-size").text($(window).width() + " x " + $(window).height());
        $("#screen-size").text(window.screen.width + " x " + window.screen.height);
        $("#user-agent").text(window.navigator.userAgent);
        $("#browser-language").text(navigator.language || navigator.userLanguage);
        $("#color-depth").text(screen.colorDepth + " bit");

        $.ajax("https://api.ipify.org?format=json")
            .done(function(data) {
                $("#ip-address").text(data.ip);
            })
            .fail(function() {
                $("#ip-address").text("unknown");
            });
    } catch (e) {
    }
})();
</script>
