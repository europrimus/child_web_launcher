# Child launcher
A web launcher for young child (4 ~ 5 years) used with a navigator in kioske mode.
There is an editable text field, where child can learn to use keyboard.

links are saved in localstorage **links** as JSON
```
[
  {
    "url":"https://www.films-pour-enfants.com/",
    "img":"https://www.films-pour-enfants.com/films-pour-enfants/films-pour-enfants-logo-white.png"
  }
]
```

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

## TODO
- admin panel to manage links
- words protect links: need to type one or more words to unlock links section
- read links from json file to complete those from localStorage
