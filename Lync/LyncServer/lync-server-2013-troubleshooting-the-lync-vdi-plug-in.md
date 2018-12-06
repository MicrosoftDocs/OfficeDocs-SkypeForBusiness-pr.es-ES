---
title: "Résol. des pb du plug-in Lync VDI (Virtual Desktop Infrastructure) ds LS 2013"
TOCTitle: "Résol. des pb du plug-in Lync VDI (Virtual Desktop Infrastructure) ds LS 2013"
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48274560
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Solución de problemas del complemento Lync VDI

 

_**Última modificación del tema:** 2012-10-10_

## Resolución de problemas con la instalación del complemento VDI de Lync en un cliente ligero.

Si encuentra problemas con la instalación del complemento VDI en un cliente ligero, compruebe lo siguiente:

  - Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.

  - Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación de su fabricante para obtener más instrucciones.

## Resolución de problemas con el emparejamiento

Cuando el emparejamiento con el complemento VDI no funcione, el icono de emparejamiento de la parte inferior derecha mostrará una “X” de color rojo tal como se muestra:

![Icono Lync VDI para indicar que el emparejamiento se ha completado correctamente](images/JJ204713.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono Lync VDI para indicar que el emparejamiento se ha completado correctamente")

A continuación se describen posibles razones para los errores, así como las acciones de corrección que puede llevar a cabo.

  - **El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**
    
    El usuario debe cerrar la sesión de Lync e iniciar sesión de nuevo con las credenciales correctas. Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.

  - **Se está ejecutando otra instancia del cliente de escritorio remoto.**
    
    En caso de que los usuarios estén usando la Conexión a Escritorio Remoto en Windows, deberán llevar a cabo lo siguiente:
    
    1.  Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.
    
    2.  Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.
    
    3.  Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**.
    
    4.  Inicie una nueva sesión de escritorio remoto e intente realizar la conexión de nuevo.

  - **Los archivos necesarios no se han instalado correctamente.**
    
    Una vez instalado el complemento en el equipo local, deberán estar presentes los siguientes archivos en el directorio C:\\Archivos de programa\\Microsoft Office\\Office15 (la letra dependerá de la unidad):
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    Si hay problemas con el emparejamiento VDI, asegúrese de que estos archivos se encuentran en el equipo local.

  - **El cliente de Lync se está ejecutando en el equipo local.**
    
    Para usar el complemento VDI de Lync, el cliente de Lync no puede estar ejecutándose en el equipo local, ya que, de lo contrario, el emparejamiento no se llevará a cabo correctamente. Por lo tanto, se recomienda que el usuario no instale ningún cliente de Lync en el equipo local.

