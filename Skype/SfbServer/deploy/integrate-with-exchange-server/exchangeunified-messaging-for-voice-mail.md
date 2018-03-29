---
title: Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Resumen: Configurar la mensajería unificada de Exchange Server para Skype Business Server para correo de voz.'
ms.openlocfilehash: 9f4cb3dcd43d8f6300a5fbe38bd37c40d48e8273
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a><span data-ttu-id="39856-103">Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="39856-103">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>
 
<span data-ttu-id="39856-104">**Resumen:** Configurar la mensajería unificada de Exchange Server para Skype Business Server para correo de voz.</span><span class="sxs-lookup"><span data-stu-id="39856-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="39856-105">Skype para el año 2015 de Business Server permite que los mensajes de correo de voz almacenados en 2016 de Exchange Server o Exchange Server 2013; los mensajes de correo de voz aparecerá como mensajes de correo electrónico en las bandejas de entrada de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="39856-105">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 
  
<span data-ttu-id="39856-106">Si ya ha configurado la autenticación de servidor a servidor entre Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, está listo para configurar la mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="39856-106">If you have already configured server-to-server authentication between Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="39856-107">Para ello, primero debe crear y asignar un nuevo plan de marcado de mensajería unificada en el Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="39856-107">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="39856-108">Por ejemplo, estos dos comandos (ejecutar desde el Shell de administración de Exchange) configuración un nuevo plan de marcado de 3 dígitos para Exchange:</span><span class="sxs-lookup"><span data-stu-id="39856-108">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="39856-p102">En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor de parámetro "Secured" indican que el canal de señalización está cifrado utilizando Seguridad de la capa de transporte (TLS). El URIType "SipName" indica que se enviarán y recibirán mensajes utilizando el protocolo SIP, y el CountryOrRegionCode de 1 indica que el plan de marcado se aplica a los EE. UU.</span><span class="sxs-lookup"><span data-stu-id="39856-p102">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="39856-111">En el segundo comando, el valor de parámetro transferido al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos dentro del país que pueden utilizarse con este plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="39856-111">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="39856-112">El valor del parámetro "en cualquier lugar,\*,\*,\*" establece lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39856-112">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="39856-113">Nombre de grupo ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="39856-113">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="39856-114">AllowedNumberString (\*, un carácter comodín que indica que se permite cualquier cadena de números)</span><span class="sxs-lookup"><span data-stu-id="39856-114">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="39856-115">DialNumberString (\*, un carácter comodín que indica que se permite cualquier número marcado)</span><span class="sxs-lookup"><span data-stu-id="39856-115">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="39856-116">TextComment (\*, un carácter comodín que indica que se permite cualquier comando de texto)</span><span class="sxs-lookup"><span data-stu-id="39856-116">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="39856-117">Al crear un nuevo plan de marcado, también se crea una Directiva de buzón predeterminada.</span><span class="sxs-lookup"><span data-stu-id="39856-117">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="39856-118">Después de crear y configurar el nuevo plan de marcado debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y luego modificar el modo de inicio de ese servidor; en particular, debe establecer el modo de inicio en "Doble".</span><span class="sxs-lookup"><span data-stu-id="39856-118">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="39856-119">Puede realizar ambas tareas desde dentro del Shell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="39856-119">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="39856-120">Después de que se ha configurado el servidor de mensajería unificado debe ejecutar a continuación el cmdlet Enable-ExchangeCertificate para garantizar que se aplica el certificado de Exchange para el servicio de mensajería unificado:</span><span class="sxs-lookup"><span data-stu-id="39856-120">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="39856-p105">Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio debe detenerse y reiniciarse cada vez que cambie el modo de inicio.</span><span class="sxs-lookup"><span data-stu-id="39856-p105">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="39856-123">Tras finalizar de configurar el servidor de mensajería unificada puede configurar el Enrutador de llamadas de mensajería unificada:</span><span class="sxs-lookup"><span data-stu-id="39856-123">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="39856-124">Puesto que el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo donde se encuentre el Enrutador de llamadas de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="39856-124">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="39856-p106">Para completar la configuración de mensajería unificada, necesitará crear una directiva de buzón de correo de mensajería unificada y luego utilizar esa directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón de correo utilizando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="39856-p106">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="39856-127">Y puede habilitar a un usuario para la mensajería unificada utilizando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="39856-127">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="39856-p107">En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario. En este ejemplo, el usuario tiene el número de extensión 100.</span><span class="sxs-lookup"><span data-stu-id="39856-p107">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="39856-130">Una vez que haya habilitado su buzón de correo, el usuario kenmyer@litwareinc.com deberá poder utilizar la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="39856-130">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="39856-131">Puede comprobar que el usuario puede conectarse a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) desde dentro el Skype para el Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="39856-131">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="39856-132">Si tiene un segundo usuario que se ha habilitado para mensajería unificada para comprobar que este segundo usuario puede dejar un mensaje de correo de voz para el primer usuario puede utilizar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="39856-132">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


