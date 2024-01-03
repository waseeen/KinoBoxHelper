// ==UserScript==
// @name         KinoBox helper
// @version      1.02
// @description  Открывай фильм на KinoDivBox прямо со страницы Кинопоиска!
// @author       waseeen
// @match        https://www.kinopoisk.ru/*
// @icon         https://raw.githubusercontent.com/kinodivbox/kinodivbox.github.io/main/favicon-32x32.png
// @grant        none
// @source       https://github.com/waseeen/KinoBoxHelper/raw/master/kinoBoxHelper.user.js
// ==/UserScript==

(function () {
  "use strict";
  function content() {
    setTimeout(() => {
      let target = document.querySelector("[class*=styles_buttonsContainer]");
      let dupe = document.querySelector("[class*=kinoDivBox]");
      if (dupe) return;
      if (target) {
        let query =
          "https://kinodivbox.github.io/kinodivbox.html?q=" + document.URL;
        var newDiv = document.createElement("div");
        newDiv.classList.add(
          "kinoDivBox",
          "styles_button__tQYKG",
          "style_button__PNtXT",
          "style_buttonSize52__b5OBe",
          "style_buttonAccent__vKDGa"
        );
        newDiv.innerHTML = "Смотреть на KinoBox";
        newDiv.addEventListener(
          "click",
          function () {
            window.open(query);
          },
          false
        );
        target.prepend(newDiv);
      }
    }, 500);
  }

  window.onload = content();
  let url = location.href;
  document.body.addEventListener(
    "click",
    () => {
      requestAnimationFrame(() => {
        url !== location.href && content();
        url = location.href;
      });
    },
    true
  );
})();
