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
ms.openlocfilehash: 7cc958e5f643a18c45989d5835fd786c001899db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="7c272-102">Crear la Directiva de enrutamiento VoIP para usuarios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c272-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c272-103">_**Última modificación del tema:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="7c272-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="7c272-104">Se recomienda crear una directiva de voz sobre IP (VoIP) independiente para los usuarios de las sucursales.</span><span class="sxs-lookup"><span data-stu-id="7c272-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="7c272-105">Esta Directiva debe contener rutas a salida de la puerta de enlace de aplicación de sucursal con funciones de supervivencia o la puerta de enlace externa de servidor de sucursal con funciones de supervivencia y rutas de reserva a salidas de una puerta de enlace en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="7c272-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="7c272-106">Independientemente de dónde esté registrado el usuario, ya sea en el registrador de la aplicación de sucursal con funciones de supervivencia o en el servidor de sucursal con funciones de supervivencia o en el clúster de registrador de reserva en el sitio central, la Directiva de VoIP del usuario siempre está en vigor.</span><span class="sxs-lookup"><span data-stu-id="7c272-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="7c272-107">Para configurar la directiva de enrutamiento VoIP para usuarios de sucursal</span><span class="sxs-lookup"><span data-stu-id="7c272-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="7c272-108">Cree un plan de marcado de nivel de usuario y asígnelo a los usuarios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="7c272-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="7c272-109">(Consulte [Create a Dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones).</span><span class="sxs-lookup"><span data-stu-id="7c272-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="7c272-110">Asigne normas de normalización que se correspondan con los hábitos de marcado de los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="7c272-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="7c272-111">Si la aplicación de sucursal con funciones de supervivencia o el usuario de servidor de sucursal con funciones de supervivencia conmuta por error al grupo de registrador de reserva en el sitio central, se aplicará el mismo plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="7c272-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="7c272-112">(Consulte [Create a Dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) en la documentación de operaciones).</span><span class="sxs-lookup"><span data-stu-id="7c272-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="7c272-113">Configure una ruta de voz que quede a partir de la puerta de enlace de aplicación de sucursal con funciones de supervivencia o la puerta de enlace externa de servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="7c272-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="7c272-114">(Consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md) en la documentación de operaciones).</span><span class="sxs-lookup"><span data-stu-id="7c272-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="7c272-115">Establezca una ruta de llamada de copia de seguridad en la aplicación de sucursal con funciones de supervivencia o en la puerta de enlace de servidor de sucursal con funciones de supervivencia para indicar el grupo de registrador de reserva (combinado con el servidor de mediación) en el sitio</span><span class="sxs-lookup"><span data-stu-id="7c272-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="7c272-116">(Consulte la aplicación de sucursal con funciones de supervivencia o la documentación del proveedor de servidor de sucursal con funciones de supervivencia).</span><span class="sxs-lookup"><span data-stu-id="7c272-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c272-117">Esta copia de seguridad de ruta de llamadas ayuda a garantizar que las llamadas entrantes al usuario de la sucursal funcionarán cuando la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia no estén disponibles (por ejemplo, si está desactivada para el mantenimiento).</span><span class="sxs-lookup"><span data-stu-id="7c272-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="7c272-118">Si el servidor de el registrador y la mediación de la aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia no están disponibles, y el usuario se registra en el grupo de registrador de reserva en el sitio central, las llamadas entrantes todavía se pueden enrutar al usuario.</span><span class="sxs-lookup"><span data-stu-id="7c272-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="7c272-119">**Siguiente paso**: [configurar las opciones de reenrutamiento del correo de voz en Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7c272-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

