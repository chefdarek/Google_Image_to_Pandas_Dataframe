# Google_Image_to_Pandas_Dataframe
Input search terms output labeled pandas dataframe of images in np.arrays

Skip to content
Pull requests
Issues
Marketplace
Explore
@chefdarek

1
0

    0

chefdarek/Google_Image_to_Pandas_Dataframe
Code
Issues 0
Pull requests 0
Projects 0
Wiki
Security
Insights
Settings
Google_Image_to_Pandas_Dataframe/Dareks_Pic_Script_Extroirdinaire.html
@chefdarek chefdarek Add files via upload 8f2ce49 3 minutes ago
13477 lines (13380 sloc) 540 KB
<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>Dareks_Pic_Script_Extroirdinaire</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:
    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+
Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*
Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme
*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }
.ansi-bold { font-weight: bold; }
    </style>
<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}
div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>
<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">
<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/latest.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#pip install google_images_download</span>
</pre></div>
    </div>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># importing google_images_download module </span>
<span class="kn">from</span> <span class="nn">google_images_download</span> <span class="k">import</span> <span class="n">google_images_download</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">matplotlib.image</span> <span class="k">as</span> <span class="nn">mpimg</span>
<span class="kn">import</span> <span class="nn">os</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">from</span> <span class="nn">PIL</span> <span class="k">import</span> <span class="n">Image</span>
<span class="kn">import</span> <span class="nn">os</span><span class="o">,</span> <span class="nn">os.path</span>
<span class="n">path_string</span> <span class="o">=</span> <span class="s2">&quot;D:/Githubrepos/DS-Unit-4-Sprint-2-Neural-Networks/downloads/&quot;</span>
<span class="k">class</span> <span class="nc">GoogleImage_to_Labeled_Df</span><span class="p">(</span><span class="nb">object</span><span class="p">):</span>
      
    <span class="k">def</span> <span class="nf">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">list_of_labels</span><span class="p">,</span> <span class="n">limit</span><span class="p">,</span> <span class="n">path_string</span><span class="p">,</span> <span class="n">size_string</span><span class="o">=</span><span class="s2">&quot;medium&quot;</span><span class="p">,</span> <span class="n">response</span> <span class="o">=</span> <span class="n">google_images_download</span><span class="o">.</span><span class="n">googleimagesdownload</span><span class="p">()):</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span> <span class="o">=</span> <span class="n">list_of_labels</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">size_string</span> <span class="o">=</span> <span class="n">size_string</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">limit</span> <span class="o">=</span> <span class="n">limit</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">path_string</span> <span class="o">=</span> <span class="n">path_string</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">response</span> <span class="o">=</span> <span class="n">response</span>
    
        
    <span class="k">def</span> <span class="nf">downloadimages</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">query</span><span class="p">):</span> 
        <span class="c1"># keywords is the search query </span>
        <span class="c1"># format is the image file format </span>
        <span class="c1"># limit is the number of images to be downloaded </span>
        <span class="c1"># print urs is to print the image file url </span>
        <span class="c1"># size is the image size which can </span>
        <span class="c1"># be specified manually (&quot;large, medium, icon&quot;) </span>
        <span class="c1"># aspect ratio denotes the height width ratio </span>
        <span class="c1"># of images to download. (&quot;tall, square, wide, panoramic&quot;)</span>
        <span class="c1"># no_numbering if removed will enumerate the files but with a . after and break the class</span>
        <span class="n">arguments</span> <span class="o">=</span> <span class="p">{</span><span class="s2">&quot;keywords&quot;</span><span class="p">:</span> <span class="n">query</span><span class="p">,</span> 
                     <span class="s2">&quot;format&quot;</span><span class="p">:</span> <span class="s2">&quot;jpg&quot;</span><span class="p">,</span> 
                     <span class="s2">&quot;limit&quot;</span><span class="p">:</span><span class="bp">self</span><span class="o">.</span><span class="n">limit</span><span class="p">,</span> 
                     <span class="s2">&quot;print_urls&quot;</span><span class="p">:</span><span class="kc">False</span><span class="p">,</span> 
                     <span class="s2">&quot;size&quot;</span><span class="p">:</span> <span class="bp">self</span><span class="o">.</span><span class="n">size_string</span><span class="p">,</span> 
                     <span class="s2">&quot;aspect_ratio&quot;</span><span class="p">:</span> <span class="s2">&quot;square&quot;</span><span class="p">,</span>
                     <span class="s2">&quot;no_numbering&quot;</span><span class="p">:</span><span class="s2">&quot;-nn&quot;</span><span class="p">}</span> 
        <span class="k">try</span><span class="p">:</span> 
            <span class="bp">self</span><span class="o">.</span><span class="n">response</span><span class="o">.</span><span class="n">download</span><span class="p">(</span><span class="n">arguments</span><span class="p">)</span> 
        <span class="c1"># Handling File NotFound Error     </span>
        <span class="k">except</span> <span class="ne">FileNotFoundError</span><span class="p">:</span>  
            <span class="n">arguments</span> <span class="o">=</span> <span class="p">{</span><span class="s2">&quot;keywords&quot;</span><span class="p">:</span> <span class="n">query</span><span class="p">,</span> 
                         <span class="s2">&quot;format&quot;</span><span class="p">:</span> <span class="s2">&quot;jpg&quot;</span><span class="p">,</span> 
                         <span class="s2">&quot;limit&quot;</span><span class="p">:</span><span class="bp">self</span><span class="o">.</span><span class="n">limit</span><span class="p">,</span> 
                         <span class="s2">&quot;print_urls&quot;</span><span class="p">:</span><span class="kc">False</span><span class="p">,</span>  
                         <span class="s2">&quot;size&quot;</span><span class="p">:</span> <span class="bp">self</span><span class="o">.</span><span class="n">size_string</span><span class="p">}</span> 
            <span class="c1"># Providing arguments for the searched query </span>
            <span class="k">try</span><span class="p">:</span> 
                <span class="c1"># Downloading the photos based </span>
                <span class="c1"># on the given arguments </span>
                <span class="n">response</span><span class="o">.</span><span class="n">download</span><span class="p">(</span><span class="n">arguments</span><span class="p">)</span>  
            <span class="k">except</span><span class="p">:</span> 
                <span class="k">pass</span>
    
    <span class="k">def</span> <span class="nf">rename_files</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">filename_string</span><span class="p">,</span> <span class="n">path</span><span class="p">):</span>
        <span class="c1">#renames the files with the correc labels</span>
        <span class="n">i</span> <span class="o">=</span> <span class="mi">0</span>
        <span class="k">for</span> <span class="n">filename</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">path</span><span class="p">):</span> 
            <span class="n">dst</span> <span class="o">=</span> <span class="n">filename_string</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">i</span><span class="p">)</span> <span class="o">+</span> <span class="s2">&quot;.jpg&quot;</span>
            <span class="n">src</span> <span class="o">=</span> <span class="n">path</span> <span class="o">+</span> <span class="n">filename</span> 
            <span class="n">dst</span> <span class="o">=</span> <span class="n">path</span> <span class="o">+</span> <span class="n">dst</span> 
            <span class="c1"># rename() function will </span>
            <span class="c1"># rename all the files </span>
            <span class="n">os</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">src</span><span class="p">,</span> <span class="n">dst</span><span class="p">)</span> 
            <span class="n">i</span> <span class="o">+=</span> <span class="mi">1</span>
            
    <span class="k">def</span> <span class="nf">rename_loop</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
        <span class="n">imgs</span> <span class="o">=</span> <span class="p">[]</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span><span class="s1">&#39;image_arrays&#39;</span> <span class="p">:</span> <span class="p">[],</span> <span class="s1">&#39;label&#39;</span> <span class="p">:</span> <span class="p">[]})</span>
        <span class="n">valid_images</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;.jpg&quot;</span><span class="p">]</span>
            <span class="c1">#loop through queries and paths to apply rename</span>
        <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span><span class="p">)):</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">paths</span> <span class="o">=</span> <span class="p">[]</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">paths</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">path_string</span> <span class="o">+</span> <span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">+</span> <span class="s2">&quot;/&quot;</span><span class="p">)</span>
            <span class="k">for</span> <span class="n">p</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">paths</span><span class="p">:</span>
                    <span class="bp">self</span><span class="o">.</span><span class="n">rename_files</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span><span class="p">[</span><span class="n">i</span><span class="p">],</span> <span class="n">p</span><span class="p">)</span>
                        
                        
    <span class="k">def</span> <span class="nf">get_images</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
        <span class="c1"># Driver Code </span>
        <span class="k">for</span> <span class="n">query</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span><span class="p">:</span> 
            <span class="bp">self</span><span class="o">.</span><span class="n">downloadimages</span><span class="p">(</span><span class="n">query</span><span class="p">)</span>  
            <span class="nb">print</span><span class="p">()</span>
            
    <span class="k">def</span> <span class="nf">make_df</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
    
        <span class="bp">self</span><span class="o">.</span><span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span><span class="s1">&#39;image_arrays&#39;</span> <span class="p">:</span> <span class="p">[],</span> <span class="s1">&#39;label&#39;</span> <span class="p">:</span> <span class="p">[]})</span>
        <span class="n">valid_images</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;.jpg&quot;</span><span class="p">,</span><span class="s2">&quot;.&quot;</span><span class="p">]</span>
        <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span><span class="p">)):</span>
            <span class="k">for</span> <span class="n">f</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">path_string</span> <span class="o">+</span> <span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span><span class="p">[</span><span class="n">i</span><span class="p">]):</span>
                <span class="n">imgs</span> <span class="o">=</span> <span class="p">[]</span>
                <span class="n">ext</span> <span class="o">=</span> <span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">splitext</span><span class="p">(</span><span class="n">f</span><span class="p">)[</span><span class="mi">1</span><span class="p">]</span>
                <span class="k">if</span> <span class="n">ext</span><span class="o">.</span><span class="n">lower</span><span class="p">()</span> <span class="ow">not</span> <span class="ow">in</span> <span class="n">valid_images</span><span class="p">:</span>
                    <span class="k">continue</span>
                <span class="n">imgs</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">Image</span><span class="o">.</span><span class="n">open</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">path_string</span> <span class="o">+</span> <span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">+</span> <span class="s2">&quot;/&quot;</span> <span class="o">+</span> <span class="n">f</span><span class="p">))</span>
                <span class="k">for</span> <span class="n">ims</span> <span class="ow">in</span> <span class="n">imgs</span><span class="p">:</span>
                    <span class="n">x</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">ims</span><span class="p">)</span>
                    <span class="bp">self</span><span class="o">.</span><span class="n">df</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">df</span><span class="o">.</span><span class="n">append</span><span class="p">({</span><span class="s1">&#39;image_arrays&#39;</span> <span class="p">:</span> <span class="n">x</span><span class="p">,</span> <span class="s1">&#39;label&#39;</span><span class="p">:</span> <span class="bp">self</span><span class="o">.</span><span class="n">search_queries</span><span class="p">[</span><span class="n">i</span><span class="p">]}</span> <span class="p">,</span> <span class="n">ignore_index</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">f</span><span class="s2">&quot;Labeled DataFrame Complete with </span><span class="si">{self.df.shape[0]}</span><span class="s2"> rows and </span><span class="si">{self.df.shape[1]}</span><span class="s2"> columns&quot;</span><span class="p">)</span>
        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
    
    <span class="k">def</span> <span class="nf">show_image</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span><span class="n">row_number</span><span class="p">):</span>
        <span class="c1">#takes in a row number and saves/returns the picture from the np.array row</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">img</span> <span class="o">=</span> <span class="n">Image</span><span class="o">.</span><span class="n">fromarray</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">df</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="n">row_number</span><span class="p">][</span><span class="mi">0</span><span class="p">])</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">img</span><span class="o">.</span><span class="n">save</span><span class="p">(</span><span class="n">f</span><span class="s2">&quot;output</span><span class="si">{row_number}</span><span class="s2">_{str(self.df.label[row_number])}.png&quot;</span><span class="p">)</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">img</span><span class="p">)</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>
    </div>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">cows_bats</span> <span class="o">=</span> <span class="n">GoogleImage_to_Labeled_Df</span><span class="p">([</span><span class="s2">&quot;cows&quot;</span><span class="p">,</span><span class="s2">&quot;bats&quot;</span><span class="p">],</span> <span class="mi">3</span><span class="p">,</span> <span class="n">path_string</span><span class="p">)</span>
