---
title: 'Lync Server 2013: ver información de teléfono de área común'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38614b2993ddd9ad3fe3a662a334440a1d1287b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="28fef-102">Ver la información de los teléfonos comunes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28fef-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28fef-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="28fef-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="28fef-104">Puede ver información sobre los teléfonos de área común configurados para su uso en su organización mediante el cmdlet **Get-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="28fef-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="28fef-105">Si se usa sin parámetros, este cmdlet devuelve información sobre todos los teléfonos de área común.</span><span class="sxs-lookup"><span data-stu-id="28fef-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="28fef-106">Los parámetros opcionales proporcionan distintas formas de filtrar la información.</span><span class="sxs-lookup"><span data-stu-id="28fef-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="28fef-107">Por ejemplo, puede devolver todos los teléfonos de área común que tengan objetos de contacto en una unidad organizativa determinada o todos los objetos de contactos que se encuentran en un edificio especificado.</span><span class="sxs-lookup"><span data-stu-id="28fef-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="28fef-108">Para obtener más información sobre los parámetros **Get-CsCommonAreaPhone** , vea [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="28fef-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="28fef-109">Ejecute **Get-CsCommonAreaPhone** desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28fef-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="28fef-110">Ver información sobre todos los teléfonos comunes de área</span><span class="sxs-lookup"><span data-stu-id="28fef-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="28fef-111">Para ver información sobre todos los teléfonos comunes de área, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="28fef-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="28fef-112">Obtendrás información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="28fef-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="28fef-113">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="28fef-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

