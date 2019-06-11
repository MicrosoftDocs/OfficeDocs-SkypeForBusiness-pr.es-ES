---
title: 'Lync Server 2013: Requisitos previos del componente de VDI de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae32480e5a3dbfbdfc22c4dbde59c62383c9587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Requisitos previos del componente de VDI de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-03-07_

En un entorno de infraestructura de escritorio virtual (VDI), las máquinas virtuales y el equipo local del usuario deben cumplir los requisitos descritos en esta sección.

<div>


> [!NOTE]  
> Para obtener más información sobre cómo instalar e implementar el entorno virtualizado, consulte su proveedor de soluciones de virtualización. Para obtener información sobre cómo implementar un entorno virtualizado basado en Hyper-V y servicios de escritorio remoto, consulte los artículos siguientes en la biblioteca de Microsoft TechNet: 
> <UL>
> <LI>
> <P>Hyper-V en<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Servicios de escritorio remoto en Windows&nbsp;Server&nbsp;2008 R2 en<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

A continuación se indican los requisitos para las máquinas virtuales que se ejecutan en el equipo del centro de datos:

  - Las máquinas virtuales deben configurarse con Windows 10, Windows 8,1, Windows 8, Windows 7 o Windows Server 2008 R2 con los Service Packs más recientes.

A continuación se indican los requisitos para el usuario y el equipo local del usuario:

  - El usuario debe estar alojado en Lync Server 2013.

  - El equipo local debe estar ejecutando Windows Embedded Standard 7 con SP1, Windows 7 con SP1, Windows 8, Windows 8,1 Embedded o Windows 8,1 (no incrustado).

  - Si está usando servicios de escritorio remoto, el bits del complemento VDI de Lync (es decir, si la aplicación es de 32 bits o 64 bits) debe coincidir con los bits del sistema operativo del equipo local. No es necesario que los bits del sistema operativo en el equipo local y en el sistema operativo de la máquina virtual coincidan. Si está usando otra solución de virtualización o plataforma, consulte la guía de su proveedor de soluciones de virtualización sobre los requisitos de bits.

  - El equipo local debe estar ejecutando la última versión del cliente de escritorio remoto. Instale las últimas actualizaciones del cliente de los Servicios de Escritorio remoto de Microsoft o el último software de cliente de escritorio remoto del proveedor de soluciones de virtualización. Para obtener las actualizaciones más recientes de servicios de [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)escritorio remoto, consulte.

  - En el equipo local, configure el cliente de escritorio remoto para que el audio se reproduzca en el equipo local y la grabación remota esté deshabilitada. Para configurar estas opciones de conexión a escritorio remoto en Windows, consulte la sección siguiente, "para configurar las opciones de conexión a escritorio remoto".

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>Para configurar las opciones de conexión a escritorio remoto

Para preparar conexión a escritorio remoto en Windows para el complemento VDI de Lync, siga estos pasos.

1.  Si el equipo local está ejecutando Windows 8, omita este paso. Si el equipo local ejecuta Windows 7 con SP1, instale la versión más reciente de Windows 8 del cliente de servicios de escritorio remoto, [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)disponible en.

2.  Inicie el cliente de Servicios de Escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a Escritorio remoto**.

3.  Haga clic en **Opciones**.

4.  Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:
    
      - En **Reproducción de audio remoto**, seleccione **Reproducir en este equipo**.
    
      - En **Grabación de audio remoto**, seleccione **No grabar**.
    
      - Haga clic en **Aceptar**.

5.  Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.

6.  Haga clic en la pestaña **General** . En **equipo**, escriba el nombre de la máquina virtual y, a continuación, haga clic en **conectar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

