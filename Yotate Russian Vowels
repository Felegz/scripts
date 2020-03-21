// ==UserScript==
// @name        Yotate Russian Vowels
// @description replace all Russian with letter Ё
// @include *
// @exclude *google*
// @exclude *yandex*
// @version     0.1
// @grant       none
// Based on code by istepaniuk:  xkcd-substitutions https://github.com/istepaniuk/xkcd-substitutions/
// https://github.com/Felegz/
// ==/UserScript==
(function() {
    var substitutions,
        textNodes,
        regexps = {};

    substitutions = {
        "[АИОУЫЭЮЯ]":"Ё",
        "[ауоыиэяюёе]":"ё",



    }

    for (var key in substitutions) {
        regexps[key] = new RegExp(key, 'g');
    }

    textNodes = document.evaluate("//text()", document, null, XPathResult.UNORDERED_NODE_SNAPSHOT_TYPE, null);
    for (var i = 0; i < textNodes.snapshotLength; i++) {
        var node = textNodes.snapshotItem(i);
        node.data = substituteTextIn(node.data);
    }

    function substituteTextIn(text) {
        for (var key in substitutions) {
            text = text.replace(regexps[key], substitutions[key]);
        }
        return text;
    }

})();
