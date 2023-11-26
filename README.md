# chromium-apps
Chromium Apps is the successor of the GoogleChromeLabs/carlo project.

Chromium Apps are build out of 2 main components a posix compatible shell and the chromium browser project.

Alternativ you can use a websocket client and the chromium browser project. depending on your needs this can get quit complex and is Enterprise stuff.

Look into the Exampels folder to get started we will use Puppeteer and NodeJS for the most examples so you can easyer adopt the patterns if your 
familar with them.

## We have tons of Distribution ways

### Greenfild patterns

#### Web Installer
- detect if running in chrome compatible browser already
- if so use FileSystem Access API to install node give node

https://download-chromium.appspot.com/ go to the url download and install chromium 
