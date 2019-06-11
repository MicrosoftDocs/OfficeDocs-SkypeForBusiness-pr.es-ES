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

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-04_

Microsoft Lync Server 2013 le permite tener mensajes de voz almacenados en Microsoft Exchange Server 2013; esos mensajes de voz aparecerán como mensajes de correo electrónico en las bandejas de los usuarios. Esta capacidad también se encontró en las ediciones de 2010 de Lync Server y Exchange; sin embargo, el proceso de configuración de esta "mensajería unificada" se ha simplificado en las ediciones de 2013 gracias a la introducción del componente de enrutador de llamadas de mensajería unificada. Este componente está instalado en el servidor de acceso de cliente de Exchange 2013 y todas las llamadas a la mensajería unificada de Exchange (como un buzón de voz) se enrutan primero a través del enrutador de llamadas y, a continuación, se redirigen al servidor de buzones adecuado.

Si ya ha configurado la autenticación de servidor a servidor entre Lync Server 2013 y Exchange 2013, estará listo para configurar la mensajería unificada. Para ello, primero debe crear y asignar un nuevo plan de marcado de mensajería unificada en el servidor Exchange. Por ejemplo, estos dos comandos (se ejecutan desde el shell de administración de Exchange) configurar un nuevo plan de marcado de 3 dígitos para Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor de parámetro "Secured" indican que el canal de señalización está cifrado utilizando Seguridad de la capa de transporte (TLS). El URIType "SipName" indica que se enviarán y recibirán mensajes utilizando el protocolo SIP, y el CountryOrRegionCode de 1 indica que el plan de marcado se aplica a los EE. UU.

En el segundo comando, el valor de parámetro transferido al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos dentro del país que pueden utilizarse con este plan de marcado. El valor del parámetro "cualquier\*lugar\*,\*,," define lo siguiente:

  - Nombre de grupo ("Anywhere")

  - AllowedNumberString (\*un carácter comodín que indica que se permite cualquier cadena de número)

  - DialNumberString (\*un carácter comodín que indica que se permite cualquier número marcado)

  - TextComment (\*un carácter comodín que indica que se permite cualquier comando de texto)

<div>


> [!NOTE]  
> Al crear un nuevo plan de marcado, también se crea una Directiva de buzón predeterminada.



</div>

Después de crear y configurar el nuevo plan de marcado debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y luego modificar el modo de inicio de ese servidor; en particular, debe establecer el modo de inicio en "Doble". Puede realizar estas dos tareas desde el shell de administración de Exchange:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Una vez configurado el servidor de mensajería unificada, debe ejecutar el cmdlet enable-ExchangeCertificate para asegurarse de que el certificado de Exchange se aplica al servicio de mensajería unificada:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio debe detenerse y reiniciarse cada vez que cambie el modo de inicio.

Tras finalizar de configurar el servidor de mensajería unificada puede configurar el Enrutador de llamadas de mensajería unificada:

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Puesto que el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo donde se encuentre el Enrutador de llamadas de mensajería unificada.

Para completar la configuración de mensajería unificada, necesitará crear una directiva de buzón de correo de mensajería unificada y luego utilizar esa directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón de correo utilizando un comando similar a este:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

Y puede habilitar a un usuario para la mensajería unificada utilizando un comando similar a este:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario. En este ejemplo, el usuario tiene el número de extensión 100.

Una vez que haya habilitado su buzón de correo, el usuario kenmyer@litwareinc.com deberá poder utilizar la mensajería unificada de Exchange. Puede comprobar que el usuario se puede conectar a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) desde el shell de administración de Lync Server:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Si tiene un segundo usuario que ha sido habilitado para la mensajería unificada, puede utilizar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) para verificar que este segundo usuario pueda dejar un mensaje de correo de voz para el primer usuario.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

