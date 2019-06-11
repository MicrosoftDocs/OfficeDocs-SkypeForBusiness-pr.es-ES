---
title: 'Lync Server 2013: configuración de versiones de cliente compatibles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14bc6decfea38151d1f060b13fa55c81006e98e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Configuración de las versiones de cliente compatibles en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

En Lync Server 2013, puede configurar directivas de versión de cliente para especificar las versiones de clientes que son compatibles con su entorno. Además, puede usar la configuración de la versión de cliente global para especificar una acción predeterminada para clientes que aún no tienen una directiva de versión definida y, por lo tanto, no se admiten o restringen explícitamente.

También puede usar las directivas de versión de cliente para administrar las actualizaciones de cliente. Al establecer una directiva de versión de cliente y usar las opciones **permitir y actualizar** , y **bloquear y actualizar**, los clientes recibirán software actualizado del servicio de actualización de Windows Server (si está usando este servicio) o de Microsoft Update.

<div>

## <a name="client-version-policy-settings"></a>Configuración de la Directiva de versión del cliente

La Directiva de versión de cliente predeterminada requiere que todos los clientes ejecuten Lync. Si los clientes de su entorno ejecutan versiones anteriores de Communicator, es posible que tenga que volver a configurar las reglas de versión de cliente para evitar que los clientes y dispositivos se bloqueen o actualicen de forma inesperada al conectarse a Lync Server 2013. Puede modificar la regla predeterminada o puede Agregar una regla en la lista de directivas de versión de cliente para invalidar la regla predeterminada. Además, a medida que se publican las actualizaciones acumulativas (CUs), debe configurar la Directiva de versión del cliente para que requiera las actualizaciones más recientes. Para obtener más información, vea [especificar las aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) en la documentación de operaciones.

</div>

</div>

<span> </span>

</div>

</div>

</div>

