---
title: 'Lync Server 2013: configuración de la mensajería unificada de Microsoft Exchange Server 2013 para Lync Server 2013 correo de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1d2bac84183e6cc274d6bb297c17401b3ff7f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="b6220-102">Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6220-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6220-103">_**Última modificación del tema:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="b6220-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="b6220-104">Microsoft Lync Server 2013 le permite tener mensajes de voz almacenados en Microsoft Exchange Server 2013; esos mensajes de voz aparecerán como mensajes de correo electrónico en las bandejas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b6220-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="b6220-105">Esta capacidad también se encontró en las ediciones de 2010 de Lync Server y Exchange; sin embargo, el proceso de configuración de esta "mensajería unificada" se ha simplificado en las ediciones de 2013 gracias a la introducción del componente de enrutador de llamadas de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="b6220-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="b6220-106">Este componente está instalado en el servidor de acceso de cliente de Exchange 2013 y todas las llamadas a la mensajería unificada de Exchange (como un buzón de voz) se enrutan primero a través del enrutador de llamadas y, a continuación, se redirigen al servidor de buzones adecuado.</span><span class="sxs-lookup"><span data-stu-id="b6220-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="b6220-107">Si ya ha configurado la autenticación de servidor a servidor entre Lync Server 2013 y Exchange 2013, estará listo para configurar la mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="b6220-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="b6220-108">Para ello, primero debe crear y asignar un nuevo plan de marcado de mensajería unificada en el servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="b6220-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="b6220-109">Por ejemplo, estos dos comandos (se ejecutan desde el shell de administración de Exchange) configurar un nuevo plan de marcado de 3 dígitos para Exchange:</span><span class="sxs-lookup"><span data-stu-id="b6220-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="b6220-p103">En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor de parámetro "Secured" indican que el canal de señalización está cifrado utilizando Seguridad de la capa de transporte (TLS). El URIType "SipName" indica que se enviarán y recibirán mensajes utilizando el protocolo SIP, y el CountryOrRegionCode de 1 indica que el plan de marcado se aplica a los EE. UU.</span><span class="sxs-lookup"><span data-stu-id="b6220-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="b6220-112">En el segundo comando, el valor de parámetro transferido al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos dentro del país que pueden utilizarse con este plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="b6220-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="b6220-113">El valor del parámetro "cualquier\*lugar\*,\*,," define lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6220-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="b6220-114">Nombre de grupo ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="b6220-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="b6220-115">AllowedNumberString (\*un carácter comodín que indica que se permite cualquier cadena de número)</span><span class="sxs-lookup"><span data-stu-id="b6220-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="b6220-116">DialNumberString (\*un carácter comodín que indica que se permite cualquier número marcado)</span><span class="sxs-lookup"><span data-stu-id="b6220-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="b6220-117">TextComment (\*un carácter comodín que indica que se permite cualquier comando de texto)</span><span class="sxs-lookup"><span data-stu-id="b6220-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6220-118">Al crear un nuevo plan de marcado, también se crea una Directiva de buzón predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b6220-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="b6220-119">Después de crear y configurar el nuevo plan de marcado debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y luego modificar el modo de inicio de ese servidor; en particular, debe establecer el modo de inicio en "Doble".</span><span class="sxs-lookup"><span data-stu-id="b6220-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="b6220-120">Puede realizar estas dos tareas desde el shell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="b6220-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="b6220-121">Una vez configurado el servidor de mensajería unificada, debe ejecutar el cmdlet enable-ExchangeCertificate para asegurarse de que el certificado de Exchange se aplica al servicio de mensajería unificada:</span><span class="sxs-lookup"><span data-stu-id="b6220-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="b6220-p106">Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio debe detenerse y reiniciarse cada vez que cambie el modo de inicio.</span><span class="sxs-lookup"><span data-stu-id="b6220-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="b6220-124">Tras finalizar de configurar el servidor de mensajería unificada puede configurar el Enrutador de llamadas de mensajería unificada:</span><span class="sxs-lookup"><span data-stu-id="b6220-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="b6220-125">Puesto que el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo donde se encuentre el Enrutador de llamadas de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="b6220-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="b6220-p107">Para completar la configuración de mensajería unificada, necesitará crear una directiva de buzón de correo de mensajería unificada y luego utilizar esa directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón de correo utilizando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="b6220-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="b6220-128">Y puede habilitar a un usuario para la mensajería unificada utilizando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="b6220-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="b6220-p108">En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario. En este ejemplo, el usuario tiene el número de extensión 100.</span><span class="sxs-lookup"><span data-stu-id="b6220-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="b6220-131">Una vez que haya habilitado su buzón de correo, el usuario kenmyer@litwareinc.com deberá poder utilizar la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b6220-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="b6220-132">Puede comprobar que el usuario se puede conectar a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b6220-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="b6220-133">Si tiene un segundo usuario que ha sido habilitado para la mensajería unificada, puede utilizar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) para verificar que este segundo usuario pueda dejar un mensaje de correo de voz para el primer usuario.</span><span class="sxs-lookup"><span data-stu-id="b6220-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

