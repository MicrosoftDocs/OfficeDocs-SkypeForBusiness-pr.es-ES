---
title: 'Lync Server 2013: componentes usados por la recogida de llamadas de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05f41b7420f15c2815ababa0f85d8aca43898dd2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Componentes usados por la recogida de llamadas grupales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

La recogida de llamadas de grupo se implementa automáticamente al implementar la telefonía IP empresarial y la aplicación estacionamiento de llamadas. Para habilitar la recogida de llamadas de grupo, configure la tabla de órbitas de estacionamiento de llamadas con intervalos de números designados como números de grupo de atención de llamadas y, a continuación, asigne usuarios a los grupos de atención de llamadas y habilite a los usuarios para la recogida de llamadas de grupo. Los siguientes componentes de Lync Server admiten la recogida de llamadas de Grupo:

  - ****   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como la aplicación de estacionamiento de llamadas. El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.

  - **Aplicación estacionamiento de llamadas**   la aplicación de estacionamiento de llamadas es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación. La recogida de llamadas de grupo se basa en la aplicación de estacionamiento de llamadas.

  - **Shell de administración de Lync Server**   use el shell de administración de Lync Server para administrar grupos de recogida de llamadas de grupo.

  - **Herramienta del kit de recursos de SEFAUtil**   usa la utilidad de activación de la característica de extensión secundaria (SEFAUtil) para asignar usuarios a un grupo de atención de llamadas y para habilitar o deshabilitar la atención de llamadas para los usuarios.

</div>

<span> </span>

</div>

</div>

</div>

