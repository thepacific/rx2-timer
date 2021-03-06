![](https://github.com/thepacific/timer/blob/master/previews/preview01.png)

This is a simple rxjava2/rxjava3/kotlin-flow timer. I copy this class into all the little apps I make. I'm tired of doing it. Now it's a library

[![Download](https://img.shields.io/maven-central/v/com.github.thepacific/rx2-timer.svg)](https://search.maven.org/artifact/com.github.thepacific/rx2-timer)

Usage
-----

```java
timer = Rx2Timer.builder()
                .initialDelay(0) //default is 0
                .period(1) //default is 1
                .take(30) //default is 60
                .unit(TimeUnit.SECONDS) // default is TimeUnit.SECONDS
                .onEmit(count -> {
                    if (count < 10) {
                        binding.text.setText("0" + count + " s");
                    } else {
                        binding.text.setText(count + " s");
                    }
                })
                .onError(e -> binding.text.setText(R.string.count))
                .onComplete(() -> binding.text.setText(R.string.count))
                .build();

timer.start();
timer.stop();
timer.restart();
timer.pause();
timer.resume();
                
```

Gradle
--------

```groovy
// rxjava2
implementation 'com.github.thepacific:rx2-timer:1.0.0'
// rxjava3
implementation 'com.github.thepacific:rx3-timer:1.0.0'
```

License
-------

[The MIT License ](https://opensource.org/licenses/MIT)

