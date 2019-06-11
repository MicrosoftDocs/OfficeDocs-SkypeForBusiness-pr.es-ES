---
title: 'Lync Server 2013: ver información del dispositivo de conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4b40e0ee28f13aa6be52009b750258c5cdadffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="78586-102">Ver información de dispositivos de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78586-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78586-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="78586-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="78586-104">Puede ver información sobre los dispositivos de conferencia configurados para su uso en la organización mediante Windows PowerShell y el cmdlet **Get-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="78586-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="78586-105">Ejecute el cmdlet **Get-CsMeetingRoom** desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78586-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78586-106">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="78586-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="78586-107">Si usa el cmdlet **Get-CsMeetingRoom** sin ningún parámetro, devolverá información acerca de todos los dispositivos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="78586-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="78586-108">Los parámetros opcionales proporcionan distintas formas de filtrar la información.</span><span class="sxs-lookup"><span data-stu-id="78586-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="78586-109">Para obtener información detallada, consulte la sección parámetros de [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span><span class="sxs-lookup"><span data-stu-id="78586-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="78586-110">Ver información sobre todos los dispositivos de conferencia</span><span class="sxs-lookup"><span data-stu-id="78586-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="78586-111">Para ver los detalles de todos los dispositivos de conferencia, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="78586-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="78586-112">Este cmdlet devuelve información similar a la siguiente para cada dispositivo de conferencia.</span><span class="sxs-lookup"><span data-stu-id="78586-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="78586-113">Tenga en cuenta que en este ejemplo se muestra solo parte de la información que verá al ejecutar este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="78586-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="78586-114">Ver información sobre un dispositivo de conferencia específico</span><span class="sxs-lookup"><span data-stu-id="78586-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="78586-115">Para ver la información de un dispositivo de conferencia específico, incluya el parámetro Identity seguido de la identidad del dispositivo de conferencia (normalmente, el nombre para mostrar de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="78586-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="78586-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78586-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="78586-117">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="78586-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

