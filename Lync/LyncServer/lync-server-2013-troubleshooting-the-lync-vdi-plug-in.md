---
title: 'Lync Server 2013: solución de problemas del complemento VDI de Lync'
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
ms.openlocfilehash: f1dfd8082ef0f0cdfc2a7931a675398507daaa51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Solución de problemas del complemento VDI de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Solución de problemas relacionados con la instalación del complemento de VDI para Lync en un cliente ligero

Si hay problemas con la instalación del complemento VDI en un cliente ligero, compruebe lo siguiente:

  - Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.

  - Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación de su fabricante para obtener más instrucciones.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Resolución de problemas con el emparejamiento

Cuando el emparejamiento de complemento de VDI falla, el icono de emparejamiento de la esquina inferior derecha se muestra como una "X" de color rojo, como se muestra a continuación:

![Icono de VDI de Lync que muestra el emparejamiento correcto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono de VDI de Lync que muestra el emparejamiento correcto")

A continuación se indican las posibles razones por las que se producen errores y las acciones correctivas que puede realizar.

  - **El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**
    
    El usuario debe cerrar la sesión de Lync y volver a iniciar sesión con las credenciales correctas. Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.

  - **Se está ejecutando otra instancia del cliente de escritorio remoto.**
    
    Si usan conexión a escritorio remoto en Windows, los usuarios deben hacer lo siguiente:
    
    1.  Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.
    
    2.  Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.
    
    3.  Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**. 
    
    4.  Inicie una nueva sesión de escritorio remoto e intente establecer la conexión de nuevo. 

  - **Los archivos necesarios no se han instalado correctamente.**
    
    Después de instalar el complemento en el equipo local, los siguientes archivos deberían estar presentes en C:\\archivos\\de programa Microsoft Office\\Office15 (o la letra de unidad correspondiente):
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    Si hay algún problema con el emparejamiento de VDI, asegúrese de que estos archivos están presentes en el equipo local.

  - **El cliente de Lync se está ejecutando en el equipo local.**
    
    Para usar el complemento de VDI para Lync, un cliente de Lync no debe estar ejecutándose en el equipo local; de lo contrario, se producirá un error de emparejamiento. Como práctica recomendada, el usuario no debe instalar un cliente de Lync en el equipo local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

