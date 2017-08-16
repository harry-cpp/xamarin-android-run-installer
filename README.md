# Xamarin Androind installer for Linux
A simple .run Linux installer for Xamarin.Android

This only installas Xamarin.Android binary to your system, this does not include the Xamarin.Android addon for MonoDevelop or anything similar to that. To install it simply run:
```sh
git clone https://github.com/cra0zy/xamarin-android-run-installer.git
./generate.sh
sudo ./bin/xamarin-android.run
```

-------

## Tips

### Skip specifying location on build

If you want to skip having to specify Android SDK/NDK each time you compile simply create a file "~/.config/xbuild/monodroid-config.xml" that looks like so:
```xml
<?xml version="1.0" encoding="utf-8"?>
<monodroid>
	<android-sdk path="/path/to/your/Android/Sdk" />
  
	<!-- Only needs specifying in case one of them is not found in default location -->
	<!-- android-ndk path="" -->
	<!-- java-sdk path="" -->
</monodroid>
```

### Get visual studio code to autocomplete

Visual studio code comes with it's own msbuild, so we need to add a symlink to it's msbuild dir. Simply do:
```sh
ln -s "/usr/lib/mono/xbuild/Xamarin" "$PathToYourOmnisharpExtension/bin/omnisharp/msbuild/Xamarin"
ln -s "/usr/lib/mono/xbuild/Novell" "$PathToYourOmnisharpExtension/bin/omnisharp/msbuild/Xamarin"
```