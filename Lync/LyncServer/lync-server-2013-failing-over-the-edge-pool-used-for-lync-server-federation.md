---
title: 'Lync Server 2013: Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Si el grupo perimetral donde tiene la Federación de Lync Server configurada, debe cambiar la Federación para usar un grupo de borde diferente para que la Federación funcione.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Conmutación por error del grupo perimetral usado para la Federación de Lync Server

1.  En un servidor front-end, abra Topology Builder. Expanda **agrupaciones perimetrales**y haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales actualmente configurados para la Federación. Seleccione **Editar propiedades**.

2.  En **Editar propiedades** , en **General**, desactive **Habilitar Federación para este grupo perimetral (puerto 5061)**. Haga clic en **Aceptar**.

3.  Expanda **agrupaciones perimetrales**y haga clic con el botón secundario en el grupo de servidores perimetrales o perimetrales que desea usar para la Federación. Seleccione **Editar propiedades**.

4.  En **propiedades de edición** , en **General**, seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)**. Haga clic en **Aceptar**.

5.  Haga clic en **acción**, seleccione **topología**, seleccione **publicar**. Cuando se le solicite al **publicar la topología**, haga clic en **siguiente**. Una vez finalizada la publicación, haga clic en **Finalizar**.

6.  En el servidor perimetral, abra el Asistente para la implementación de Lync Server. Haga clic en **instalar o actualizar el sistema Lync Server**y, a continuación, haga clic en **configurar o quitar los componentes de Lync Server**. **Vuelva a**hacer clic en ejecutar.

7.  En instalación de los componentes de Lync Server, haga clic en **siguiente**. La pantalla resumen mostrará las acciones a medida que se ejecutan. Una vez que haya finalizado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.
    
    Si el sitio que contiene el grupo perimetral con error contiene servidores front-end que aún se están ejecutando, debe actualizar el servicio de conferencias web y el servicio de conferencia A/V en estos grupos front-end para usar un grupo perimetral en un sitio remoto que aún se esté ejecutando. Para obtener más información, vea [cambiar el grupo perimetral asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP en Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

