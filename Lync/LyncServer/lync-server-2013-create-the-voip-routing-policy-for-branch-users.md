---
title: 'Lync Server 2013: crear la Directiva de enrutamiento VoIP para usuarios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308c4ad3a7371c9a27f668b79623a512227623b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Crear la Directiva de enrutamiento VoIP para usuarios de sucursal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-23_

Se recomienda crear una directiva de voz sobre IP (VoIP) independiente para los usuarios de las sucursales. Esta Directiva debe contener rutas a salida de la puerta de enlace de aplicación de sucursal con funciones de supervivencia o la puerta de enlace externa de servidor de sucursal con funciones de supervivencia y rutas de reserva a salidas de una puerta de enlace en el sitio central. Independientemente de dónde esté registrado el usuario, ya sea en el registrador de la aplicación de sucursal con funciones de supervivencia o en el servidor de sucursal con funciones de supervivencia o en el clúster de registrador de reserva en el sitio central, la Directiva de VoIP del usuario siempre está en vigor.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>Para configurar la directiva de enrutamiento VoIP para usuarios de sucursal

1.  Cree un plan de marcado de nivel de usuario y asígnelo a los usuarios de sucursal. (Consulte [Create a Dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones).

2.  Asigne normas de normalización que se correspondan con los hábitos de marcado de los usuarios de ese sitio. Si la aplicación de sucursal con funciones de supervivencia o el usuario de servidor de sucursal con funciones de supervivencia conmuta por error al grupo de registrador de reserva en el sitio central, se aplicará el mismo plan de marcado. (Consulte [Create a Dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones).

3.  Configure una ruta de voz que quede a partir de la puerta de enlace de aplicación de sucursal con funciones de supervivencia o la puerta de enlace externa de servidor de sucursal con funciones de supervivencia. (Consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md) en la documentación de operaciones).

4.  Establezca una ruta de llamada de copia de seguridad en la aplicación de sucursal con funciones de supervivencia o en la puerta de enlace de servidor de sucursal con funciones de supervivencia para indicar el grupo de registrador de reserva (combinado con el servidor de mediación) en el sitio (Consulte la aplicación de sucursal con funciones de supervivencia o la documentación del proveedor de servidor de sucursal con funciones de supervivencia).
    
    <div>
    

    > [!NOTE]  
    > Esta copia de seguridad de ruta de llamadas ayuda a garantizar que las llamadas entrantes al usuario de la sucursal funcionarán cuando la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia no estén disponibles (por ejemplo, si está desactivada para el mantenimiento). Si el servidor de el registrador y la mediación de la aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia no están disponibles, y el usuario se registra en el grupo de registrador de reserva en el sitio central, las llamadas entrantes todavía se pueden enrutar al usuario.

    
    </div>

**Siguiente paso**: [configurar las opciones de reenrutamiento del correo de voz en Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

