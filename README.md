# Child launcher
A web launcher for young child (4 ~ 5 years) used with a navigator in kioske mode.
There is an editable text field, where child can learn to use keyboard.

## My setup
A raspberry PI connected to TV and configured to launch Chromium in kiok mode (full screan with out menu) at startup:
```
chromium-browser /path/to/child_launcher.html --kiosk
```
More info could be find at [sylvain durand web site](https://sylvaindurand.org/launch-chromium-in-kiosk-mode/)

## Dev
clone this repository
```
git clone https://github.com/europrimus/child_web_launcher.git
```

install packages
```
npm install
```
