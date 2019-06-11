---
title: 'Lync Server 2013: Configurar los valores para volver a enrutar el correo de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="ea661-102">Configurar los valores para volver a enrutar el correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea661-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea661-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ea661-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ea661-104">Las aplicaciones de sucursales y los servidores de sucursales supervivientes pueden ofrecer una supervivencia en el correo de voz durante una interrupción de la WAN, si la mensajería unificada de Exchange se instala en el sitio central y se implementa un operador automático de mensajes de mensajería unificada de Exchange (AA).</span><span class="sxs-lookup"><span data-stu-id="ea661-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="ea661-105">Le recomendamos que el administrador de Exchange configure el AA para que acepte solo los mensajes, lo que deshabilita otras funciones genéricas, como la transferencia a un usuario o la transferencia a un operador.</span><span class="sxs-lookup"><span data-stu-id="ea661-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="ea661-106">También puede usar un AA genérico o un AA personalizado para enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="ea661-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="ea661-107">Para obtener más información, consulte la sección "prepararse para la supervivencia del correo de voz" de los [requisitos de resistencia de sitios de sucursales para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="ea661-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="ea661-108">Para configurar la supervivencia del correo de voz</span><span class="sxs-lookup"><span data-stu-id="ea661-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="ea661-109">Pida a su administrador de Exchange que configure el AA para aceptar solo los mensajes (en el shell de Exchange use el cmdlet siguiente: **set-UMAutoAttendant \<AA nombre\> -CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="ea661-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="ea661-110">El parámetro que especifica que se permite dejar mensajes (*SendVoiceMsgEnabled*) es verdadero de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ea661-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="ea661-111">En el shell de administración de Lync Server, use el cmdlet **New-CSVoiceMailReroutingConfiguration** para establecer el número de teléfono AA como el número de teléfono del operador automático de mensajería unificada de Exchange en la configuración de redireccionamiento del correo de voz en el dispositivo de sucursal con la supervivencia o Servidor de sucursal superviviente.</span><span class="sxs-lookup"><span data-stu-id="ea661-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea661-112">Si más adelante necesita modificar la configuración de redireccionamiento del correo de voz, use el cmdlet <STRONG>set-CsVoiceMailReRoutingConfiguration</STRONG> para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ea661-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="ea661-113">Para obtener más información sobre <STRONG>New-</STRONG> and <STRONG>set-CSVoiceMailReroutingConfiguration</STRONG>, vaya a los temas de ayuda de Shell.</span><span class="sxs-lookup"><span data-stu-id="ea661-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="ea661-114">Establezca el número de acceso de suscriptor de mensajería unificada de Exchange que corresponda al plan de marcado de mensajería unificada de Exchange del usuario de la sucursal como número de acceso de suscriptor de mensajería unificada de Exchange en la configuración de redireccionamiento del correo de voz en el equipo con la sucursal o el servidor de sucursal</span><span class="sxs-lookup"><span data-stu-id="ea661-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea661-115">Configure el plan de marcado de los usuarios de mensajería unificada de Exchange de modo que solo haya un plan de marcado asociado con todos los usuarios de la sucursal que necesiten acceder a la funcionalidad obtener correo de voz durante una interrupción de WAN.</span><span class="sxs-lookup"><span data-stu-id="ea661-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="ea661-116">**Paso siguiente** para los equipos de sucursales que sean revivientes o los servidores de sucursal supervivientes: [usuarios domésticos en un dispositivo o servidor de sucursal con la supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="ea661-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

