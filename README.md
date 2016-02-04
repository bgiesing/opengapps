Getting the latest Open GApps
---------------
The latest version of pre-built Open GApps can be found at http://opengapps.org

Build your own Open GApps
---------------
If you want to build your own version of Open GApps, you'll need to get the git sources:

To initialize your local repository using the Open GApps source tree, use a command like:
```
git clone --recursive git@github.com:opengapps/opengapps.git
```
Then to update the sources later to the most recent version:
```
./download_sources.sh [--shallow] [arch]
```
* ```--shallow``` will order to fetch only the latest snapshot of the APKs (reduces space used and amount of data to be retrieved by git, by not fetching the APKs' history)
* ```arch``` can be one of the following "arm, arm64, x86, x86_64" to fetch only data required for specified architecture (note that fallback architectures will be be fetched too)

To build Open GApps for all platforms and all android releases:
```
make
```
To build Open GApps for a specific android release on a specific platform,
define both the platform and the API level of that release, seperated by a dash and optionally add the variant with another dash.
Two (most widely used) examples:
```
make arm-22
```
or
```
make arm-22-stock
```
To add updated source APKs to the sources archive (you can add more than one at once):
```
./add_sourceapp.sh [/path/to/the/files/you/want/to/add.apk]* [beta] [/apps/that/should/be/marked/as/beta.apk...]*
```
For contributors, updated sources can be uploaded by using this command:
```
./upload_sources.sh
```
If you want an overview of the locally available sources:
```
./report_sources.sh
```
