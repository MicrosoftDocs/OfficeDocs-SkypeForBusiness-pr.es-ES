---
title: "Config. mensajería unif. MS Exchange Server 2013 para correo voz MS Lync Server 2013"
TOCTitle: "Conf. de la mess. un. MES 2013 pour mess. voc. Microsoft LS 2013"
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49888908
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013

 

_**Última modificación del tema:** 2013-02-04_

Microsoft Lync Server 2013 le permite tener mensajes de correo de voz almacenados en Microsoft Exchange Server 2013; esos mensajes de correo de voz aparecerán luego como mensajes de correo electrónico en las bandejas de entrada de sus usuarios. Esta capacidad también se encontraba en las ediciones de 2010 de Lync Server y Exchange; sin embargo, el proceso de configuración de esta "mensajería unificada" se ha simplificado en las ediciones de 2013 gracias a la introducción del componente Enrutador de llamadas de mensajería unificada. Este componente se instala en el servidor Acceso de clientes de Exchange 2013, y todas las llamadas realizadas a la mensajería unificada de Exchange (como un correo de voz) se enrutan primero a través del Enrutador de llamadas y luego se restringen al servidor Buzón de correo apropiado.

Si ya ha configurado la autenticación de servidor a servidor entre Lync Server 2013 y Exchange 2013, está listo para configurar la mensajería instantánea. Para realizar eso, debe primero crear y asignar un nuevo plan de marcado de mensajería unificada en su servidor de Exchange. Por ejemplo, estos dos comandos (ejecutados desde el Shell de administración de Exchange) configuran un nuevo plan de marcado de tres dígitos para Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor de parámetro "Secured" indican que el canal de señalización está cifrado utilizando Seguridad de la capa de transporte (TLS). El URIType "SipName" indica que se enviarán y recibirán mensajes utilizando el protocolo SIP, y el CountryOrRegionCode de 1 indica que el plan de marcado se aplica a los EE. UU.

En el segundo comando, el valor de parámetro transferido al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos dentro del país que pueden utilizarse con este plan de marcado. El valor de parámetro "Anywhere,\*,\*,\*" establece lo siguiente:

  - Nombre de grupo ("Anywhere")

  - AllowedNumberString (\*, un carácter comodín que indica que cualquier cadena de números está permitida)

  - DialNumberString (\*, un carácter comodín que indica que cualquier número marcado está permitido)

  - TextComment (\*, un carácter comodín que indica que cualquier comando de texto está permitido)

Después de crear y configurar el nuevo plan de marcado debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y luego modificar el modo de inicio de ese servidor; en particular, debe establecer el modo de inicio en "Doble". Puede realizar ambas tareas desde el Shell de administración de Exchange:

    Set-UmServer -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Una vez que se haya configurado el servidor de mensajería unificada, debe ejecutar el cmdlet Enable-ExchangeCertificate para asegurarse que su certificado de Exchange se aplica al servicio de mensajería unificada:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio debe detenerse y reiniciarse cada vez que cambie el modo de inicio.

Tras finalizar de configurar el servidor de mensajería unificada puede configurar el Enrutador de llamadas de mensajería unificada:

    Set-CsUMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Puesto que el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo donde se encuentre el Enrutador de llamadas de mensajería unificada.

Para completar la configuración de mensajería unificada, necesitará crear una directiva de buzón de correo de mensajería unificada y luego utilizar esa directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón de correo utilizando un comando similar a este:

    New-UMMailboxPolicy -ID "RedmondMailboxPolicy" -AllowedCountryOrRegionGroups "Anywhere"

Y puede habilitar a un usuario para la mensajería unificada utilizando un comando similar a este:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario. En este ejemplo, el usuario tiene el número de extensión 100.

Una vez que haya habilitado su buzón de correo, el usuario kenmyer@litwareinc.com deberá poder utilizar la mensajería unificada de Exchange. Puede verificar que el usuario se pueda conectar a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMConnectivity) desde el Shell de administración de Lync Server:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Si tiene un segundo usuario que ha sido habilitado para la mensajería unificada, puede utilizar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMVoiceMail) para verificar que este segundo usuario pueda dejar un mensaje de correo de voz para el primer usuario.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

