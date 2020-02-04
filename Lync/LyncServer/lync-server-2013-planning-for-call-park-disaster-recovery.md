---
title: 'Lync Server 2013: Planear la recuperación ante desastres del estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76052297e527e24fd3daf0c03d02661c7ddc255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Planear la recuperación ante desastres del estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En esta sección se describen algunas formas de preparar la aplicación de estacionamiento de llamadas para la recuperación ante desastres y algunas consideraciones para el proceso de recuperación ante desastres.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Preparación de la recuperación ante desastres de estacionamiento de llamadas

Tenga en cuenta lo siguiente cuando prepare y lleve a cabo procedimientos de recuperación ante desastres.

  - Planee la recuperación de desastres cuando realice su plan de capacidad. Para la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe poder administrar las cargas de trabajo de los servicios de estacionamiento de llamadas en ambos grupos. Para obtener más información sobre la planeación de la capacidad de estacionamiento de llamadas, consulte [planificación de la capacidad de estacionamiento de llamadas en Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durante la recuperación de desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan el servicio de estacionamiento de llamadas que se ejecuta en el grupo de copias de seguridad. Por lo tanto, la compatibilidad con el parque de llamadas durante la recuperación de desastres requiere que la aplicación de estacionamiento de llamadas se implemente y se habilite en el grupo primario y en el grupo de copia de seguridad.

  - Cada grupo debe tener un intervalo válido de números de órbita para los usuarios que estén alojados en ese grupo para usarlos en las llamadas de aparcamiento.

  - Mantenga siempre una copia de seguridad separada de cualquier música personalizada en espera que se haya cargado para el parque de llamadas. No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación de desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se hayan borrado.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Consideraciones de recuperación ante desastres de estacionamiento de llamadas

Solo puede definir un conjunto de parámetros de configuración de la aplicación de estacionamiento de llamadas y un archivo de audio de música en espera personalizado por grupo de servidores. Esta configuración incluye el umbral de tiempo de espera, la música en espera, los intentos de recogida máxima de llamadas y el URI de tiempo de espera. Para ver estas opciones de configuración, ejecute el cmdlet **Get-CsCpsConfiguration** . Para obtener más información sobre el cmdlet **Get-CsCpsConfiguration** , vea [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Durante la recuperación de desastres, el parque de llamadas usa la aplicación de estacionamiento de llamadas del grupo de copia de seguridad, por lo que no se realiza una copia de seguridad de la configuración del grupo principal. Si el repositorio principal no se puede recuperar e implementa un nuevo grupo para reemplazar el grupo primario, se perderán las opciones de configuración del grupo principal y tendrá que volver a configurar la configuración de la suspensión de llamada y los archivos de audio de música activada en el nuevo grupo.

Si implementa un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente para reemplazar el grupo primario, tendrá que reasignar todos los intervalos de órbita del parque de llamadas asociados con el grupo primario al FQDN del nuevo grupo. Para reasignar intervalos orbitales al nuevo grupo, puede usar el panel de control de Lync Server o el cmdlet **set-CsCallParkOrbit** . Para obtener más información sobre el cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

