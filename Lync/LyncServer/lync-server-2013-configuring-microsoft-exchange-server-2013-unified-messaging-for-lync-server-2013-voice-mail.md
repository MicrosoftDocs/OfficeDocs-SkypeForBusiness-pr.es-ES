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
ms.openlocfilehash: 7376ce3cbafe1321878a28e43e9bc3ab065c990f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525947"
---
# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-04_

Microsoft Lync Server 2013 permite almacenar mensajes de correo de voz en Microsoft Exchange Server 2013; Estos mensajes de correo de voz aparecerán como mensajes de correo electrónico en los buzones de los usuarios. Esta capacidad también se encuentra en las ediciones de 2010 de Lync Server y Exchange; sin embargo, el proceso de configuración de esta "mensajería unificada" se ha simplificado en las ediciones de 2013 gracias a la introducción del componente enrutador de llamadas de mensajería unificada. Este componente se instala en el servidor de acceso de cliente de Exchange 2013 y todas las llamadas a la mensajería unificada de Exchange (como un correo de voz) se enrutan primero a través del enrutador de llamadas y, a continuación, se redirigen al servidor de buzones de correo apropiado.

Si ya ha configurado la autenticación de servidor a servidor entre Lync Server 2013 y Exchange 2013, estará listo para configurar la mensajería unificada. Para ello, primero debe crear y asignar un nuevo plan de marcado de mensajería unificada en el servidor de Exchange. Por ejemplo, estos dos comandos (que se ejecutan desde dentro del shell de administración de Exchange) configuran un nuevo plan de marcado de 3 dígitos para Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor de parámetro "Secured" indican que el canal de señalización se cifra mediante la seguridad de la capa de transporte (TLS). La URIType "SipName" indica que los mensajes se enviarán y recibirán mediante el protocolo SIP y el CountryOrRegionCode 1 indica que el plan de marcado se aplica a los Estados Unidos.

En el segundo comando, el valor del parámetro que se pasa al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos nacionales que se pueden usar con este plan de marcado. El valor del parámetro "Anywhere, \* , \* , \* " define lo siguiente:

  - Nombre de grupo ("Anywhere")

  - AllowedNumberString ( \* , un carácter comodín que indica que cualquier cadena de números está permitida)

  - DialNumberString ( \* , un carácter comodín que indica que cualquier número marcado está permitido)

  - TextComment ( \* , un carácter comodín que indica que cualquier comando de texto está permitido)

<div>


> [!NOTE]  
> Al crear un nuevo plan de marcado, también se creará una directiva de buzón de correo predeterminada.



</div>

Después de crear y configurar el nuevo plan de marcado, debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y, a continuación, modificar el modo de inicio de ese servidor; en concreto, debe establecer el modo de inicio en "dual". Puede realizar ambas tareas desde dentro del shell de administración de Exchange:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Una vez configurado el servidor de mensajería unificada, debe ejecutar el cmdlet Enable-ExchangeCertificate para asegurarse de que el certificado de Exchange se aplica al servicio de mensajería unificada:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio se debe detener y reiniciar cada vez que se cambia el modo de inicio.

Después de finalizar la configuración del servidor de mensajería unificada, puede configurar el enrutador de llamadas de mensajería unificada:

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Como el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo que hospeda el enrutador de llamadas de mensajería unificada.

Para completar la configuración de la mensajería unificada, debe crear una directiva de buzón de mensajería unificada y, a continuación, usar esa Directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón de correo con un comando similar a este:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

Y puede habilitar a un usuario para la mensajería unificada mediante un comando similar a este:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario. En este ejemplo, el usuario tiene el número de extensión 100.

Una vez habilitado el buzón de correo, el usuario kenmyer@litwareinc.com debe poder usar la mensajería unificada de Exchange. Puede comprobar que el usuario se puede conectar a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) desde el shell de administración de Lync Server:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Si tiene un segundo usuario que se ha habilitado para mensajería unificada, puede usar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) para comprobar que este segundo usuario puede dejar un mensaje de correo de voz para el primer usuario.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

