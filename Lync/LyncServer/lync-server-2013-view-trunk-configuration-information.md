---
title: 'Lync Server 2013: ver la información de configuración del tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 102fb942397b8329da067d8c41c16ec393076a00
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="d606a-102">Ver la información de configuración de tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d606a-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d606a-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d606a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d606a-p101">Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d606a-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="d606a-106">Si se debe habilitar el desvío de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="d606a-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="d606a-107">Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="d606a-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="d606a-108">Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="d606a-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="d606a-109">Al instalar Microsoft Lync Server 2013, se crea una colección global de opciones de configuración de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="d606a-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="d606a-110">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="d606a-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="d606a-111">Para ver la información de configuración de tronco SIP mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d606a-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d606a-112">En el panel de control de Lync Server, haga clic en **enrutamiento de voz** y, a continuación, en **configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="d606a-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="d606a-113">En la pestaña **configuración de tronco** verá una lista de todas las colecciones de opciones de configuración de tronco; para cada colección, verá valores para las propiedades **Name**, **Scope**, **State**y **bypass de medios** , junto con el número de **usos de RTC**, **las reglas de números de llamadas**y **las reglas de números** asociados a la colección.</span><span class="sxs-lookup"><span data-stu-id="d606a-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="d606a-114">Para ver más detalles sobre una colección de opciones de configuración de tronco, haga clic en la colección de interés, en **Editar**y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d606a-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="d606a-115">Tenga en cuenta que solo puede ver información detallada para una recopilación de opciones de configuración de tronco a la vez.</span><span class="sxs-lookup"><span data-stu-id="d606a-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d606a-116">Visualización de la información de configuración de tronco SIP mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d606a-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d606a-117">Las opciones de configuración de tronco SIP se pueden ver con Lync Server PowerShell y el cmdlet Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d606a-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="d606a-118">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d606a-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="d606a-119">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="d606a-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="d606a-120">Para ver la información de configuración de tronco SIP</span><span class="sxs-lookup"><span data-stu-id="d606a-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="d606a-121">Para ver información acerca de todos los valores de configuración del tronco SIP, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="d606a-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="d606a-122">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d606a-122">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

<span data-ttu-id="d606a-123">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="d606a-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

