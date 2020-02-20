---
title: 'Lync Server 2013: configurar las opciones de redireccionamiento del correo de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38818a6514d4d7bce5266df57347415a600a28c8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="25b60-102">Configurar la configuración de reenrutamiento del correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25b60-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25b60-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="25b60-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="25b60-104">Las aplicaciones de sucursal con funciones de supervivencia y los servidores de sucursal con funciones de supervivencia pueden proporcionar supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la WAN, si la mensajería unificada (UM) de Exchange está instalada en el sitio central y se implementa un operador automático de mensajes de mensajería unificada (AA) de Exchange.</span><span class="sxs-lookup"><span data-stu-id="25b60-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="25b60-105">Recomendamos que su administrador de Exchange configure el Operador automático para que acepte solo mensajes, con lo cual se deshabilita el resto de la funcionalidad general como, por ejemplo, las transferencias a un usuario o a un operador.</span><span class="sxs-lookup"><span data-stu-id="25b60-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="25b60-106">También puede usar un AA genérico o un AA personalizado para enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="25b60-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="25b60-107">Para obtener más información, consulte la sección "preparación para la supervivencia del correo de voz" de [Branch-site Resiliency Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="25b60-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="25b60-108">Para configurar las funciones de supervivencia del correo de voz</span><span class="sxs-lookup"><span data-stu-id="25b60-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="25b60-109">Pida al administrador de Exchange que configure el AA para que acepte sólo mensajes (en el shell de Exchange, use el siguiente cmdlet: **set-UMAutoAttendant \<AA nombre\> -CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="25b60-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="25b60-110">El parámetro que especifica que se debe permitir dejar mensajes (*SendVoiceMsgEnabled*) es "true" de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="25b60-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="25b60-111">En el shell de administración de Lync Server, use el cmdlet **New-CSVoiceMailReroutingConfiguration** para establecer el número de teléfono AA como el número de teléfono del operador automático de mensajería unificada de Exchange en la configuración de reenrutamiento del correo de voz en la aplicación de sucursal con funciones de supervivencia o con el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="25b60-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25b60-112">Si, más tarde, necesita modificar la configuración de reenrutamiento del correo de voz, use para ello el cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="25b60-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="25b60-113">Para ver más detalles acerca de <STRONG>New-</STRONG> y <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, consulte los temas de ayuda del shell.</span><span class="sxs-lookup"><span data-stu-id="25b60-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="25b60-114">Establezca el número de acceso de suscriptor de mensajería unificada de Exchange que corresponda al plan de marcado de mensajería unificada de Exchange del usuario de sucursal como el número de acceso de suscriptor de mensajería unificada de Exchange en la configuración de reenrutamiento del correo de voz de la aplicación de sucursal con funciones de supervivencia o servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="25b60-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25b60-115">Configure el plan de marcado de los usuarios de mensajería unificada de Exchange para que solo haya un plan de marcado asociado a todos los usuarios de la sucursal que necesiten tener acceso a la funcionalidad obtener correo de voz durante una interrupción de la WAN.</span><span class="sxs-lookup"><span data-stu-id="25b60-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="25b60-116">**Paso siguiente** para las aplicaciones de sucursal con funciones de supervivencia o servidores de sucursal con funciones de supervivencia: [usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="25b60-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

