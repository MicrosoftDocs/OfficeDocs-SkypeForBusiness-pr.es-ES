---
title: Impedir nuevas conexiones a Lync Server para el mantenimiento del servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3678414e45e556eb7092b923fab4b737bfd4842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Impedir nuevas conexiones a Lync Server 2013 para el mantenimiento del servidor

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Lync Server permite desconectar un servidor (por ejemplo, para aplicar actualizaciones de software o hardware) sin que los usuarios pierdan el servicio.

Si especifica la opción para prevenir nuevas conexiones o llamadas al servidor en un grupo de servidores, dicho grupo deja de atender nuevas conexiones o llamadas en el momento en que se implementa la opción. Dichas nuevas conexiones y llamadas se redirigen a los otros servidores del grupo. Un servidor que no permite las nuevas conexiones permite que continúen las sesiones de conexiones existentes hasta su final natural. Cuando terminan todas las sesiones iniciadas, el servidor está listo para ser desconectado.

Cuando evita nuevas conexiones a un servidor front-end, algunas características y servicios de Lync Server se basan en el equilibrio de carga de DNS para asegurarse de que funcionan correctamente. Si no usa el equilibrador de carga de DNS en el grupo de servidores, puede que las conexiones a través de dichos servicios no se redirijan a otros servidores durante el período en que el servidor no admite nuevas conexiones, por lo cual es posible que cuando el servidor se desconecte se vean interrumpidas algunas sesiones y llamadas. Las características que dependen del equilibrador de carga de DNS para garantizar que esta opción funciona correctamente son las siguientes:

  - Auxiliar

  - Aplicación de anuncio de conferencia

  - Aplicación de grupo de respuesta

  - Aplicación de anuncio

  - Aplicación Estacionamiento de llamadas

Para obtener más información sobre el equilibrio de carga de DNS, vea [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación referente a la planeación.

Además de impedir nuevas conexiones para todos los servicios en un servidor que ejecuta Lync Server, también puede evitar nuevas conexiones para servicios individuales de Lync Server. Por ejemplo, este método es útil en una situación en la que se debe aplicar una actualización de Lync Server que no requiera que se cierre todo el servidor. Tenga en cuenta que cuando deje de admitir conexiones para un servicio, es necesario seleccionar un servicio según está agrupado y según se muestra en la lista de servicios de Windows. Por ejemplo, el servicio front-end de Lync Server y el agente de recopilación de datos para la supervisión son servicios independientes de Lync Server, pero en la lista de servicios de Windows se consolidan y se muestran como el servicio front-end de Lync Server. Puede evitar nuevas conexiones para el servicio front-end de Lync Server, pero no puede evitar nuevas conexiones para estos dos servicios de Lync Server subyacentes por separado.

<div>


> [!IMPORTANT]
> Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Para evitar nuevas conexiones a Lync Server:

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Abra la consola del complemento Servicios: haga clic en **Inicio**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicios**.

3.  En la lista, haga doble clic en el servicio de Windows Lync Server en el que desea impedir que se realicen nuevas conexiones.

4.  En el cuadro de diálogo Propiedades, en **Estado del servicio: Iniciado**, haga clic en **Pausar**.

5.  Como alternativa, y recomendación, junto a **Tipo de inicio**, haga clic en **Manual**.
    
    <div>
    

    > [!IMPORTANT]
    > Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.

    
    </div>

6.  Cuando haya terminado, haga clic en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

