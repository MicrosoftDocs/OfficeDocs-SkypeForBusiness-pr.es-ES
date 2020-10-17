---
title: 'Lync Server 2013: requisitos previos del complemento Lync VDI'
description: 'Lync Server 2013: requisitos previos del complemento Lync VDI.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4389f776747426d07442e29418ab97e9609de7ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566546"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Requisitos previos del complemento Lync VDI en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-03-07_

En un entorno de infraestructura de escritorio virtual (VDI), las máquinas virtuales y el equipo local del usuario deben cumplir los requisitos descritos en esta sección.

<div>


> [!NOTE]  
> Consulte al proveedor de soluciones de virtualización para obtener más información sobre la instalación y la implementación del entorno virtualizado. Para más información sobre la implementación de un entorno virtualizado en función de los servicios de Hyper-V y de escritorio remoto, consulte los artículos siguientes en la biblioteca de TechNet de Microsoft: 
> <UL>
> <LI>
> <P>Hyper-V en <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Servicios de escritorio remoto en Windows Server &nbsp; 2008 &nbsp; R2 en <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

A continuación aparecen los requisitos para las máquinas virtuales que se ejecutan en el equipo del centro de datos:

  - Las máquinas virtuales deben configurarse con Windows 10, Windows 8,1, Windows 8, Windows 7 o Windows Server 2008 R2 con los últimos Service Packs.

A continuación se indican los requisitos para el usuario y el equipo local del usuario:

  - El usuario debe estar alojado en Lync Server 2013.

  - El equipo local debe ejecutar Windows Embedded Standard 7 con SP1, Windows 7 con SP1, Windows 8, Windows 8,1 Embedded o Windows 8,1 (no incrustado).

  - Si usa servicios de escritorio remoto, el bits de complemento de VDI de Lync (es decir, si la aplicación es de 32 bits o de 64 bits) debe coincidir con los bits del sistema operativo del equipo local. No es necesario que coincidan el valor de bits del sistema operativo del equipo local y del sistema operativo de la máquina virtual. Si usa otra plataforma u otra solución de virtualización, consulte a su proveedor de soluciones de virtualización para informarse de los requisitos del valor de bits.

  - El equipo local debe ejecutar la última versión del cliente de escritorio remoto. Instale las últimas actualizaciones de cliente de los servicios de escritorio remoto de Microsoft o el último software cliente de escritorio remoto del proveedor de soluciones de virtualización. Para obtener las actualizaciones más recientes de servicios de escritorio remoto, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .

  - En el PC local, configure el cliente de escritorio remoto para que el audio se reproduzca en el PC local y que la grabación remota esté deshabilitada. Para configurar estas opciones para conexión a escritorio remoto en Windows, consulte la sección siguiente, "para configurar las opciones de conexión a escritorio remoto".

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>Configuración de los parámetros de conexión al escritorio remoto

Para preparar la conexión a escritorio remoto en Windows para el complemento de VDI de Lync, siga estos pasos.

1.  Si el equipo local ejecuta Windows 8, omita este paso. Si el equipo local ejecuta Windows 7 con SP1, instale la versión más reciente de Windows 8 del cliente de servicios de escritorio remoto, disponible en [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .

2.  Inicie el cliente de servicios de escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a escritorio remoto**.

3.  Haga clic en **Opciones**.

4.  Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:
    
      - En **Reproducción de audio remota**, seleccione **Reproducir en este equipo**.
    
      - En **Grabación de audio remota**, seleccione **No grabar**.
    
      - Haga clic en **Aceptar**.

5.  Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.

6.  Haga clic en la pestaña **General**. En **Equipo**, escriba el nombre de la máquina virtual y haga clic en **Conectar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

