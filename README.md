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

###### Al realizar este paso, tener en cuenta tener actualizados el paquete de Google Play Services y el de Google Repository, se pueden actualizar desde el SDK Manager, en el paquete de Extras (Para asegurarse de que esten bien actualizados, se pueden desistalar y luego volver a instalar dichos paquetes):

![Alt text](https://github.com/orejuelajd/HelloWorld_CastVideo_GoogleCast/blob/master/imagesreadme/cast_005.JPG "Optional Text")

## Ajustar target y sdk mínimo

Clic derecho a la carpeta del proyecto "app", clic en "open module settings" y cambiar la configuración de la siguiente manera:

* En la pestaña <b>properties</b>:
  - Compile SDK version: API 21: Android 5.0 (Lollipop)
  - Build Tools Version: 21.1.2
  
  ![Alt text](https://github.com/orejuelajd/HelloWorld_CastVideo_GoogleCast/blob/master/imagesreadme/cast_001.JPG "Optional Text")
  
* En la pestaña <b>Flavors</b>:
  - Min Sdk Version: API 21: Android 5.0 (Lollipop)
  - Target Sdk version: API 21: Android 5.0 (Lollipop) 
  
  ![Alt text](https://github.com/orejuelajd/HelloWorld_CastVideo_GoogleCast/blob/master/imagesreadme/cast_002.JPG "Optional Text")

## Agregar valores en strings.xml
    
```
  </resources>
    ...
    <string name="action_settings">Settings</string>
    <string name="video_url"></string>
    <string name="play_video"> Video</string>
    <string name="pause_video">Pause Video</string>
    <string name="resume_video">Resume Video</string>
    <string name="video_title">VIDEO STREAM OF MP4 FILES IN CHROMECAST</string>
    <string name="content_type_mp4">videos/mp4</string>
    ...
  </resources>
```
    
## Agregar item en el menú de la main activity (menu_main.xml)

```
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    tools:context=".MainActivity">
    <item android:id="@+id/action_settings" android:title="@string/action_settings"
        android:orderInCategory="100" android:showAsAction="never" />

    <item
        android:id="@+id/media_route_menu_item"
        android:title="Chromecast"
        app:actionProviderClass="android.support.v7.app.MediaRouteActionProvider"
        app:showAsAction="always"/> 
</menu>
```

Con esto, se podrá visualizar el botón que brinda la opción de hacer cast cuando hay un 
y que aparece cuando se detecta un dispositivo Chromecast en la red.

![Alt text](https://github.com/orejuelajd/HelloWorld_CastVideo_GoogleCast/blob/master/imagesreadme/cast_004.JPG "Optional Text")

## Agregar el botón de reproducir y pausar

En el layout de la activity principal (activity_main.xml), añade el botón.

```
<RelativeLayout ...>
    ...
    <Button
        android:id="@+id/button"
        android:text="Play Video"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>
    ...
</RelativeLayout>
```

Esto nos dará como resultado lo siguiente:

![Alt text](https://github.com/orejuelajd/HelloWorld_CastVideo_GoogleCast/blob/master/imagesreadme/cast_003.JPG "Optional Text")
