---
title: "URI Encode/Decode"
---

## Plain Text
<textarea id="plain_text" rows="5" class="w-100"></textarea>

## Encoded
<textarea id="encoded_text" rows="5" class="w-100"></textarea>

## Decoded
<textarea id="decoded_text" rows="5" class="w-100"></textarea>

<script>
    $("#plain_text").on("propertychange change keyup paste input", function() {
        $("#encoded_text").val(encodeURIComponent($("#plain_text").val()));
        $("#decoded_text").val(decodeURIComponent($("#encoded_text").val()));
    });

    $("#encoded_text").on("propertychange change keyup paste input", function() {
        $("#decoded_text").val(decodeURIComponent($("#encoded_text").val()));
    });
</script>
