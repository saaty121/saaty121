var Siloti = document.querySelector("#nagri");
var Siletin = document.querySelector("#siletin");
var Siletern = document.querySelector("#bangla");

var sylotiGlyphs = [
  {
    "ꠀ": "a": "আ",
    "ꠁ": "i": "ই",
    "ꠃ": "u": "উ",
    "ꠄ": "e": "এ",
    "ꠅ": "o": "ও",
    "ꠇ": "k": "ক",
    "ꠈ": "x": "খ",
    "ꠉ": "g": "গ",
    "ꠊ": "gw": "ঘ",
    "ꠋ": "z": "ং",
    "ꠌ": "c": "চ",
    "ꠍ": "s": "ছ",
    "ꠎ": "j": "জ",
    "ꠏ": "jw": "ঝ",
    "ꠐ": "t": "ট",
    "ꠑ": "tq": "ঠ",
    "ꠒ": "d": "ড",
    "ꠓ": "dq": "ঢ",
    "ꠔ": "tv": "ত",
    "ꠕ": "tw": "থ",
    "ꠖ": "dv": "দ",
    "ꠗ": "dw": "ধ",
    "ꠘ": "n": "ন",
    "ꠙ": "p": "প",
    "ꠚ": "f": "ফ",
    "ꠛ": "b": "ব",
    "ꠜ": "bw": "ভ",
    "ꠝ": "m": "ম",
    "ꠞ": "r": "র",
    "ꠟ": "l": "ল",
    "ꠡ": "sy": "শ",
    "ꠢ": "h": "হ",
    "ꠠ": "ry": "ড়",
   "꠆" : "": "্", // হসচিহ্ন
   "ꠣ" : "a": "া", // আ-কার
   "ꠤ" : "i": "ি", // ই-কার
   "ꠥ" : "u": "ু", // উ-কার
   "ꠦ" : "e": "ে", // এ-কার
   "ꠧ" : "o": "ো", // ও-কার
   "ꠂꠂ" : "oi": "ৈ"

    "*": ".": "।", // দাঁড়ি
    "॥": "॥": "॥", // দ্বৈত দাঁড়ি
    " ": " ": " ", // space, ফাঁকা স্থান
  },
];

/**
 * Handle Nagri Inputs.
 */
nagri.addEventListener("keyup", function (e) {
  var sylotiGlyphs = "";

  var str = this.value;
  for (var i = 0; i < str.length; i++) {
    for (var key in sylotiGlyphs) {
      // console.warn(str[i], " - ", typeof sylotiGlyphs[key][str[i]]);
      if ("undefined" !== typeof sylotiGlyphs[key][str[i]]) {
        sylotiGlyphs += sylotiGlyphs[key][str[i]];
      } else {
        sylotiGlyphs += str[i];
      }
    }
  }
  syloti.value = sylotiGlyphs;
});
