# coordinates2country-android

What country is at a particular latitude/longitude? This tiny Android library (less than 100kB) tells you in 50 milliseconds, without using the Internet and without requiring any permission.

- Fast reverse geocoding
- Never needs an Internet connection

For the Java desktop/server version, see https://github.com/coordinates2country/coordinates2country.

# Use

This [sample Android app that uses the library](https://github.com/coordinates2country/sample-android) might help.

## 1) Import the library

If using Gradle:
```
implementation("io.github.coordinates2country:coordinates2country-android:1.8") { exclude group: 'com.google.android', module: 'android' }
```

For other build systems or for the JAR, search for the latest version on [Maven Central](https://search.maven.org/artifact/io.github.coordinates2country/coordinates2country/1.2/jar).

At the top of your Java file, after the package declaration, insert this line:
```
import io.github.coordinates2country.Coordinates2Country;
```

## 2) Call the library

`Coordinates2Country.country(-23.7, 39.8)` returns the String `France`.

If you prefer identifiers, `Coordinates2Country.countryQID(-23.7, 39.8)` returns `142`, the Wikidata [QID](https://www.wikidata.org/wiki/Q142) number of France.

# Build

Run `./gradlew build -x test`, or `./build.sh` if you modified anything in the `data` folder.

# Generate the gray map

- Open countries.xcf in Gimp
- Image > Duplicate
- Colors > Components > Extract component > RGB Red
- File > Export As
- Filename: data/countries-8bitgray.png
- Export > 8bpc GRAY 

When modifying the map, you can modify colors to see better, as long as you keep the RGB red component.

# Info

Source image: https://commons.wikimedia.org/wiki/File:Internationalwaters.png Kvasir Creative Commons Attribution-Share Alike 3.0 Unported, 2.5 Generic, 2.0 Generic and 1.0 Generic license.

Projection: https://en.wikipedia.org/wiki/Equirectangular_projection with phi0=0 and lambda0=0

Useful maps: https://farm8.staticflickr.com/7292/10134658063_fca4fc3da2_o.jpg https://i.imgur.com/lzm0fWN.png
