---
title: "LATERRE BLOG HOME"
description: "환영합니다 라테르 기술 블로그 입니다."
---

<script>
  var typeText = document.querySelector(".typeText")
  var textToBeTyped = "Hello, World"
  var textToBeTypedArr = ["Java", "Spring", "Rust", "Kotlin"]
  var index = 0, isAdding = true, textToBeTypedIndex = 0
  
  function playAnim() {
    setTimeout(function () {
      // set the text of typeText to a substring of the text to be typed using index.
      typeText.innerText = textToBeTypedArr[textToBeTypedIndex].slice(0, index)
      if (isAdding) {
        // adding text
        if (index > textToBeTypedArr[textToBeTypedIndex].length) {
          // no more text to add
          isAdding = false
          //break: wait 2s before playing again
          setTimeout(function () {
            playAnim()
          }, 2000)
          return
        } else {
          // increment index by 1
          index++
        }
      } else {
        // removing text
        if (index === 0) {
          // no more text to remove
          isAdding = true
          //switch to next text in text array
          textToBeTypedIndex = (textToBeTypedIndex + 1) % textToBeTypedArr.length
        } else {
          // decrement index by 1
          index--
        }
      }
      // call itself
      playAnim()
    }, isAdding ? 120 : 60)
  }
  // start animation
  playAnim()
</script>

<div class="flex px-4 py-2 mb-8 text-base rounded-md bg-primary-100 dark:bg-primary-900">
  <span class="flex items-center ltr:pr-3 rtl:pl-3 text-primary-400">
    {{< icon "code" >}}
  </span>
  <span class="flex items-center justify-between grow dark:text-neutral-300">
    <span class="prose dark:prose-invert typo-idx">
      <p class="typeText"></p>
    </span>
  </span>
</div>

다양한 것을 배우고 `좋은 개발 경험`을 얻기 위해 항상 도전하고 있습니다.

주로 `자바`와 `스프링` 그리고 `서버`를 다루고 있습니다.
요즘은 `코틀린`, `러스트`와 `Node.JS`에 관심이 많습니다.