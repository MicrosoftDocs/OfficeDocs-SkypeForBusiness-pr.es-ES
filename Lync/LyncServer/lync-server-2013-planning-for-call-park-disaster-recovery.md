---
title: 'Lync Server 2013: Planeación de la recuperación ante desastres del estacionamiento de llamadas'
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
ms.openlocfilehash: 74aec0a6fe0edc288dfaae57a146c52cf9a0babe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Planeación de la recuperación ante desastres del estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En esta sección se describen algunas formas de preparar la aplicación de estacionamiento de llamadas para la recuperación ante desastres y algunas consideraciones sobre el proceso de recuperación ante desastres.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Preparación para la recuperación ante desastres del estacionamiento de llamadas

Recuerde las siguientes prácticas recomendadas a la hora de preparar y llevar a cabo procedimientos de recuperación ante desastres.

  - Planee la recuperación ante desastres cuando realice la planificación de capacidad. Para la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe poder administrar las cargas de trabajo de los servicios de estacionamiento de llamadas en ambos grupos de servidores. Para obtener más información sobre la planeación de la capacidad de estacionamiento de llamadas, consulte [Capacity Planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durante la recuperación ante desastres, los usuarios que hayan sido redirigidos al grupo de servidores de copia de seguridad como parte del proceso de conmutación por error usan el servicio Estacionamiento de llamadas implementado en el grupo de servidores de copia de seguridad. Por lo tanto, la compatibilidad con el estacionamiento de llamadas durante la recuperación ante desastres requiere que la aplicación de estacionamiento de llamadas se implemente y esté habilitada tanto en el grupo principal como en el grupo de copia de seguridad.

  - Cada grupo de servidores debe tener un intervalo válido de números de órbita para que lo usen los usuarios hospedados en dicho grupo para estacionar llamadas.

  - Mantenga siempre una copia de seguridad independiente de cualquier música personalizada en espera que se haya cargado para el estacionamiento de llamadas. Estos archivos no se incluyen en la copia de seguridad como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, dañados o borrados.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Consideraciones de recuperación ante desastres del estacionamiento de llamadas

Solo puede definir un conjunto de opciones de configuración de aplicación de estacionamiento de llamadas y un archivo de audio de música en espera personalizado por grupo de servidores. Estas configuraciones incluyen el umbral de tiempo en espera, música en espera, número máximo de intentos de respuesta de llamadas y el URI del tiempo en espera. Para ver estas opciones de configuración, ejecute el cmdlet **Get-CsCpsConfiguration**. Para obtener más información sobre el cmdlet **Get-CsCpsConfiguration** , consulte [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Durante la recuperación ante desastres, el estacionamiento de llamadas usa la aplicación estacionamiento de llamadas en el grupo de servidores de copia de seguridad, por lo que no se realiza una copia de seguridad de la configuración del grupo principal. Si no se puede recuperar el grupo principal e implementa un nuevo grupo de servidores para reemplazar el grupo principal, se pierde la configuración del grupo principal y es necesario volver a configurar las opciones de estacionamiento de llamadas y los archivos de audio de música en espera personalizados en el nuevo grupo.

Si implementa un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente para reemplazar el grupo principal, tendrá que reasignar todos los intervalos de órbita de estacionamiento de llamadas asociados con el grupo principal al FQDN del nuevo grupo. Para reasignar intervalos de órbitas al nuevo grupo, puede usar el panel de control de Lync Server o el cmdlet **set-CsCallParkOrbit** . Para obtener más información sobre el cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

