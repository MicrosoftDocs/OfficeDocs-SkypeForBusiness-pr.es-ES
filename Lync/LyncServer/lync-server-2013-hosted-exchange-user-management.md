---
title: 'Lync Server 2013: Administración de usuarios de Hosted Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead9762c67f3239f84cc1290b4ff2e9acc976318
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="de562-102">Administración de usuarios de Hosted Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de562-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de562-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="de562-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="de562-104">Para proporcionar servicios de correo de voz para los usuarios de Lync Server 2013 cuyos buzones se encuentran en un servicio de Exchange hospedado, debe habilitar sus cuentas de usuario para el correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="de562-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de562-105">Para que un usuario de Lync Server 2013 pueda estar habilitado para el correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a la cuenta de usuario correspondiente.</span><span class="sxs-lookup"><span data-stu-id="de562-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="de562-106">La Directiva puede ser global, de sitio o por usuario en ámbito, siempre que se aplique al usuario que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="de562-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="de562-107">Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="de562-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="de562-108">El atributo msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="de562-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="de562-109">Lync Server 2013 introduce un nuevo atributo de usuario denominado **msExchUCVoiceMailSettings**, que se crea como parte de la preparación del esquema de Active Directory de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de562-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="de562-110">Este atributo multivalor tiene la configuración del correo de voz compartida por Lync Server 2013 y el servicio hospedado de Exchange.</span><span class="sxs-lookup"><span data-stu-id="de562-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="de562-111">En algunos casos, el servicio hospedado de Exchange puede establecer el valor del atributo msExchUCVoiceMailSettings en el proceso de habilitar la mensajería unificada de Exchange o durante el proceso de transferencia de buzones a un servidor de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="de562-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="de562-112">Si Exchange no establece este atributo, el administrador de Lync Server 2013 debe establecerlo ejecutando el cmdlet Set-CsUser, tal y como se describió anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="de562-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="de562-113">En la tabla siguiente se muestran los pares de clave y valor del atributo y sus autores.</span><span class="sxs-lookup"><span data-stu-id="de562-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="de562-114">Pares clave/valor de atributo msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="de562-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de562-115">Valor</span><span class="sxs-lookup"><span data-stu-id="de562-115">Value</span></span></th>
<th><span data-ttu-id="de562-116">Autorización</span><span class="sxs-lookup"><span data-stu-id="de562-116">Author</span></span></th>
<th><span data-ttu-id="de562-117">Significado</span><span class="sxs-lookup"><span data-stu-id="de562-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de562-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="de562-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="de562-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="de562-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="de562-120">El usuario ha habilitado el acceso a UM hospedado en el servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="de562-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="de562-121">La aplicación de enrutamiento de mensajería unificada de Exchange verificará la Directiva de correo de voz hospedada del usuario para ver los detalles de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="de562-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de562-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="de562-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="de562-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="de562-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="de562-124">El usuario ha deshabilitado el acceso a UM hospedado por parte de Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="de562-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de562-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="de562-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="de562-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="de562-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="de562-127">El usuario ha sido habilitado para el acceso a UM hospedado por Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de562-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="de562-128">La aplicación de enrutamiento ExUM de Lync Server 2013 verificará la Directiva de correo de voz hospedada del usuario para ver los detalles de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="de562-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de562-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="de562-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="de562-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="de562-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="de562-131">Lync Server 2013 ha deshabilitado al usuario para el acceso a mensajería unificada hospedada.</span><span class="sxs-lookup"><span data-stu-id="de562-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="de562-132">Si el atributo ya tiene valores distintos de uno de los pares de clave y valor de Lync Server 2013 (CSHostedVoiceMail = 0 o CSHostedVoiceMail = 1), una advertencia indicará que el atributo puede ser administrado por otra aplicación distinta.</span><span class="sxs-lookup"><span data-stu-id="de562-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="de562-133">Por ejemplo, se muestra una advertencia si el par clave/valor ExchangeHostedVoiceMail = 0 o ExchangeHostedVoiceMail = 1 ya está presente.</span><span class="sxs-lookup"><span data-stu-id="de562-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="de562-134">En ese caso, puede cambiar el valor editándolo en Active Directory o ejecutar el cmdlet siguiente para establecer el valor en NULL:</span><span class="sxs-lookup"><span data-stu-id="de562-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="de562-135">Set-CsUser-Identity User-HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="de562-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="de562-136">Habilitar usuarios para el correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="de562-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="de562-137">Para permitir que las llamadas de correo de voz de un usuario se enruten a la mensajería unificada de Exchange hospedada, debe ejecutar el cmdlet Set-CsUser para establecer el valor del parámetro *HostedVoiceMail* .</span><span class="sxs-lookup"><span data-stu-id="de562-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="de562-138">Este parámetro también indica Lync Server 2013 para que se ilumine el indicador "llamar al correo de voz".</span><span class="sxs-lookup"><span data-stu-id="de562-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="de562-139">En el siguiente ejemplo se habilita la cuenta de usuario de Pilar Ackerman para el correo de voz hospedado:</span><span class="sxs-lookup"><span data-stu-id="de562-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="de562-140">El cmdlet verifica que se aplica una directiva de correo de voz hospedada (global, de sitio o por usuario) a este usuario.</span><span class="sxs-lookup"><span data-stu-id="de562-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="de562-141">Si no se aplica ninguna directiva, se produce un error en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="de562-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="de562-142">En el ejemplo siguiente se deshabilita la cuenta de usuario de Pilar Ackerman para el correo de voz hospedado:</span><span class="sxs-lookup"><span data-stu-id="de562-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="de562-143">El cmdlet verifica que no se aplica ninguna directiva de correo de voz hospedada (global, de sitio o por usuario) a este usuario.</span><span class="sxs-lookup"><span data-stu-id="de562-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="de562-144">Si se aplica una directiva, se produce un error en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="de562-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="de562-145">Para obtener más información sobre cómo usar el cmdlet Set-CsUser, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de562-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

