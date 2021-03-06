# geohash-poly

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.xlvecle/geohash-poly/badge.svg?style=plastic)](https://maven-badges.herokuapp.com/maven-central/com.xlvecle/geohash-poly)
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)


A tool written by kotlin for users who want to transform a GeoPolygon to a list of geohashes that cover it.
You can use it in kotlin/java/scala or any other jvm languages. 

帮助你获取地理多边形内所包含的geohash块，支持JVM系语言，kotlin/java/scala。

## Maven
```xml
<dependency>
  <groupId>com.xlvecle</groupId>
  <artifactId>geohash-poly</artifactId>
  <version>1.0.4</version>
</dependency>
```

## SBT
```
libraryDependencies += "com.xlvecle" % "geohash-poly" % "1.0.4"
```

## Gradle via JCenter
```
compile 'com.xlvecle:geohash-poly:1.0.4'
```

## Example
java
```java
List<String> result = GeohashPolyKt.geohashPoly(yourPoly, 7,"center",null);
```

kotlin
```kotlin
val result = geohashPoly(polygon = yourPoly)
```

polygon
```
[[43.82682, 87.561062], [43.82603, 87.56118], [43.825584, 87.561228], [43.824812, 87.559267], [43.823374, 87.559966], [43.822403, 87.55697], [43.822063, 87.557242], [43.82196, 87.557343], [43.821884, 87.557411], [43.821541, 87.557739], [43.821297, 87.557968], [43.821026, 87.558212], [43.821026, 87.55822], [43.82095, 87.558289], [43.820648, 87.55854], [43.820457, 87.558701], [43.820316, 87.558784], [43.819336, 87.55941], [43.818413, 87.559868], [43.818369, 87.559888], [43.818079, 87.560069], [43.816741, 87.560534], [43.816735, 87.560536], [43.816155, 87.560759], [43.816258, 87.561499], [43.816504, 87.562881], [43.817145, 87.562698], [43.818107, 87.567492], [43.818326, 87.569616], [43.813458, 87.571201], [43.813561, 87.571781], [43.813934, 87.573748], [43.813909, 87.573757], [43.814606, 87.577705], [43.819122, 87.575989], [43.819328, 87.576653], [43.819881, 87.576721], [43.820751, 87.576462], [43.821248, 87.577614], [43.821629, 87.577293], [43.821831, 87.577744], [43.823769, 87.577217], [43.82365, 87.575882], [43.825039, 87.5755], [43.824669, 87.574402], [43.82653, 87.573799], [43.825508, 87.572128], [43.826324, 87.568733], [43.828007, 87.569618], [43.828228, 87.568977], [43.828635, 87.569151], [43.828725, 87.569072], [43.828926, 87.568604], [43.828968, 87.568535], [43.829071, 87.568367], [43.829262, 87.567757], [43.829269, 87.567688], [43.829258, 87.567665], [43.829113, 87.567551], [43.829102, 87.567505], [43.829109, 87.567429], [43.829342, 87.56665], [43.829315, 87.566544], [43.829277, 87.56649], [43.828979, 87.566254], [43.828751, 87.566055], [43.828674, 87.56601], [43.82798, 87.565628], [43.827759, 87.565498], [43.827629, 87.565453], [43.827522, 87.565437], [43.827412, 87.565437], [43.827347, 87.565453], [43.827248, 87.565483], [43.82753, 87.564476], [43.827785, 87.56356], [43.827789, 87.563316], [43.827779, 87.563052]]
``` 
inner geohashes
```
["tzy328p","tzy32b0","tzy32b1","tzy328r","tzy32b2","tzy32b3","tzy32b6","tzy32b7","tzy3288","tzy328x","tzy32b8","tzy32b9","tzy32bd","tzy32be","tzy322z","tzy328b","tzy328c","tzy328f","tzy328g","tzy328u","tzy328v","tzy328y","tzy328z","tzy32bb","tzy32bc","tzy32bf","tzy323p","tzy3290","tzy3291","tzy3294","tzy3295","tzy329h","tzy329j","tzy329n","tzy329p","tzy32c0","tzy32c1","tzy32c4","tzy323q","tzy323r","tzy3292","tzy3293","tzy3296","tzy3297","tzy329k","tzy329m","tzy329q","tzy329r","tzy32c2","tzy32c3","tzy32c6","tzy32c7","tzy323t","tzy323w","tzy323x","tzy3298","tzy3299","tzy329d","tzy329e","tzy329s","tzy329t","tzy329w","tzy329x","tzy32c8","tzy32c9","tzy32cd","tzy32ce","tzy323z","tzy329b","tzy329c","tzy329f","tzy329g","tzy329u","tzy329v","tzy329y","tzy329z","tzy32cb","tzy32cc","tzy32cf","tzy326p","tzy32d0","tzy32d1","tzy32d4","tzy32d5","tzy32dh","tzy32dj","tzy32dn","tzy32dp","tzy32f0","tzy32f1","tzy32d2","tzy32d3","tzy32d6","tzy32d7","tzy32dk","tzy32dm","tzy32de","tzy32ds","tzy32dt"]
```

## Options

+ precision: precision of geohash, default is 7 
+ mode: ```{"center", "inside", "intersect"}``` mode of calculation, default is "center", it means the center of geohash within polygon   
+ threshold: if you choose "intersect" mode, you can set threshold to control the degree of intersection
  
## 选项

+ precision: `geohash精度，base32位数`
+ mode: `计算包含geohash块的模式，默认是center，计算规则为geohash块中心点在多边形内`
+ threshold: `如果你选择了'intersect'模式，那么可以提供一个阈值来用来控制geohash和多边形相交的程度`
