# Docker usage or other oci

```
// Docker Example
/**
You have to start your process with a pipe for stdin which does not block nor close
when the current input was written through. endless loop which will be piped
bash -c "(while [ 1 ]; do sleep 1; done) | yourProgramToStart"
 */
// https://github.com/andyearnshaw/docketeer/issues/7 , 
// https://github.com/puppeteer/puppeteer/issues/8272#issuecomment-1143365918
// Puppeteer._productName = 'firefox'
// you can replace docker run with docker attach ofcourse
const launchConfigs = {
  dockerExample: { // docker run -i --init --cap-add=SYS_ADMIN --rm ghcr.io/puppeteer/puppeteer:latest /bin/bash -c "google-chrome-stable --headless --remote-debugging-pipe 3<&0 4>&1"
    // product: 'firefox', // if you want to use firefox do not forget the above 
    ignoreDefaultArgs: true, // use only our supplyed args: []
    executablePath: '/usr/bin/docker', // we want to run docker right?
    args: [ 
      // docker arguments
        'run', 
        '--rm',
        '-ti',
        `ghcr.io/puppeteer/puppeteer:latest`,
        `/bin/bash -c /usr/bin/google-chrome`, // spawn tty for pipeSupport
        // end docker arguments
        ...Puppeteer._launcher.defaultArgs({ 
                devtools: false, // devtools auto open needs headless false
                headless: true, // needs to be false if devtools auto open
                userDataDir // needs to get set here no where else is optional
        }),
        // ... restBrowserArgs.

    ],
    pipe: true // default
  },
}

```
