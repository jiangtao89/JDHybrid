# XWebView - Android

## 依赖

Gradle

项目 `build.gradle`

```groovy
	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```

模块 `build.gradle`

```groovy
	implementation 'com.github.JDHybrid.JDHybridTmp:XWebView:1.0.0'
```

## 使用

### WebView

使用 `XWebView` 作为您的Web View。

> ```kotlin
> import com.jd.hybrid.XWebView
> 
> ...
> 
> val webView = XWebView(context)
> 
> ...
> ```

## 能力

### JDBridge

已集成 [JDBridge](../JDBridge/README.md)

### 生命周期事件

`XWebView` 的生命周期变化时会发射以下JS事件：

- onStart -> event: ContainerShow

- onResume -> event: ContainerActive

- onPause -> event: ContainerInactive

- onStop -> event: ContainerHide

### 以下方法会在主线程执行

`XWebView`的以下方法将会自动切换到主线程执行，您无需手动切换：

- addJavascriptInterface
- evaluateJavascript
- loadUrl
- reload
- stopLoading
- goBack
- goForward
- goBackOrForward