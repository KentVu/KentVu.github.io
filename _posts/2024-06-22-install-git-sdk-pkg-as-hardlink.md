---
layout: post
author: kent
title: Install git sdk package by hardlink
---

Assume you've built a mingw64 package by `makepkg-mingw`, we now have a package
file name like: `mingw-w64-x86_64-neovim-0.9.5-4-any.pkg.tar.zst`.

Here is the script I used:
```shell
tar -tf /usr/src/MINGW-packages/mingw-w64-neovim/mingw-w64-x86_64-neovim-0.9.5-4-any.pkg.tar.zst | grep -v /$ |
	while read f; do
		source="$(cygpath -w /$f)"
		dest="$(cygpath -w '/c/Program Files/Git/'$f)"
		echo "$source => $dest"
		if [ ! -d "$(dirname "$dest")" ]; then
			mkdir -pv "$(dirname "$dest")"
		fi
		cmd <<<"mklink /H \"$dest\" \"$source\""
	done
```
Thanks to this [SO post](https://stackoverflow.com/a/25394801/1562087).
