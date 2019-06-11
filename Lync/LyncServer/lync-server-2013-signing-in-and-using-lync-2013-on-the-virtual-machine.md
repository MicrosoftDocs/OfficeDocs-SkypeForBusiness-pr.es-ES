---
title: 'Lync Server 2013: Iniciar sesión y utilizar Lync 2013 en la máquina virtual'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3b890f008b30ecf008bd2e6f03803fbfe6c1674
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Iniciar sesión y utilizar Lync 2013 en la máquina virtual

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Después de habilitar el complemento VDI, se realizan los pasos siguientes cuando el usuario inicia sesión en Lync 2013.

1.  El usuario escribe sus credenciales en el cliente de Lync 2013 que se ejecuta en la máquina virtual.

2.  Una vez que Lync detecta la disponibilidad del complemento VDI, Lync le pide al usuario que vuelva a escribir sus credenciales. En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para no tener que escribir las credenciales en inicios de sesión posteriores.

3.  Lync comienza a emparejarse con el complemento VDI. Antes de completar el emparejamiento, el cliente muestra dos iconos en la barra de estado de Lync. El icono de la esquina inferior izquierda indica que no hay dispositivos de audio disponibles, y el icono parpadeante en la esquina inferior derecha indica que el emparejamiento de VDI está en curso, tal y como se muestra:
    
    ![Icono de VDI de Lync que muestra el emparejamiento correcto] (images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono de VDI de Lync que muestra el emparejamiento correcto")  

4.  Una vez realizado el emparejamiento de VDI, los iconos cambian para indicar el dispositivo de audio que se utilizará para las llamadas y el emparejamiento de VDI:
    
    ![Icono de emparejamiento de VDI de Lync que muestra el éxito] (images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icono de emparejamiento de VDI de Lync que muestra el éxito")  

5.  Después de que Lync emparejado con el complemento VDI, el usuario puede ver su presencia en dispositivos compatibles con Lync que están conectados al equipo local. Ahora, el usuario puede colocar y contestar llamadas como de costumbre.

</div>

<span> </span>

</div>

</div>

</div>

