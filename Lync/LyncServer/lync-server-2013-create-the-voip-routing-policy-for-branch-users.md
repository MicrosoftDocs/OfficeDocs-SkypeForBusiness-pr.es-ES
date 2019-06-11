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

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="a6f6a-102">Crear la directiva de enrutamiento VoIP para usuarios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f6a-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6f6a-103">_**Última modificación del tema:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="a6f6a-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="a6f6a-104">Recomendamos crear una directiva de voz sobre IP (VoIP) distinta para los usuarios de sucursales.</span><span class="sxs-lookup"><span data-stu-id="a6f6a-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="a6f6a-105">Esta Directiva debe contener rutas a salida de la puerta de enlace de la aplicación de rama superviviente o la puerta de enlace externa y las rutas de seguridad del servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="a6f6a-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="a6f6a-106">Independientemente del lugar en el que esté registrado el usuario, ya sea en el registrador del equipo de sucursal o en el servidor de sucursal con la supervivencia o en el clúster de registro de backup en el sitio central, la Directiva de VoIP del usuario siempre está activa.</span><span class="sxs-lookup"><span data-stu-id="a6f6a-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="a6f6a-107">Para configurar la Directiva de enrutamiento de VoIP para los usuarios de la sucursal</span><span class="sxs-lookup"><span data-stu-id="a6f6a-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="a6f6a-108">Crear un plan de marcado de nivel de usuario y asignarlo a los usuarios de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="a6f6a-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="a6f6a-109">(Consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones).</span><span class="sxs-lookup"><span data-stu-id="a6f6a-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="a6f6a-110">Asigne reglas de normalización que correspondan a los hábitos de marcado de los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="a6f6a-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="a6f6a-111">Si el equipo de la sucursal o el usuario de servidor de sucursal supervivientes conmuta por error al grupo de registro de la copia de seguridad en el sitio central, el mismo plan de marcado estará vigente.</span><span class="sxs-lookup"><span data-stu-id="a6f6a-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="a6f6a-112">(Consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones).</span><span class="sxs-lookup"><span data-stu-id="a6f6a-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="a6f6a-113">Configure una ruta de voz que quede a partir de la puerta de enlace de la aplicación de rama superviviente o la puerta de enlace externa de servidor de sucursal.</span><span class="sxs-lookup"><span data-stu-id="a6f6a-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="a6f6a-114">(Consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md) en la documentación de operaciones).</span><span class="sxs-lookup"><span data-stu-id="a6f6a-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="a6f6a-115">Establezca una ruta de llamada de copia de seguridad en la sucursal con la que se haya sobreviviente o en una puerta de enlace de servidor de sucursal que pueda apuntar al grupo de registro de la copia de seguridad (en el servidor de mediación).</span><span class="sxs-lookup"><span data-stu-id="a6f6a-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="a6f6a-116">(Consulte la documentación del fabricante de su equipo de sucursal o de su equipo de sucursal superviviente).</span><span class="sxs-lookup"><span data-stu-id="a6f6a-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6f6a-117">Esta configuración de la ruta de llamada de copia de seguridad ayuda a garantizar que las llamadas entrantes al usuario de la sucursal funcionen cuando la aplicación ramificada o el servidor de sucursal supervivientes no estén disponibles (por ejemplo, si está desactivado para realizar tareas de mantenimiento).</span><span class="sxs-lookup"><span data-stu-id="a6f6a-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="a6f6a-118">Si el servidor de la aplicación de la sucursal o el servidor de la sucursal que mantiene la aplicación no están disponibles, y el usuario está registrado con el grupo de registro de la copia de seguridad en el sitio central, las llamadas entrantes se pueden enrutar al usuario.</span><span class="sxs-lookup"><span data-stu-id="a6f6a-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="a6f6a-119">**Siguiente paso**: [configurar la configuración de redireccionamiento del correo de voz en Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a6f6a-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

