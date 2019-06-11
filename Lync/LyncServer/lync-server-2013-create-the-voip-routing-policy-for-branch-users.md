---
title: 'Lync Server 2013: Crear la directiva de enrutamiento VoIP para usuarios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f53e69069bc1f39f84c057f1e90882d5ae0d65d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Crear la directiva de enrutamiento VoIP para usuarios de sucursal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-23_

Recomendamos crear una directiva de voz sobre IP (VoIP) distinta para los usuarios de sucursales. Esta Directiva debe contener rutas a salida de la puerta de enlace de la aplicación de rama superviviente o la puerta de enlace externa y las rutas de seguridad del servidor de sucursal Independientemente del lugar en el que esté registrado el usuario, ya sea en el registrador del equipo de sucursal o en el servidor de sucursal con la supervivencia o en el clúster de registro de backup en el sitio central, la Directiva de VoIP del usuario siempre está activa.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>Para configurar la Directiva de enrutamiento de VoIP para los usuarios de la sucursal

1.  Crear un plan de marcado de nivel de usuario y asignarlo a los usuarios de la sucursal. (Consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones).

2.  Asigne reglas de normalización que correspondan a los hábitos de marcado de los usuarios de ese sitio. Si el equipo de la sucursal o el usuario de servidor de sucursal supervivientes conmuta por error al grupo de registro de la copia de seguridad en el sitio central, el mismo plan de marcado estará vigente. (Consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones).

3.  Configure una ruta de voz que quede a partir de la puerta de enlace de la aplicación de rama superviviente o la puerta de enlace externa de servidor de sucursal. (Consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md) en la documentación de operaciones).

4.  Establezca una ruta de llamada de copia de seguridad en la sucursal con la que se haya sobreviviente o en una puerta de enlace de servidor de sucursal que pueda apuntar al grupo de registro de la copia de seguridad (en el servidor de mediación). (Consulte la documentación del fabricante de su equipo de sucursal o de su equipo de sucursal superviviente).
    
    <div>
    

    > [!NOTE]  
    > Esta configuración de la ruta de llamada de copia de seguridad ayuda a garantizar que las llamadas entrantes al usuario de la sucursal funcionen cuando la aplicación ramificada o el servidor de sucursal supervivientes no estén disponibles (por ejemplo, si está desactivado para realizar tareas de mantenimiento). Si el servidor de la aplicación de la sucursal o el servidor de la sucursal que mantiene la aplicación no están disponibles, y el usuario está registrado con el grupo de registro de la copia de seguridad en el sitio central, las llamadas entrantes se pueden enrutar al usuario.

    
    </div>

**Siguiente paso**: [configurar la configuración de redireccionamiento del correo de voz en Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

