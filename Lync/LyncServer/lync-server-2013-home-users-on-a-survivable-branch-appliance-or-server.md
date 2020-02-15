---
title: 'Lync Server 2013: usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6efd5991260ffeec3c6279857625eadfe34eca4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="19cf0-102">Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19cf0-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19cf0-103">_**Última modificación del tema:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="19cf0-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="19cf0-104">El proceso de alojamiento de usuarios en una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia es similar al de los usuarios que se retienen en un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="19cf0-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="19cf0-105">Realice la aplicación de sucursal con funciones de supervivencia o el procedimiento de servidor de sucursal con funciones de supervivencia en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="19cf0-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="19cf0-106">Para hospedar a usuarios en un servidor o una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="19cf0-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="19cf0-107">Antes de mover usuarios al servidor de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia, abra el shell de administración de Lync Server y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="19cf0-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="19cf0-108">Ejecute el cmdlet **Test-CsPstnOutboundCall** para comprobar que el servidor de sucursal con funciones de supervivencia se está ejecutando y que se ha configurado la conectividad de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="19cf0-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="19cf0-109">Si tiene que modificar las propiedades de la puerta de enlace RTC, use el cmdlet **set-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="19cf0-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="19cf0-110">Ejecute el cmdlet **Get-CsVoicePolicy** para comprobar que los usuarios que van a estar hospedados en el servidor de sucursal con funciones de supervivencia tienen la Directiva de enrutamiento de VoIP adecuada.</span><span class="sxs-lookup"><span data-stu-id="19cf0-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="19cf0-111">Si necesita modificar la Directiva de VoIP, use el cmdlet **set-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="19cf0-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="19cf0-112">Ejecute el cmdlet **Get-CsVoicemailReroutingConfiguration** para comprobar que la configuración de reenrutamiento del correo de voz está configurada.</span><span class="sxs-lookup"><span data-stu-id="19cf0-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="19cf0-113">Si necesita modificar la configuración de reenrutamiento del correo de voz, use el cmdlet **set-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="19cf0-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="19cf0-114">En el shell de administración de Lync Server, ejecute el cmdlet **Move-CsUser** para mover usuarios domésticos.</span><span class="sxs-lookup"><span data-stu-id="19cf0-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19cf0-115">También puede usar el panel de control de Lync Server para comprobar los requisitos previos y los usuarios domésticos.</span><span class="sxs-lookup"><span data-stu-id="19cf0-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="19cf0-116">Los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia de Lync Server no pueden crear salones de chat nuevos ni ver la tarjeta de la sala para las salas existentes.</span><span class="sxs-lookup"><span data-stu-id="19cf0-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19cf0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="19cf0-117">See Also</span></span>


[<span data-ttu-id="19cf0-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="19cf0-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="19cf0-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="19cf0-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="19cf0-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="19cf0-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="19cf0-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="19cf0-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

