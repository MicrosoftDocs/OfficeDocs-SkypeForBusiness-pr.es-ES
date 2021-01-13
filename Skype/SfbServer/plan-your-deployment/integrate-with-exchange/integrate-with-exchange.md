---
title: Plan para la integración de Skype Empresarial y Exchange
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumen: revise este tema para obtener información sobre cómo integrar Skype Empresarial Server con Exchange Server 2016 o Exchange Server 2013.'
ms.openlocfilehash: f2a9dfc718b7891a0cbe9b7b1455df24531a6ed0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810106"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan para la integración de Skype Empresarial y Exchange
 
**Resumen:** Revise este tema para obtener información sobre cómo integrar Skype Empresarial Server con Exchange Server 2016 o Exchange Server 2013.
  
Antes de poder integrar Skype Empresarial Server y Exchange Server, debe asegurarse de que tanto Exchange Server como Skype Empresarial Server estén completamente instalados y en funcionamiento. 
  
Para obtener más información sobre Exchange Server instalación, consulte la documentación Exchange Server planeamiento e implementación de su versión de Exchange. 
   
Una vez que los servidores estén en funcionamiento, debe asignar certificados de autenticación de servidor a servidor a Skype Empresarial Server y Exchange Server; Estos certificados permiten a Skype Empresarial Server y Exchange Server intercambiar información y comunicarse entre sí. Al instalar el Exchange Server, se crea automáticamente un certificado autofirmado con el nombre Microsoft Exchange Server certificado de autenticación. Este certificado, que puede encontrarse en el almacén de certificados del equipo local, debe usarse para la autenticación de servidor a servidor en Exchange Server. Para obtener más información acerca de la asignación de certificados Exchange Server, vea [Configure Mail Flow and Client Access](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Para Skype Empresarial Server, puede usar un certificado existente de Skype Empresarial Server como certificado de autenticación de servidor a servidor; por ejemplo, el certificado predeterminado también puede usarse como certificado OAuthTokenIssuer. Skype Empresarial Server le permite usar cualquier certificado de servidor web como certificado para la autenticación de servidor a servidor siempre que:
  
- El certificado incluya el nombre del dominio SIP en el campo Asunto.
    
- Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.
    
- El certificado tenga una longitud de al menos 2048 bits.
    
Para obtener más información sobre los certificados de autenticación de servidor a servidor para Skype Empresarial Server, consulte Asignar un certificado de autenticación de servidor [a servidor a Skype Empresarial Server.](../../manage/authentication/assign-a-server-to-server-certificate.md)
  
Una vez asignados los certificados, debe configurar el servicio de detección automática en Exchange Server. En Exchange Server, el servicio de detección automática configura perfiles de usuario y proporciona acceso a los servicios de Exchange cuando los usuarios inician sesión en el sistema. Los usuarios presentan el servicio de detección automática con su dirección de correo electrónico y contraseña; a su vez, los servicios proporcionan al usuario información como:
  
- Información de conexión para conectividad interna y externa a Exchange Server.
    
- La ubicación del servidor de buzones de correo del usuario.
    
- Direcciones URL de las características de Outlook como información de libre u ocupado, Mensajería unificada y la libreta de direcciones sin conexión.
    
- Configuración del servidor Outlook Anywhere.
    
El servicio de detección automática debe configurarse para poder integrar Skype Empresarial Server y Exchange Server. Puede comprobar si el servicio de detección automática se ha configurado ejecutando el siguiente comando desde el Shell de administración de Exchange Server y comprobando el valor de la propiedad AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si este valor está en blanco, deberá asignar un URI al servicio de detección automática. Normalmente, este URI tendrá un aspecto similar al siguiente: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Puede asignar el URI de detección automática ejecutando un comando similar al siguiente:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obtener más información sobre el servicio de detección automática, consulte [Servicio de detección automática.](https://go.microsoft.com/fwlink/p/?LinkId=268542)
  
Una vez configurado el servicio de detección automática, debe modificar las opciones de configuración de OAuth de Skype Empresarial Server; Esto garantiza que Skype Empresarial Server sepa dónde encontrar el servicio de detección automática. Para modificar las opciones de configuración de OAuth en Skype Empresarial Server, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server. Al ejecutar este comando, asegúrese de especificar el URI para el servicio de detección automática que se ejecuta en su Exchange Server y que usa **autodiscover.svc** para apuntar a la ubicación del servicio en lugar de **autodiscover.xml** (que apunta al archivo XML usado por el servicio):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> El parámetro Identity del comando anterior es opcional; esto se debe a que Skype Empresarial Server solo le permite tener una colección única y global de opciones de configuración de OAuth. Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto. 
  
Además de configurar el servicio de detección automática, también debe crear un registro DNS para el servicio que apunta a su Exchange Server. Por ejemplo, si el servicio de detección automática se encuentra en autodiscover.litwareinc.com deberá crear un registro DNS para autodiscover.litwareinc.com que se resuelva en el nombre de dominio completo de su Exchange Server (por ejemplo, atl-exchange-001.litwareinc.com).
  
Si está integrando Skype Empresarial Server con Exchange Online, los siguientes pasos son configurar la integración entre Skype Empresarial Server local y [Outlook Web App;](../../deploy/integrate-with-exchange-server/outlook-web-app.md)de lo contrario, consulte Integrar Skype Empresarial [Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Compatibilidad con características
<a name="feature_support"> </a>

>[!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de que las integraciones de Exchange que se enumeran a continuación que incluyen el servicio ya no sean compatibles.

En la tabla siguiente se detallan las características admitidas en varias combinaciones de exchange o local para Exchange y Skype Empresarial.
  
||**Exchange 2016/2013/2010 (local) + Skype Empresarial Server (local)**|**Exchange Online + Skype Empresarial Server (local)**|**Exchange 2010 (local) + Skype Empresarial Online**|**Exchange 2016/2013(local) + Skype Empresarial Online**|**Exchange Online + Skype Empresarial Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presencia en Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Responder a través de mensajería instantánea, llamada RTC, llamada de Skype o videollamada desde un correo electrónico de Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Presencia en Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Responder a través de mensajería instantánea, llamada RTC, llamada de Skype o videollamada desde un correo electrónico de OWA  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Mensajería instantánea y presencia en clientes móviles  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Unirse a reuniones en línea en clientes móviles  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Publicar el estado en función de la información de disponibilidad del calendario de Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Lista de contactos (a través del almacén de contactos unificado)  <br/> |Y (necesita Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Foto de contacto de alta resolución (requiere clientes de Lync 2013 o Skype Empresarial como mínimo. No compatible con LWA, aplicaciones móviles, Lync 2010, Lync para Mac y otros clientes más antiguos).  <br/> |Y (necesita Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |
|Delegación de reuniones  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de exchange del usuario  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Contenido de archivado (mensajería instantánea y reunión) en Exchange  <br/> |Y (necesita Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Buscar contenido archivado  <br/> |Y (necesita Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Correo de voz de mensajería unificada de Exchange  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Historial de conversaciones del lado servidor  <br/> |v  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |

> [!NOTE]
> Hay un servicio de correo de voz en la nube compatible con Skype Empresarial Online, Skype Empresarial Server 2019, Skype Empresarial Server 2015 y Lync Server 2013.
> 

## <a name="see-also"></a>Ver también
<a name="feature_support"> </a>

[Configurar la integración entre Skype Empresarial Server local y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar OAuth entre Skype Empresarial Online y Exchange local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar Skype Empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Cómo integrar Exchange Server 2013 con Lync Server 2013, Skype Empresarial Online o una implementación híbrida de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurar aplicaciones de asociados en Skype Empresarial Server y Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
