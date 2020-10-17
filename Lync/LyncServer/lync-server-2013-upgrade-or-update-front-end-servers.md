---
title: 'Lync Server 2013: actualización o actualización de los servidores front-end'
description: 'Lync Server 2013: actualizar o actualizar los servidores front-end.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5340ca5549aeff51b275798572573b2c9f017644
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569926"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Actualizar o actualizar los servidores front-end en Lync Server 2013

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-28_

Los servidores front-end de un grupo de servidores de Enterprise Edition se organizan en *dominios de actualización*. Estos son subconjuntos de servidores front-end del grupo de servidores. El generador de topologías crea automáticamente los dominios de actualización.

Al actualizar los servidores, debe hacerlo a un dominio de actualización cada vez. Ponga a cada servidor en un dominio de actualización inactivo, actualícelo y, a continuación, reinícielo antes de pasar a otro dominio de actualización. Asegúrese de realizar un seguimiento de los dominios de actualización y los servidores que ha actualizado hasta ahora. Use el siguiente diagrama de diagrama de flujo al actualizar cada servidor.

![Actualización o mejora de los servidores front-end](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar una actualización a los servidores front-end de un grupo de servidores

1.  En un servidor front-end del grupo de servidores, ejecute el siguiente cmdlet:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Si el valor de *PoolUpgradeState* está **ocupado**, espere 10 minutos y vuelva a intentar **Get-CsPoolUpgradeReadinessState** . Si ve **ocupado** durante al menos tres veces consecutivas, después de esperar 10 minutos entre cada intento, o si ve algún resultado de **InsufficientActiveFrontEnds** para **PoolUpgradeState,** entonces hay un problema con el grupo de servidores. Si este grupo de servidores se usa junto con otro grupo de servidores front-end en una topología de recuperación ante desastres, debería realizar la conmutación por error del grupo de servidores al grupo de servidores de copia de seguridad y, a continuación, actualizar los servidores de este grupo de servidores. Para obtener más información, consulte [Failing over a Pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Si el valor de *PoolUpgradeState* es **Ready**, vaya al paso 2.

2.  El cmdlet **Get-CsPoolUpgradeReadinessState** también devuelve información sobre cada dominio de actualización del grupo y sobre qué servidores front-end hay en cada uno de los dominios de actualización. Si el valor **ReadyforUpgrade** es **true** para el dominio de actualización que contiene el servidor o los servidores que desea actualizar, puede actualizar los servidores de forma segura ahora. Para ello, haga lo siguiente:
    
    1.  Detenga las nuevas conexiones a los servidores front-end que va a actualizar con el `Stop-CsWindowsService -Graceful -Verbose` cmdlet.
        
        <div>
        

        > [!NOTE]  
        > Si va a realizar estas actualizaciones del servidor durante un tiempo de inactividad del servidor programado, puede ejecutar este cmdlet sin el parámetro<STRONG>"-</STRONG>Engrave", de la siguiente manera: <STRONG>Stop-CsWindowsService</STRONG>. Esto cerrará inmediatamente los servicios, sin tener que esperar a que todas las solicitudes de servicio existentes se rellenen.

        
        </div>
    
    2.  Actualice los servidores asociados con este dominio de actualización.
    
    3.  Reinicie los servidores y asegúrese de que aceptan nuevas conexiones.

3.  Repita los pasos 1 y 2 para cada uno de los demás dominios de actualización del grupo hasta que se hayan actualizado todos los servidores front-end.

</div>

</div>

<span> </span>

</div>

</div>

</div>

