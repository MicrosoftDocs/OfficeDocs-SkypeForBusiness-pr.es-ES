---
title: 'Lync Server 2013: iniciar sesión y usar Lync 2013 en la máquina virtual'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710119091a5ed6254f18f7b40a4549ab9d09c776
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533987"
---
# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Inicio de sesión y uso de Lync 2013 en la máquina virtual

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Una vez habilitado el complemento VDI, se producen los siguientes pasos cuando el usuario inicia sesión en Lync 2013.

1.  El usuario escribe sus credenciales en el cliente de Lync 2013 que se ejecuta en la máquina virtual.

2.  Una vez que Lync detecta la disponibilidad del complemento VDI, Lync solicita al usuario que vuelva a escribir sus credenciales. En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para que no tener que escribir las credenciales en inicios de sesión posteriores.

3.  Lync empieza a emparejarse con el complemento VDI. Antes de completar el emparejamiento, el cliente muestra dos iconos en la barra de estado de Lync. El icono que aparece en la parte inferior izquierda indica que no hay dispositivos de audio disponibles y el icono intermitente en la parte inferior derecha, que el emparejamiento de VDI está en curso, tal y como se muestra a continuación:
    
    ![Icono de VDI de Lync que muestra el emparejamiento correcto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono de VDI de Lync que muestra el emparejamiento correcto")  

4.  Una vez realizado el emparejamiento de VDI, los iconos cambian para indicar el dispositivo de audio que se utilizará para las llamadas y el emparejamiento de VDI:
    
    ![Icono de emparejamiento de VDI de Lync que muestra correcto](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icono de emparejamiento de VDI de Lync que muestra correcto")  

5.  Después de que los pares de Lync con el complemento VDI, el usuario pueda ver su presencia en dispositivos compatibles con Lync conectados al equipo local. También podrá realizar y contestar llamadas con normalidad.

</div>

<span> </span>

</div>

</div>

</div>

