

### rxjava 관련 셋팅

- https://github.com/ReactiveX/RxKotlin
- https://github.com/JakeWharton/RxBinding
- https://www.journaldev.com/22527/android-rxbinding // 예제 많음 기초로 좋음

```
    // rx java
    implementation("io.reactivex.rxjava2:rxkotlin:2.4.0")
    // rx binding android x
    implementation 'com.jakewharton.rxbinding3:rxbinding-core:3.0.0'
    implementation 'com.jakewharton.rxbinding3:rxbinding-appcompat:3.0.0'
    implementation 'com.jakewharton.rxbinding3:rxbinding-drawerlayout:3.0.0'
    implementation 'com.jakewharton.rxbinding3:rxbinding-leanback:3.0.0'
    implementation 'com.jakewharton.rxbinding3:rxbinding-recyclerview:3.0.0'
    implementation 'com.jakewharton.rxbinding3:rxbinding-slidingpanelayout:3.0.0'
    implementation 'com.jakewharton.rxbinding3:rxbinding-swiperefreshlayout:3.0.0'
    implementation 'com.jakewharton.rxbinding3:rxbinding-viewpager:3.0.0'
```


example 
```
       textMessage.clicks()
            .observeOn(AndroidSchedulers.mainThread())
            .subscribe {
                textMessage.setText("tttt");
            }
```

### mvvm

https://github.com/hazems/mvvm-sample-app
