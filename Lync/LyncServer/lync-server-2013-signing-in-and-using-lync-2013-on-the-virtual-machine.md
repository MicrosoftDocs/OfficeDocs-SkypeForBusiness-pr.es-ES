---
title: 'Lync Server 2013: Iniciar sesión y utilizar Lync 2013 en la máquina virtual'
TOCTitle: Iniciar sesión y utilizar Lync 2013 en la máquina virtual
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48275433
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Iniciar sesión y utilizar Lync 2013 en la máquina virtual

 

_**Última modificación del tema:** 2012-10-03_

Una vez habilitado el complemento de VDI, se produce el siguiente proceso cuando el usuario inicia sesión en Lync 2013.

1.  El usuario escribe sus credenciales en el cliente Lync 2013 que está en ejecución en la máquina virtual.

2.  Cuando Lync detecte la disponibilidad del complemento de VDI, Lync solicita al usuario que vuelva a escribir sus credenciales. En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para que no tener que escribir las credenciales en inicios de sesión posteriores.

3.  Lync comienza a emparejarse con el complemento de VDI. Antes de que finalice el emparejamiento, el cliente muestra dos iconos en la barra de estado de Lync. El icono que aparece en la parte inferior izquierda indica que no hay dispositivos de audio disponibles y el icono intermitente en la parte inferior derecha, que el emparejamiento de VDI está en curso, tal y como se muestra a continuación:
    
    ![Icono Lync VDI para indicar que el emparejamiento se ha completado correctamente](images/JJ204713.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono Lync VDI para indicar que el emparejamiento se ha completado correctamente")  

4.  Una vez realizado el emparejamiento de VDI, los iconos cambian para indicar el dispositivo de audio que se utilizará para las llamadas y el emparejamiento de VDI:
    
    ![Icono de emparejamiento de Lync VDI para indicar que se ha completado correctamente](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icono de emparejamiento de Lync VDI para indicar que se ha completado correctamente")  

5.  Una vez que Lync se empareja con el complemento de VDI, el usuario podrá ver su presencia en los dispositivos compatibles con Lync que estén conectados al equipo local. También podrá realizar y contestar llamadas con normalidad.

