---
title: Exemples
description: 
published: true
date: 2021-11-12T20:44:31.445Z
tags: 
editor: markdown
dateCreated: 2021-10-29T17:38:51.241Z
---

## Date et heure
```js
/* Date et Heure */
new Date().toLocaleString();
// 16/07/2021 à 17:49:08

/* Date */
new Date().toLocaleDateString();
// 16/07/2021

/* Heure */
new Date().toLocaleTimeString();
// 17:49:08

/* Date et Heure Formatées */
function DateTimeFormat() {
  var DateTimeFormat = new Date();

  var DateFormat = DateTimeFormat.toLocaleDateString("fr-FR", {
    weekday: "long",
    year: "numeric",
    month: "long",
    day: "numeric",
  });

  var TimeFormat = DateTimeFormat.toLocaleTimeString().split(":", 2).join(":");

  console.log(DateFormat + " " + TimeFormat);
}

DateTimeFormat();
// vendredi 16 juillet 2021 17:48

```  

## Afficher le navigateur
```js
navigator.sayswho = (function () {
  var ua = navigator.userAgent,
    tem,
    M =
      ua.match(
        /(opera|chrome|safari|firefox|msie|trident(?=\/))\/?\s*(\d+)/i
      ) || [];
  if (/trident/i.test(M[1])) {
    tem = /\brv[ :]+(\d+)/g.exec(ua) || [];
    return "IE " + (tem[1] || "");
  }
  if (M[1] === "Chrome") {
    tem = ua.match(/\b(OPR|Edge)\/(\d+)/);
    if (tem != null) return tem.slice(1).join(" ").replace("OPR", "Opera");
  }
  M = M[2] ? [M[1], M[2]] : [navigator.appName, navigator.appVersion, "-?"];
  if ((tem = ua.match(/version\/(\d+)/i)) != null) M.splice(1, 1, tem[1]);
  return M.join(" ");
})();

return navigator.sayswho;
```

## Afficher l'OS
```js
function getOS() {
  var userAgent = window.navigator.userAgent,
    platform = window.navigator.platform,
    macosPlatforms = ["Macintosh", "MacIntel", "MacPPC", "Mac68K"],
    windowsPlatforms = ["Win32", "Win64", "Windows", "WinCE"],
    iosPlatforms = ["iPhone", "iPad", "iPod"],
    os = null;

  if (macosPlatforms.indexOf(platform) !== -1) {
    os = "Mac OS";
  } else if (iosPlatforms.indexOf(platform) !== -1) {
    os = "iOS";
  } else if (windowsPlatforms.indexOf(platform) !== -1) {
    os = "Windows";
  } else if (/Android/.test(userAgent)) {
    os = "Android";
  } else if (!os && /Linux/.test(platform)) {
    os = "Linux";
  }

  return os;
}
return getOS();
```

## Convertiseur de taille
```js
export const convertKo = (number) => {
    const x = number;
    let res;

    if (x >= Math.pow(1024, 3))
        res = Math.round(x / Math.pow(1024, 3)) + " To";
    else if (x >= Math.pow(1024, 2))
        res = Math.round(x / Math.pow(1024, 2)) + " Go";
    else if (x >= 1024) res = Math.round(x / 1024) + " Mo";
    else res = x + " Ko";

    return res;
}
```



