---
title: 'Lync Server 2013: configuración de versiones de cliente admitidas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34d74de1ae5e25c372e51783d8321ebc8699eaef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Configuración de versiones de cliente admitidas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

En Lync Server 2013, puede configurar directivas de versión de cliente para especificar las versiones de clientes que son compatibles con su entorno. Además, puede usar la configuración de versión de cliente global para especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión y que, por lo tanto, no estén explícitamente admitidos o restringidos.

También puede usar directivas de versión de cliente para administrar las actualizaciones de cliente. Cuando establece una directiva de versión de cliente y usa las opciones **Permitir y actualizar** y **Bloquear y actualizar**, los clientes recibirán software actualizado de Windows Server Update Services (si usa este servicio) o de Microsoft Update.

<div>

## <a name="client-version-policy-settings"></a>Configuración de la directiva de versión de cliente

La Directiva de versión de cliente predeterminada requiere que todos los clientes ejecuten Lync. Si los clientes del entorno ejecutan versiones anteriores de Communicator, es posible que deba volver a configurar las reglas de versión de cliente para evitar que los clientes y dispositivos se bloqueen o se actualicen inesperadamente al conectarse a Lync Server 2013. Puede modificar la regla predeterminada o agregar una regla más alta en la lista de directivas de versiones de cliente para anular la regla predeterminada. Además, a medida que se publiquen actualizaciones acumulativas, deberá configurar la directiva de versión de cliente para pedir las últimas actualizaciones. Para obtener más información, consulte especificación de las [aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) en la documentación de operaciones.

</div>

</div>

<span> </span>

</div>

</div>

</div>

