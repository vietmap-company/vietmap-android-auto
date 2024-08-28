# vietmap-android-auto
vietmap-android-auto

License by Vietmap company.

# Distribute document

- Copy the generated aar file and paste to the distribute repository
- Rename the SDK file as below format:
```
VietmapAndroidAutoSDK.aar
```
Example:
```
VietmapAndroidAutoSDK.aar
```
- Change the version in `jitpack.yml` file as below
```yml
 - FILE="-Dfile=VietmapAndroidAutoSDK.aar" 
 ```
- Create new tag __match with the version was created__
## The tag must be compliance with below format:
```yml
    [0-9]+.[0-9]+.[0-9]
i.e:
    1.0.1
```

- Commit and push new code to created tag
- Github action will release new version to jitpack automatically

### Go to https://jitpack.io/#vietmap-company/vietmap-android-auto
and make sure the get it button of latest version is full-fill green status. If it getting white status, click it.