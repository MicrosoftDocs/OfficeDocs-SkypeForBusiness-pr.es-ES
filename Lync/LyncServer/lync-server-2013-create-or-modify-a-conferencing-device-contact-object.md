---
title: 'Lync Server 2013: crear o modificar un objeto de contacto de dispositivo de conferencia'
description: 'Lync Server 2013: cree o modifique un objeto de contacto de dispositivo de conferencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853ee1c7dfda2fda99431b8cc1a5210a51f39a4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578016"
---
# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="37783-103">Crear o modificar un objeto de contacto de dispositivos de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37783-103">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37783-104">_**Última modificación del tema:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="37783-104">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="37783-105">Para crear un objeto de sala de conferencias, primero cree una cuenta de usuario de Active Directory que represente el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="37783-105">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="37783-106">A continuación, use el cmdlet **enable-CsMeetingRoom** para habilitar esa cuenta para que funcione como un dispositivo de conferencia.</span><span class="sxs-lookup"><span data-stu-id="37783-106">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="37783-107">Si necesita cambiar las propiedades de un dispositivo de conferencia existente, use el cmdlet **set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="37783-107">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="37783-108">Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37783-108">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37783-109">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="37783-109">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="37783-110">Crear un dispositivo de conferencia</span><span class="sxs-lookup"><span data-stu-id="37783-110">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="37783-111">Después de crear la cuenta de usuario de Active Directory que representa el nuevo dispositivo de conferencia, habilítelo mediante el cmdlet **enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="37783-111">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="37783-112">Asegúrese de incluir a) la identidad del dispositivo de conferencia, b) el grupo de registrador en el que se va a hospedar la cuenta de la sala y c) la dirección SIP que se va a asignar a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="37783-112">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="37783-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="37783-113">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="37783-114">Modificación de un dispositivo de conferencia</span><span class="sxs-lookup"><span data-stu-id="37783-114">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="37783-115">Para modificar los valores de propiedad de un dispositivo de conferencia existente, use el cmdlet **set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="37783-115">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="37783-116">Por ejemplo, el siguiente comando actualiza el número de teléfono (LineUri) asociado con un dispositivo de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="37783-116">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="37783-117">Para obtener más información, consulte los temas de ayuda para el cmdlet [enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) y el cmdlet [set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="37783-117">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

