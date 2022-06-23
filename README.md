# Important: Versioning

We use SemVer versioning convention. The key component to check the version is this one, PixelCore. The meaning of the version numbers for PixelCore is described below.

**Component: PixelCore**\
Version: XX.YY.ZZ

XX: Major version number, changes unfrequently, assumes significant shift of the architecture/desing apporach/other things.\
YY: Minor version number, indicates Database Structure Version, which usually indicates an adjustment version to the Database Structure. 
Different Minor versions may not be compatible, however the overall architecture approach is still the same. Major/Minor Version pair should be checked by other PixelCore  
components to make sure that PixelCore DB Structure is what it is expected to be. \
ZZ. Patch version number, indicates some non-braking change of software or scripts or anything else, which doesn't touch PixelCore DB structure. Serves mainly for 
informational purpose.


**Component: All other Components beside PixelCore**\
Version: XX.YY.ZZ 

XX.YY: Major/Mijor which indicates which PixelCore Version is required to run this Component.\
ZZ. Patch version number, which indicates some improvement of functionality of the Component.

**Example 1**\
PixelCore: 3.0.1\
Dispatcher: 3.0.5\
Comment: Dispatcher version indicates that it is supposed to run with Version 3.0.x of the PixelCore. This combination of Versions is valid.

**Example 2**\
PixelCore: 3.0.1\
Dispatcher: 3.1.2\
Comment: Dispatcher version indicates that it is supposed to run with Version 3.1.x of the PixelCore. This combination of Versions is not valid.

# pix-timescaledb

Scripts to compose pix-timescaledb image based on timescaledb:2.0.0-pg12 with database init scripts

## Build

```
make docker
```

## Release version

```
make version
```

This command will increment `VERSION`, tag the repository, then build docker image and publish it to `pixelcore.azurecr.io`.
