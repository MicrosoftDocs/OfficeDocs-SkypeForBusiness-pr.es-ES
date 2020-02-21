---
title: Conmutación por recuperación del grupo de servidores perimetrales usado para la Federación de Lync Server o la Federación XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3531e50efec5d981249e892c692a20095bef9eff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Conmutación por recuperación del grupo de servidores perimetrales usado para la Federación de Lync Server o la Federación XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Después de volver a poner en línea un grupo de servidores perimetrales erróneo que hospedaba la federación, siga este procedimiento para conmutar por recuperación la ruta de la federación de Lync Server y/o la ruta de la federación XMPP para volver a usar este grupo de servidores perimetrales.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Conmutar por recuperación una federación en un grupo de servidores perimetrales restaurado

1.  En el grupo de servidores perimetrales que vuelve a estar disponible, inicie los servicios perimetrales.

2.  Si quiere conmutar por recuperación la ruta de la federación de Lync Server para usar el servidor perimetral restaurado, haga lo siguiente:
    
      - En un servidor front-end, abra el Generador de topologías. Expanda **Grupos de servidores perimetrales** y después haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales que está configurado actualmente para la federación. Seleccione **Editar propiedades**.
    
      - En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.
    
      - Expanda **Grupos de servidores perimetrales**, después haga clic con el botón secundario en el servidor perimetral original o en el grupo de servidores perimetrales que quiere volver a usar para la federación. Seleccione **Editar propiedades**.
    
      - En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.
    
      - Haga clic en **Acción**, y seleccione sucesivamente **Topología** y **Publicar**. Cuando el sistema se lo solicite, en **Publicar la topología**, haga clic en **Siguiente**. Cuando haya acabado la publicación, haga clic en **Finalizar**.
    
      - En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en **Instalar o actualizar el sistema Lync Server** y después haga clic en **Instalar o eliminar componentes de Lync Server**. Haga clic en **Ejecutar de nuevo**.
    
      - En Instalar componentes de Lync Server, haga clic en **Siguiente**. En la pantalla de resumen aparecerán las acciones tal como se ejecutan. Cuando haya acabado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.

3.  Si quiere conmutar por recuperación la ruta de la federación XMPP para usar el servidor perimetral restaurado, haga lo siguiente:
    
      - Ejecute el cmdlet siguiente para volver a apuntar la ruta de la federación XMPP al grupo de servidores perimetrales que ahora hospedarán la federación XMPP (en este ejemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        En este ejemplo, Site1 es el sitio que contiene el grupo de servidores perimetrales que ahora contendrá la ruta de la federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral de ese grupo de servidores.
    
      - Si todavía no tiene un registro DNS SRV para la federación XMPP que se resuelva en el grupo de servidores perimetrales que ahora hospedará la federación XMPP, agréguelo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - En el servidor DNS externo, cambie el registro DNS A para la federación XMPP para que apunte a EdgeServer2.contoso.com.
    
      - Compruebe que el grupo de servidores perimetrales que ahora hospedará la federación XMPP tiene el puerto 5269 abierto externamente.

4.  Si los grupos de servidores front-end siguieron ejecutándose en el sitio que contiene el grupo de servidores perimetrales que tuvo el error y que se ha restaurado, actualice el servicio de conferencia web y el servicio de conferencia A/V en estos grupos de servidores front-end para que vuelvan a usar los grupos de servidores perimetrales en su sitio local. Para obtener más información, consulte [cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Si el grupo de servidores front-end del mismo sitio que el grupo de servidores perimetrales también tuvo errores, ahora puede usar Invoke–CsPoolFailback para conmutar por recuperación el grupo de servidores front-end.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

