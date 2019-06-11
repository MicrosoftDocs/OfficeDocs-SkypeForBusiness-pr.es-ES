---
title: Impedir nuevas conexiones a Lync Server para el mantenimiento del servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3838af59a6a91699fa6d38b8aa2912e2b30012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Impedir nuevas conexiones a Lync Server 2013 para el mantenimiento del servidor

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Lync Server le permite poner fuera de conexión un servidor (por ejemplo, para aplicar actualizaciones de software o hardware) sin ninguna pérdida de servicio para los usuarios.

Cuando especifica la opción de evitar nuevas conexiones o llamadas a un servidor de un grupo, deja de tomarse cualquier conexión y llamada nuevas tan pronto como implemente esta opción. Estas nuevas conexiones y llamadas se enrutan a través de otros servidores del grupo. Un servidor que impide nuevas conexiones permite que las sesiones de las conexiones existentes continúen hasta que se desordenan de forma natural. Cuando haya finalizado todas las sesiones existentes, el servidor estará listo para desconectarse.

Cuando impide nuevas conexiones a un servidor front-end, algunas características y servicios de Lync Server dependen del equilibrio de carga de DNS para asegurarse de que funciona correctamente. Si no usa el equilibrio de carga de DNS en el grupo, es posible que las conexiones a través de estos servicios no se redirijan a otros servidores durante el período en el que el servidor está impidiendo las conexiones nuevas y, por lo tanto, cuando el servidor se desconecta, algunas sesiones y llamadas pueden ser interrupción. Las características que dependen del equilibrio de carga de DNS para asegurarse de que esta opción funciona correctamente son las siguientes:

  - Operador

  - Aplicación de anuncio de conferencia

  - Aplicación de grupo de respuesta

  - Aplicación de anuncio

  - Aplicación de estacionamiento de llamadas

Para obtener más información sobre el equilibrio de carga de DNS, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación de planeación.

Además de impedir nuevas conexiones para todos los servicios en un servidor que ejecuta Lync Server, también puede impedir nuevas conexiones para servicios individuales de Lync Server. Por ejemplo, este método es útil en una situación en la que necesita aplicar una actualización de Lync Server que no requiera que se cierre todo el servidor. Tenga en cuenta que cuando impide las conexiones para un servicio, debe seleccionar un servicio tal como está agrupado y se muestra en la lista de servicios de Windows. Por ejemplo, el servicio front-end de Lync Server y el agente de recopilación de datos para la supervisión son servicios independientes de Lync Server, pero en la lista de servicios de Windows se consolidan y se muestran como el servicio front-end de Lync Server. Puede evitar nuevas conexiones para el servicio front-end de Lync Server, pero no puede evitar nuevas conexiones por separado en estos dos servicios de Lync Server subyacentes.

<div>


> [!IMPORTANT]
> Al configurar un servidor para evitar nuevas conexiones y reiniciar el servidor, de forma predeterminada, el servidor comenzará a aceptar inmediatamente nuevas conexiones después de que se inicie. Para evitar esto, configure el servidor para que solo PAUSE y reanude de forma manual, antes de reiniciar el servidor.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Para evitar nuevas conexiones a Lync Server:

1.  Inicie sesión en el equipo local como miembro del grupo Administradores.

2.  Abra la consola del complemento Servicios: haga clic en **Inicio**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicios**.

3.  En la lista, haga doble clic en el servicio de Windows de Lync Server en el que desea evitar nuevas conexiones.

4.  En el cuadro de diálogo Propiedades, en **Estado del servicio: iniciado**, haga clic en pausar. ****

5.  De forma opcional, pero recomendado, junto a **tipo de inicio**, haga clic en **manual**.
    
    <div>
    

    > [!IMPORTANT]
    > Al configurar un servidor para evitar nuevas conexiones y reiniciar el servidor, de forma predeterminada, el servidor comenzará a aceptar inmediatamente nuevas conexiones después de que se inicie. Para evitar esto, configure el servidor para que solo PAUSE y reanude de forma manual, antes de reiniciar el servidor.

    
    </div>

6.  Cuando haya terminado, haga clic en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

