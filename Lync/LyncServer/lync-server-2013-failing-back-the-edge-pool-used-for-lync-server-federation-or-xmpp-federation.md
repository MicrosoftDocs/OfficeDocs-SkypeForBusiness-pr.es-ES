---
title: Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Después de que se haya vuelto a conectar un grupo perimetral que usó para hospedar la Federación, use este procedimiento para recuperar la ruta de Federación de Lync Server y/o la ruta de Federación XMPP para usar de nuevo este grupo de bordes restaurado.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Conmutación por error de la Federación a un grupo perimetral restaurado

1.  En el grupo Edge que ya está disponible de nuevo, inicie los servicios de Edge.

2.  Si desea recuperar la conmutación por error de la ruta de Federación de Lync Server para usar el servidor perimetral restaurado, haga lo siguiente:
    
      - En un servidor front-end, abra Topology Builder. Expanda **agrupaciones perimetrales**y haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales actualmente configurados para la Federación. Seleccione **Editar propiedades**.
    
      - En **Editar propiedades** , en **General**, desactive **Habilitar Federación para este grupo perimetral (puerto 5061)**. Haga clic en **Aceptar**.
    
      - Expanda **agrupaciones perimetrales**y, a continuación, haga clic con el botón secundario en el servidor perimetral original o en el grupo de servidores perimetrales que desea usar de nuevo para la Federación. Seleccione **Editar propiedades**.
    
      - En **propiedades de edición** , en **General**, seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)**. Haga clic en **Aceptar**.
    
      - Haga clic en **acción**, seleccione **topología**, seleccione **publicar**. Cuando se le solicite al **publicar la topología**, haga clic en **siguiente**. Una vez finalizada la publicación, haga clic en **Finalizar**.
    
      - En el servidor perimetral, abra el Asistente para la implementación de Lync Server. Haga clic en **instalar o actualizar el sistema Lync Server**y, a continuación, haga clic en **configurar o quitar los componentes de Lync Server**. **Vuelva a**hacer clic en ejecutar.
    
      - En instalación de los componentes de Lync Server, haga clic en **siguiente**. La pantalla resumen mostrará las acciones a medida que se ejecutan. Una vez que haya finalizado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.

3.  Si desea recuperar la conmutación por recuperación de la ruta de Federación de XMPP para usar el servidor perimetral restaurado, haga lo siguiente:
    
      - Ejecute el siguiente cmdlet para redirigir la ruta de Federación de XMPP al conjunto de servidores perimetrales que ahora hospedan la Federación XMPP (en este ejemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        En este ejemplo, Sitio1 es el sitio que contiene el grupo Edge que ahora hospedará la ruta de Federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral en ese grupo.
    
      - Si todavía no tiene un registro SRV de DNS para la Federación de XMPP, que se resuelve en el grupo Edge que ahora hospedará la Federación XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - En el servidor DNS externo, cambie el registro A de DNS para la Federación XMPP para que apunte a EdgeServer2.contoso.com.
    
      - Verifique que el grupo de servidores perimetrales que ahora hospeda la Federación XMPP tenga el puerto 5269 abierto externamente.

4.  Si las agrupaciones front-end permanecieron ejecutándose en el sitio que contiene el grupo perimetral que falló y se han restaurado, debe actualizar el servicio de conferencias web y el servicio de conferencia A/V en estos grupos de aplicaciones para el usuario de nuevo para usar los grupos perimetrales en su sitio local. Para obtener más información, vea [cambiar el grupo perimetral asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Si el grupo de servidores front-end en el mismo sitio que el grupo perimetral con errores también ha fallado, ahora puede usar Invoke-CsPoolFailback para recuperar el repositorio front-end.

</div>

<div>

## <a name="see-also"></a>Vea también


[Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

