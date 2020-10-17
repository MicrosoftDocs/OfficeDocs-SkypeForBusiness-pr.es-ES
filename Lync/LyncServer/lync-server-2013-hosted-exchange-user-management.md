---
title: 'Lync Server 2013: administración de usuarios hospedados de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a54c4a7a3833fdd31999d7613659f9a35f9732
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504207"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="d9cbb-102">Administración de usuarios de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9cbb-102">Hosted Exchange user management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9cbb-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d9cbb-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d9cbb-104">Para proporcionar servicios de correo de voz para Lync Server 2013 usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado, debe habilitar sus cuentas de usuario para el correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9cbb-105">Antes de que un usuario de Lync Server 2013 pueda estar habilitado para el correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a la cuenta de usuario correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="d9cbb-106">La directiva puede ser de ámbito global, de sitio o de usuario, siempre y cuando se aplique al usuario que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="d9cbb-107">Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="d9cbb-108">El atributo msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="d9cbb-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="d9cbb-109">Lync Server 2013 presenta un nuevo atributo de usuario denominado **msExchUCVoiceMailSettings**, que se crea como parte de la preparación del esquema de Active Directory de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="d9cbb-110">Este atributo multivalor contiene la configuración del correo de voz que se comparte con Lync Server 2013 y el servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="d9cbb-111">En algunos casos, el servicio de Exchange hospedado puede definir el valor del atributo msExchUCVoiceMailSettings durante el proceso de habilitación de la mensajería unificada de Exchange, o bien durante el proceso de transferencia de buzones de correo a un servidor hospedado de Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="d9cbb-112">Si Exchange no establece este atributo, el administrador de Lync Server 2013 debe establecerlo ejecutando el cmdlet Set-CsUser, tal y como se ha descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="d9cbb-113">En la tabla a continuación se muestran los pares clave/valor del atributo y sus autores.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="d9cbb-114">Los pares clave/valor del atributo msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="d9cbb-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9cbb-115">Valor</span><span class="sxs-lookup"><span data-stu-id="d9cbb-115">Value</span></span></th>
<th><span data-ttu-id="d9cbb-116">Autor</span><span class="sxs-lookup"><span data-stu-id="d9cbb-116">Author</span></span></th>
<th><span data-ttu-id="d9cbb-117">Significado</span><span class="sxs-lookup"><span data-stu-id="d9cbb-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9cbb-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="d9cbb-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="d9cbb-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9cbb-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="d9cbb-120">Exchange Server ha habilitado al usuario para el acceso a la mensajería unificada hospedada.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="d9cbb-121">La aplicación de enrutamiento de mensajería unificada de Exchange comprobará la Directiva de correo de voz hospedado del usuario para ver los detalles de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9cbb-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="d9cbb-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="d9cbb-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9cbb-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="d9cbb-124">Exchange Server ha deshabilitado al usuario para el acceso a la mensajería unificada hospedada.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9cbb-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="d9cbb-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="d9cbb-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="d9cbb-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="d9cbb-127">Lync Server 2013 ha habilitado al usuario para el acceso a la mensajería unificada hospedada.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="d9cbb-128">La aplicación Lync Server 2013 ExUM Routing comprobará la Directiva de correo de voz hospedado del usuario para obtener detalles de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9cbb-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="d9cbb-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="d9cbb-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="d9cbb-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="d9cbb-131">Lync Server 2013 ha deshabilitado al usuario para el acceso a la mensajería unificada hospedada.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d9cbb-132">Si el atributo ya tiene valores distintos de uno de los pares de clave/valor de Lync Server 2013 (CSHostedVoiceMail = 0 o CSHostedVoiceMail = 1), una advertencia indicará que el atributo puede ser administrado por una aplicación diferente.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="d9cbb-133">Por ejemplo, se muestra una advertencia si el par clave/valor ExchangeHostedVoiceMail=0 o ExchangeHostedVoiceMail=1 ya está presente.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="d9cbb-134">En tal caso, puede cambiar el valor editándolo en Active Directory, o bien ejecute el cmdlet siguiente para definir el valor como nulo:</span><span class="sxs-lookup"><span data-stu-id="d9cbb-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="d9cbb-135">Set-CsUser –identity user –HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="d9cbb-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="d9cbb-136">Habilitación de usuarios para correo de voz hospedado</span><span class="sxs-lookup"><span data-stu-id="d9cbb-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="d9cbb-137">Para habilitar las llamadas de correo de voz de un usuario para que se redirijan a la mensajería unificada hospedada de Exchange, ejecute el cmdlet Set-CsUser para definir el valor del parámetro *HostedVoiceMail*.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="d9cbb-138">Este parámetro también indica a Lync Server 2013 que debe aclarar el indicador "llamar al correo de voz".</span><span class="sxs-lookup"><span data-stu-id="d9cbb-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="d9cbb-139">En el ejemplo siguiente se habilita la cuenta de usuario de Pilar Ackerman para correo de voz hospedado:</span><span class="sxs-lookup"><span data-stu-id="d9cbb-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="d9cbb-p108">El cmdlet comprueba que una directiva de correo de voz hospedado (global, de nivel de sitio o por usuario) se aplique al usuario. Si no se aplica ninguna directiva, el cmdlet no se completará correctamente.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-p108">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user. If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="d9cbb-142">En el ejemplo siguiente se deshabilita la cuenta de usuario de Pilar Ackerman para correo de voz hospedado:</span><span class="sxs-lookup"><span data-stu-id="d9cbb-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="d9cbb-p109">El cmdlet comprueba que ninguna directiva de correo de voz hospedado (global, de nivel de sitio o por usuario) se aplique al usuario. Si se aplica alguna directiva, el cmdlet no se completará correctamente.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-p109">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user. If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="d9cbb-145">Para obtener información detallada sobre cómo usar el cmdlet Set-CsUser, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9cbb-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

