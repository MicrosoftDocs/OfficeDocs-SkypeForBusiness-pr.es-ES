---
title: 'Lync Server 2013: solución de problemas del complemento Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad67f17f3d12f72472ee8ddbc0e7605cf58dab52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Solución de problemas del complemento Lync VDI en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Solución de problemas con la instalación del complemento Lync VDI en un cliente ligero

Si encuentra problemas con la instalación del complemento VDI en un cliente ligero, compruebe lo siguiente:

  - Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.

  - Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación de su fabricante para obtener más instrucciones.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Resolución de problemas con el emparejamiento

Cuando el emparejamiento con el complemento VDI no funcione, el icono de emparejamiento de la parte inferior derecha mostrará una “X” de color rojo tal como se muestra:

![Icono de VDI de Lync que muestra el emparejamiento correcto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono de VDI de Lync que muestra el emparejamiento correcto")

A continuación se describen posibles razones para los errores, así como las acciones de corrección que puede llevar a cabo.

  - **El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**
    
    El usuario debe cerrar la sesión de Lync e iniciarla de nuevo con las credenciales correctas. Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.

  - **Se está ejecutando otra instancia del cliente de escritorio remoto.**
    
    Si usa conexión a escritorio remoto en Windows, los usuarios deben hacer lo siguiente:
    
    1.  Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.
    
    2.  Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.
    
    3.  Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**.
    
    4.  Inicie una nueva sesión de escritorio remoto e intente realizar la conexión de nuevo.

  - **Los archivos necesarios no se han instalado correctamente.**
    
    Una vez instalado el complemento en el equipo local, los siguientes archivos deben estar presentes en C:\\archivos\\de programa Microsoft Office\\Office15 (o la letra de unidad correspondiente):
    
      - LyncVdiPlugin. dll
    
      - UcVdi. dll
    
    Si hay problemas con el emparejamiento VDI, asegúrese de que estos archivos se encuentran en el equipo local.

  - **El cliente de Lync se está ejecutando en el equipo local.**
    
    Para usar el complemento VDI para Lync, un cliente de Lync no debe estar en ejecución en el equipo local; de lo contrario, se producirá un error de emparejamiento. Como procedimiento recomendado, el usuario no debe instalar un cliente de Lync en el equipo local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

