---
title: 'Lync Server 2013: actualizar o actualizar servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99c91a4f5fcae9f8d78bf01b19a17795916fb660
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Upgrade or update Front End Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-28_

Los servidores front-end de un grupo de servidores Enterprise Edition se organizan en *dominios de actualización*. Estos son subconjuntos de servidores front-end en el grupo. El generador de topología crea automáticamente los dominios de actualización.

Al actualizar los servidores, debe hacerlo a un dominio de actualización cada vez. Vuelva a poner cada servidor en un dominio de actualización, actualícelo y, a continuación, reinícielo antes de pasar a otro dominio de actualización. Asegúrese de realizar un seguimiento de los dominios de actualización y los servidores que ha actualizado hasta ahora. Use el siguiente diagrama de diagrama de flujo al actualizar cada servidor.

![42ed59a4-1c26-49f7-ade4-a5a788457ab9] (images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "42ed59a4-1c26-49f7-ade4-a5a788457ab9")

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar una actualización a los servidores front-end de un grupo de servidores

1.  En un servidor front-end del grupo, ejecute el siguiente cmdlet:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Si el valor de *PoolUpgradeState* está **ocupado**, espera 10 minutos y vuelve a probar **Get-CsPoolUpgradeReadinessState** . Si ve **ocupado** durante al menos tres veces consecutivas, después de esperar 10 minutos entre cada intento, o si ve cualquier resultado de **InsufficientActiveFrontEnds** para **PoolUpgradeState,** entonces hay un problema con el grupo. Si este grupo está emparejado con otro grupo de servidores front-end en una topología de recuperación ante desastres, debe dar error a la agrupación y, a continuación, actualizar los servidores de este grupo. Para obtener más información, consulte [errores en un grupo en Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Si el valor de *PoolUpgradeState* está **listo**, vaya al paso 2.

2.  El cmdlet **Get-CsPoolUpgradeReadinessState** también devuelve información acerca de cada dominio de actualización del grupo y acerca de qué servidores front-end se encuentran en cada uno de los dominios de actualización. Si el valor **ReadyforUpgrade** es **verdadero** para el dominio de actualización que contiene el servidor o los servidores que desea actualizar, puede actualizarlos de forma segura ahora. Para ello, haga lo siguiente:
    
    1.  Detenga las nuevas conexiones a los servidores front-end que va a actualizar con el `Stop-CsWindowsService -Graceful -Verbose` cmdlet.
        
        <div>
        

        > [!NOTE]  
        > Si va a realizar estas actualizaciones del servidor durante un tiempo de inactividad del servidor programado, puede ejecutar este cmdlet<STRONG></STRONG>sin el parámetro "-acNormal", de la siguiente manera: <STRONG>Stop-CsWindowsService</STRONG>. Esto cerrará inmediatamente los servicios, sin tener que esperar a que se completen todas las solicitudes de servicio existentes.

        
        </div>
    
    2.  Actualice los servidores asociados con este dominio de actualización.
    
    3.  Reinicie los servidores y asegúrese de que acepten nuevas conexiones.

3.  Repita los pasos 1 y 2 para cada uno de los dominios de actualización del grupo, hasta que se hayan actualizado todos los servidores de aplicaciones para el usuario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