</pre></div>
    </div>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">cows_bats</span><span class="o">.</span><span class="n">get_images</span><span class="p">()</span>
<span class="n">cows_bats</span><span class="o">.</span><span class="n">rename_loop</span><span class="p">()</span>
<span class="n">cows_bats</span><span class="o">.</span><span class="n">make_df</span><span class="p">()</span>
</pre></div>
    </div>
</div>
</div>
<div class="output_wrapper">
<div class="output">
<div class="output_area">
    <div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>
Item no.: 1 --&gt; Item name = cows
Evaluating...
Starting Download...
Completed Image ====&gt; 1.17-cow.w700.h700.jpg
Completed Image ====&gt; 2.13797_main_v16_tp.jpg
Completed Image ====&gt; 3.Holstein-Cow-Headshot.jpg
Errors: 0
Item no.: 1 --&gt; Item name = bats
Evaluating...
Starting Download...
Completed Image ====&gt; 1.bat_rodrigues_baby.jpg
Completed Image ====&gt; 2.27-bats.w700.h700.jpg
Completed Image ====&gt; 3.P-brandts-bat.jpg
Errors: 0
Labeled DataFrame Complete with 6 rows and 2 columns
</pre>
</div>
</div>
<div class="output_area">
    <div class="prompt output_prompt">Out[6]:</div>
