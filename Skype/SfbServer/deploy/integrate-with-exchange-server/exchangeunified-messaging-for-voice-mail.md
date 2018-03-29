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
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a>Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype Empresarial Server 2015
 
**Resumen:** Configurar la mensajería unificada de Exchange Server para Skype Business Server para correo de voz.
  
Skype para el año 2015 de Business Server permite que los mensajes de correo de voz almacenados en 2016 de Exchange Server o Exchange Server 2013; los mensajes de correo de voz aparecerá como mensajes de correo electrónico en las bandejas de entrada de los usuarios. 
  
Si ya ha configurado la autenticación de servidor a servidor entre Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, está listo para configurar la mensajería unificada. Para ello, primero debe crear y asignar un nuevo plan de marcado de mensajería unificada en el Exchange Server. Por ejemplo, estos dos comandos (ejecutar desde el Shell de administración de Exchange) configuración un nuevo plan de marcado de 3 dígitos para Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

En el primer comando del ejemplo, el parámetro VoIPSecurity y el valor de parámetro "Secured" indican que el canal de señalización está cifrado utilizando Seguridad de la capa de transporte (TLS). El URIType "SipName" indica que se enviarán y recibirán mensajes utilizando el protocolo SIP, y el CountryOrRegionCode de 1 indica que el plan de marcado se aplica a los EE. UU.
  
En el segundo comando, el valor de parámetro transferido al parámetro ConfiguredInCountryOrRegionGroups especifica los grupos dentro del país que pueden utilizarse con este plan de marcado. El valor del parámetro "en cualquier lugar,\*,\*,\*" establece lo siguiente:
  
- Nombre de grupo ("Anywhere")
    
- AllowedNumberString (\*, un carácter comodín que indica que se permite cualquier cadena de números)
    
- DialNumberString (\*, un carácter comodín que indica que se permite cualquier número marcado)
    
- TextComment (\*, un carácter comodín que indica que se permite cualquier comando de texto)
    
> [!NOTE]
> Al crear un nuevo plan de marcado, también se crea una Directiva de buzón predeterminada. 
  
Después de crear y configurar el nuevo plan de marcado debe agregar el nuevo plan de marcado a su servidor de mensajería unificada y luego modificar el modo de inicio de ese servidor; en particular, debe establecer el modo de inicio en "Doble". Puede realizar ambas tareas desde dentro del Shell de administración de Exchange:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Después de que se ha configurado el servidor de mensajería unificado debe ejecutar a continuación el cmdlet Enable-ExchangeCertificate para garantizar que se aplica el certificado de Exchange para el servicio de mensajería unificado:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Una vez que el certificado se haya asignado correctamente, debe detener y reiniciar el servicio MsExchangeUM en el servidor de mensajería unificada. Este servicio debe detenerse y reiniciarse cada vez que cambie el modo de inicio.
  
Tras finalizar de configurar el servidor de mensajería unificada puede configurar el Enrutador de llamadas de mensajería unificada:
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Puesto que el modo de inicio ha cambiado, debe detener y reiniciar el servicio MsExchangeUMCR en el equipo donde se encuentre el Enrutador de llamadas de mensajería unificada.
  
Para completar la configuración de mensajería unificada, necesitará crear una directiva de buzón de correo de mensajería unificada y luego utilizar esa directiva para habilitar a los usuarios para la mensajería unificada. Puede crear una directiva de buzón de correo utilizando un comando similar a este:
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Y puede habilitar a un usuario para la mensajería unificada utilizando un comando similar a este:
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

En el comando anterior, el parámetro Extensions representa el número de extensión del teléfono del usuario. En este ejemplo, el usuario tiene el número de extensión 100.
  
Una vez que haya habilitado su buzón de correo, el usuario kenmyer@litwareinc.com deberá poder utilizar la mensajería unificada de Exchange. Puede comprobar que el usuario puede conectarse a la mensajería unificada de Exchange ejecutando el cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) desde dentro el Skype para el Shell de administración de servidor empresarial:
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Si tiene un segundo usuario que se ha habilitado para mensajería unificada para comprobar que este segundo usuario puede dejar un mensaje de correo de voz para el primer usuario puede utilizar el cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) .
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


