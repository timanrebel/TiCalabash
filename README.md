## This is beta software ##
 the single biggest reason is because of the ruby dependency
if you  do not have either rvm or rbenv installed then you may have issues installing this package
 system ruby for mac can have issues
 the designation from beta to full production is a high priority and moving quickly.

# TiCalabash Package

[![NPM](https://nodei.co/npm/ticalabash.png)](https://nodei.co/npm/ticalabash/)

Yes. Calabash for Appcelerator Titanium (vanilla and Alloy) iOS and Android
This includes to physical devices as well as Simulators/Emulators

## Getting Started
Install the module with: `npm install -g ticalabash`

Don't use `sudo`, because it is bad practise and will break the installation process. It's better to correctly set the permissions on the `/usr/local` directory instead, so you don't have to ever use `sudo` again when installing npm packages.

```
sudo chown -R $USER /usr/local
```

## Examples
`ti calabash --platform=[android,ios] `

## Documentation
Because TiCalabash is wrapping [Calabash](http://calaba.sh), please use Calabash's documentation to learn how to use Calabash together with [Cucumber](http://cukes.info):
* [Calabash iOS documentation](https://github.com/calabash/calabash-ios/wiki/00-Calabash-iOS-documentation)
* [Calabash Android documentation](https://github.com/calabash/calabash-android/blob/master/README.md)

(The iOS documentation is far superior to the Android documentation and is mostly valid for Android as well). 

If you don't have a features directory at the project root level, it will be created.
The calabash command will rebuild your android or iOS binary every time.

**Querying your UI**
* On [iOS](https://github.com/calabash/calabash-ios/wiki/05-Query-syntax)
* On [Android](http://blog.lesspainful.com/2012/12/18/Android-Query/ )
 
**Recording Touches**

Recording of touches is currently not supported, for two reasons:
* It does not work anymore with Calabash iOS on iOS 7+ 
* Has never been implemented in Calabash Android

## Presentation
The following slide deck may be of use: [TiCalabash: Fully automated Acceptance Testing @ TiConf EU 2014](http://www.slideshare.net/sophrinix/ticalabash-fully-automated-testing-ticonf-eu-2014)

## Jenkins configuration
If you want to integrate TiCalabash in Jenkins, use the following configuration:
```
cd ~/Desktop/ticonf2014testappdemo/alloytest # or actually pull from git. 
titanium clean titanium build --platform=iphone --test & 
sleep 30 
killall "iPhone Simulator" 

export PATH=“/Users/andrewmcelroy/.rbenv/shims:/Users/andrewmcelroy/bin:/usr/local/bin: /Users/andrewmcelroy/.rbenv/bin:/Users/andrewmcelroy/android/tools:/Users/andrewmcelroy/android/: /Users/andrewmcelroy/android//tools:/Users/andrewmcelroy/android/platform-tools/:/usr/bin:/bin: /usr/sbin:/sbin:/usr/local/bin:/usr/local/git/bin:" 

echo | titanium calabash —platform=iphone
cd ~/Library/Application Support/iPhone Simulator/7.1/Applications/ 
AppGUID = $(ﬁnd . -name "alloytest" | cut -d "/" -f 2) 

cp "~/Library/Application Support/iPhone Simulator/7.1/Applications/$AppGUID/Documents/jenkins.xml" $WORKSPACE/jenkins.xml
```

Make sure you replace the folders with the actual folders on your system.

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality.

## Release History
1.0.4 - Added Sample features
1.0.0 - TiCalabash wraps calabash


## License
License: MIT (c) 2014
Matt Apperson / Apperson Labs
Andrew McElroy / Codex Labs, LLC