<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }
    .dataframe tbody tr th {
        vertical-align: top;
    }
    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>image_arrays</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>[[[255, 255, 255], [255, 255, 255], [255, 255,...</td>
      <td>cows</td>
    </tr>
    <tr>
      <th>1</th>
      <td>[[[71, 139, 200], [74, 140, 201], [76, 140, 20...</td>
      <td>cows</td>
    </tr>
    <tr>
      <th>2</th>
      <td>[[[204, 216, 240], [198, 210, 236], [196, 210,...</td>
      <td>cows</td>
    </tr>
    <tr>
      <th>3</th>
      <td>[[[165, 199, 244], [163, 200, 244], [164, 201,...</td>
      <td>bats</td>
    </tr>
    <tr>
      <th>4</th>
      <td>[[[134, 163, 73], [134, 163, 73], [135, 164, 7...</td>
      <td>bats</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">cows_bats</span><span class="o">.</span><span class="n">show_image</span><span class="p">(</span><span class="mi">2</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">cows_bats</span><span class="o">.</span><span class="n">show_image</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> 
</pre></div>

    </div>
</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>

    © 2019 GitHub, Inc.
    Terms
    Privacy
    Security
    Status
    Help

    Contact GitHub
    Pricing
    API
    Training
    Blog
    About

