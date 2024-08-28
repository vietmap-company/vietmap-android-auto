This SDK only work with Vietmap Android Map SDK v3.1.0 and above. 
Please make sure you have already integrated Vietmap Android Map SDK before using this SDK.
```gradle
dependencies {
    implementation 'com.github.vietmap-company:vietmap-android-auto:1.4.0'
    implementation 'com.github.vietmap-company:maps-sdk-android:3.1.0'
}
```
Please follow the Android Auto implementation guide [here](https://developer.android.com/codelabs/car-app-library-fundamentals#0)

This SDK will return the map as a surface view, you can add it to your Android Auto layout as a surface view.


## Usage guide
- Create a new instance of the VietMapAndroidAutoSurface
```kotlin
    val mNavigationCarSurface = VietMapAndroidAutoSurface(carContext, lifecycle)
```

- Init the VietMapAndroidAutoSurface with the style
```kotlin
    mNavigationCarSurface.init(
        Style.Builder()
            .fromUri("https://maps.vietmap.vn/api/maps/light/styles.json?apikey=YOUR_API_KEY_HERE")
    )
```
- Add onMapReady callback (if needed)
```kotlin
    mNavigationCarSurface.init(
        Style.Builder()
            .fromUri("https://maps.vietmap.vn/api/maps/light/styles.json?apikey=YOUR_API_KEY_HERE"),
        OnMapReadyCallback {
            vietMapGL = it
        }
    )
```
- Add onStyleLoaded callback (if needed)
```kotlin
    mNavigationCarSurface.init(
        Style.Builder()
            .fromUri("https://maps.vietmap.vn/api/maps/light/styles.json?apikey=YOUR_API_KEY_HERE"),
        OnStyleLoaded{
            style = it
        },
        OnMapReadyCallback {
            vietMapGL = it
        },
    )
```
- Add surface lifecycle callback (if needed)
```kotlin
    private val mSurfaceCallback: SurfaceCallback = object : SurfaceCallback {
        override fun onSurfaceAvailable(container: SurfaceContainer) {
            super.onSurfaceAvailable(container)
        }
        override fun onClick(x: Float, y: Float) {
            super.onClick(x, y)
        }

        override fun onFling(velocityX: Float, velocityY: Float) {
            super.onFling(velocityX, velocityY)
        }

        override fun onScroll(distanceX: Float, distanceY: Float) {
            super.onScroll(distanceX, distanceY)
        }

        override fun onScale(focusX: Float, focusY: Float, scaleFactor: Float) {
            super.onScale(focusX, focusY, scaleFactor)
        }
    }

    mNavigationCarSurface.addOnSurfaceCallbackListener(mSurfaceCallback)
```
