---
layout: post
author: kent
has_cast: true
title: How I installed NeoVim on git-sdk-64?
---

<script src="{{ site.baseurl }}{% link assets/js/asciinema-player.min.js %}"> </script>
<div id="demo"></div>
<script>
//'01:02:03'.split(':').reduce((acc,time) => (60 * acc) + +time);
String.prototype.toSeconds = function () {
  if (!this) return null;
  var hms = this.split(':');
  return (+hms[0]) * 60 * 60 + (+hms[1]) * 60 + (+hms[2] || 0);
}
const player = AsciinemaPlayer.create(
  '{{ site.baseurl }}{% link assets/casts/git-sdk-64-install-neovim.cast %}',
  document.getElementById('demo'),
  {
    //idleTimeLimit: 1000,
    markers: [
      ['0:0:53'.toSeconds(), 'cd'],
      ['0:2:10'.toSeconds(), 'makepkg-mingw'],
      ['0:10:10'.toSeconds(), 'done'],
    ]
  }
);
</script>
- Make sure you're at git sdk promt. (SDK command available)
- cd to MINGW-packages directory.
- [Temporarily](javascript:player.seek({marker: 0});) add official msys2 remote and checkout latest master branch.
- [cd](javascript:player.seek({marker: 0});) to /usr/src/MINGW-packages/mingw-w64-neovim
- run [makepkg-mingw -s](javascript:player.seek({marker: 1});)
