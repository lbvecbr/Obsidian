`pkg update`
`pkg install x11-repo`
`pkg install termux-x11`
`nvim ~/.termux/termux.properties`

раскоментировать allow-external-apps = true
[github termux-x11](https://github.com/termux/termux-x11/releases/tag/nightly)
скачать и установить debug.apk

`export XDG_RUNTIME_DIR=${TMPDIR}`
`termux-x11 :1 &`
`env DISPLAY=:1 xfce4-session`

[Youtube](https://youtu.be/lB9eqixqSS8?si=BjuYG-ObUKCcetcI)
