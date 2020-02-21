---
title: 'Lync Server 2013: configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebce894ae93b9071a880b35dffd039225b5485cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="06821-102">Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06821-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06821-103">_**Última modificación del tema:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="06821-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="06821-104">Microsoft Lync Server 2013 permite almacenar mensajes de correo de voz en Microsoft Exchange Server 2013; Estos mensajes de correo de voz aparecerán como mensajes de correo electrónico en los buzones de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="06821-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="06821-105">Esta capacidad también se encuentra en las ediciones de 2010 de Lync Server y Exchange; sin embargo, el proceso de configuración de esta "mensajería unificada" se ha simplificado en las ediciones de 2013 gracias a la introducción del componente enrutador de llamadas de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="06821-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="06821-106">Este componente se instala en el servidor de acceso de cliente de Exchange 2013 y todas las llamadas a la mensajería unificada de Exchange (como un correo de voz) se enrutan primero a través del enrutador de llamadas y, a continuación, se redirigen al servidor de buzones de correo apropiado.</span><span class="sxs-lookup"><span data-stu-id="06821-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="06821-107">Si ya ha configurado la autenticación de servidor a servidor entre Lync Server 2013 y Exchange 2013, estará listo para configurar la mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="06821-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="06821-108">Para ello, primero debe crear y asignar un nuevo plan de marcado de mensajería unificada en el servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="06821-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="06821-109">Por ejemplo, estos dos comandos (que se ejecutan desde dentro del shell de administración de Exchange) configuran un nuevo plan de marcado de 3 dígitos para Exchange:</span><span class="sxs-lookup"><span data-stu-id="06821-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="06821-110">En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor de parámetro "Secured" indican que el canal de señalización se cifra mediante la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="06821-110">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="06821-111">La URIType "SipName" indica que los mensajes se enviarán y recibirán mediante el protocolo SIP y el CountryOrRegionCode 1 indica que el plan de marcado se aplica a los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="06821-111">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="06821-112">En el segundo comando, el valor del parámetro que se pasa al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos nacionales que se pueden usar con este plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="06821-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="06821-113">El valor del parámetro "Anywhere\*,\*,\*," define lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="06821-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="06821-114">Nombre de grupo ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="06821-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="06821-115">AllowedNumberString (\*, un carácter comodín que indica que cualquier cadena de números está permitida)</span><span class="sxs-lookup"><span data-stu-id="06821-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="06821-116">DialNumberString (\*, un carácter comodín que indica que cualquier número marcado está permitido)</span><span class="sxs-lookup"><span data-stu-id="06821-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="06821-117">TextComment (\*, un carácter comodín que indica que cualquier comando de texto está permitido)</span><span class="sxs-lookup"><span data-stu-id="06821-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06821-118">Al crear un nuevo plan de marcado, también se creará una directiva de buzón de correo predeterminada.</span><span class="sxs-lookup"><span data-stu-id="06821-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="06821-119">Después de crear y configurar el nuevo plan de marcado, debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y, a continuación, modificar el modo de inicio de ese servidor; en concreto, debe establecer el modo de inicio en "dual".</span><span class="sxs-lookup"><span data-stu-id="06821-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="06821-120">Puede realizar ambas tareas desde dentro del shell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="06821-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="06821-121">Una vez configurado el servidor de mensajería unificada, debe ejecutar el cmdlet enable-ExchangeCertificate para asegurarse de que el certificado de Exchange se aplica al servicio de mensajería unificada:</span><span class="sxs-lookup"><span data-stu-id="06821-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="06821-122">Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="06821-122">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server.</span></span> <span data-ttu-id="06821-123">Este servicio se debe detener y reiniciar cada vez que se cambia el modo de inicio.</span><span class="sxs-lookup"><span data-stu-id="06821-123">This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="06821-124">Después de finalizar la configuración del servidor de mensajería unificada, puede configurar el enrutador de llamadas de mensajería unificada:</span><span class="sxs-lookup"><span data-stu-id="06821-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="06821-125">Como el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo que hospeda el enrutador de llamadas de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="06821-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="06821-126">Para completar la configuración de la mensajería unificada, debe crear una directiva de buzón de mensajería unificada y, a continuación, usar esa Directiva para habilitar a los usuarios para la mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="06821-126">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging.</span></span> <span data-ttu-id="06821-127">Puede crear una directiva de buzón de correo con un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="06821-127">You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="06821-128">Y puede habilitar a un usuario para la mensajería unificada mediante un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="06821-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="06821-129">En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="06821-129">In the preceding command, the Extensions parameter represents the telephone extension number for the user.</span></span> <span data-ttu-id="06821-130">En este ejemplo, el usuario tiene el número de extensión 100.</span><span class="sxs-lookup"><span data-stu-id="06821-130">In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="06821-131">Una vez habilitado el buzón de correo, el usuario kenmyer@litwareinc.com debe poder usar la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="06821-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="06821-132">Puede comprobar que el usuario se puede conectar a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="06821-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="06821-133">Si tiene un segundo usuario que se ha habilitado para mensajería unificada, puede usar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) para comprobar que este segundo usuario puede dejar un mensaje de correo de voz para el primer usuario.</span><span class="sxs-lookup"><span data-stu-id="06821-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

