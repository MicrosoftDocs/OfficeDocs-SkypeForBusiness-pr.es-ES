---
title: 'Lync Server 2013: Configuración de rutas de voz para llamadas salientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Configuración de rutas de voz para llamadas salientes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Una ruta de voz de Lync Server 2013 asocia los números de teléfono de destino con una o más puertas de enlace de red telefónica conmutada (RTC) o troncos SIP y uno o más registros de uso de RTC.

**Para ver las rutas de voz con el panel de control de Lync Server**

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Haga clic en **enrutamiento de voz**.

3.  Haga clic en **Ruta**.

4.  Haga doble clic en una ruta de voz para ver propiedades adicionales de la lista de rutas de voz, o bien seleccione la ruta y haga clic en **Editar**. A continuación, haga clic en **Mostrar detalles**.
    
    <div>
    

    > [!NOTE]  
    > Solo puede ver información detallada para una única ruta a la vez.

    
    </div>

**Para ver las rutas de voz mediante Windows PowerShell**

  - Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**. Las rutas de voz se pueden ver con Windows PowerShell y el cmdlet **Get-CsVoiceRoute** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.
    
    Para ver información sobre todas las rutas de voz, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsVoiceRoute
    
    Devolverá información similar a la siguiente:
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> Para obtener más información, vea <A href="lync-server-2013-voice-routes.md">rutas de voz en Lync Server 2013</A> en la documentación de planeación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Administrar el enrutamiento de voz en Lync Server 2013](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

