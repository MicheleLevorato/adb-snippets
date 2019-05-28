# Operazione preliminare: abilitare il debug mode
*Impostazioni* > *Informazioni sul telefono* > 7 volte tap su *Numero Build*
*Opzioni sviluppatore* > *Debug USB*

## Debug con Android Debug Bridge

### Elenca i devices connessi
```
adb devices -l
```

### Elenca le app e le filtra per stringa
```
adb shell pm list packages -f |find "stringa"
adb shell pm list packages -f |findstr stringa
```
### Info sulla app
```
adb shell dumpsys package com.company.appname
```

### Logcat: Svuota il buffer
```
adb logcat -c
```
### Importare in locale
```
adb pull "/data/app/com.yyy.xxx-ab123cd456DEFG-ab123cd==/base.apk"
```
### Logcat: pulizia schermo
```
Cls
```
## Tool di terze parti
### Localytics: stack filtrato
```
adb logcat Localytics:V *:S | find "upload_format=2"
```
 
### Firebase: forzare modalità debug
```
adb shell setprop debug.firebase.analytics.app com.company.appname
```
