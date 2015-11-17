# HelloWorld_CastVideo_GoogleCast
Proyecto en Android Studio para realizar un Cast, reproduciendo un vídeo en el televisor que tiene conectado el Chromecast. 
En la interfaz para el smartphone se despliega un solo botón que sirve para reproducir o pausar el vídeo.

## build.gradle(Module:app)

Agregar las siguientes dependencias en el archivo build.gradle de la app.

```
  dependencies {	
    ...	
    compile 'com.android.support:appcompat-v7:21.0.0'	
    compile 'com.android.support:mediarouter-v7:19.0.+' 
    compile 'com.google.android.gms:play-services:6.1.11'
    ...
  }
  
```

## Ajustar target y sdk mínimo

Clic derecho a la carpeta del proyecto "app", clic en "open module settings" y cambiar la configuración de la siguiente manera:

* En la pestaña <b>properties</b>:
  - Compile SDK version: API 21: Android 5.0 (Lollipop)
  - Build Tools Version: 21.1.2
  
  ![Alt text](https://github.com/orejuelajd/HelloWorld_CastVideo_GoogleCast/blob/master/imagesreadme/cast_001.JPG "Figura 01")
  
* En la pestaña <b>Flavors</b>:
  - Min Sdk Version: API 21: Android 5.0 (Lollipop)
  - Target Sdk version: API 21: Android 5.0 (Lollipop) 
  
