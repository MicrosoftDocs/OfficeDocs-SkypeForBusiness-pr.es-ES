---
title: Plan para la integración de Skype Empresarial y Exchange
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumen: Revise este tema para obtener información acerca de cómo integrar Skype para profesionales de 2015 servidor con Exchange Server 2016 o Exchange Server 2013.'
ms.openlocfilehash: 2534cd1d2b3bd02998beb2034c704259b6b14c49
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19505121"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan para la integración de Skype Empresarial y Exchange
 
**Resumen:** Revise este tema para obtener información acerca de cómo integrar Skype para profesionales de 2015 servidor con Exchange Server 2016 o Exchange Server 2013.
  
Antes de que se puede integrar Skype para Business Server 2015 y Exchange Server, debe asegurarse de que Exchange Server y Skype para Business Server 2015 están completamente instalados y arriba y que se está ejecutando. 
  
Para obtener información detallada sobre la instalación de Exchange Server, consulte la documentación de Exchange Server planeación e implementación para su versión de Exchange. 
  
Para obtener información detallada acerca de cómo instalar Skype para Business Server 2015, vea [Implementar Skype para Business Server 2015](../../deploy/deploy.md).
  
Después de que los servidores estén en funcionamiento, debe asignar certificados de autenticación de servidor a servidor a ambos Skype para Business Server 2015 y Exchange Server; Estos certificados permiten Skype para Business Server 2015 y Exchange Server para intercambiar información y para comunicarse entre sí. Al instalar Exchange Server, se crea un certificado autofirmado con el nombre de certificado de autenticación de servidor de Microsoft Exchange para usted. Este certificado, que se puede encontrar en el almacén de certificados del equipo local, se debe usar para la autenticación de servidor a servidor en el servidor de Exchange. Para obtener información detallada sobre la asignación de certificados en Exchange Server, vea [Configurar el flujo de correo y acceso de cliente](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Para Skype para Business Server 2015 puede usar un Skype existente para el certificado de servidor empresarial como su certificado de autenticación de servidor a servidor; Por ejemplo, también se puede utilizar su certificado predeterminado como el certificado OAuthTokenIssuer. Skype para Business Server 2015 le permite usar cualquier certificado de servidor Web como el certificado de autenticación de servidor a servidor, siempre que:
  
- El certificado incluya el nombre del dominio SIP en el campo Asunto.
    
- Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.
    
- El certificado tenga una longitud de al menos 2048 bits.
    
Para obtener información detallada sobre los certificados de autenticación de servidor a servidor para Skype para Business Server 2015, vea [asignar un certificado de autenticación de servidor a servidor a Skype para Business Server 2015](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Después de que se han asignado los certificados, a continuación, debe configurar el servicio de detección automática en Exchange Server. En Exchange Server, el servicio Detección automática configura los perfiles de usuario y proporciona acceso a los servicios de Exchange cuando los usuarios inician sesión en el sistema. Los usuarios presentan el servicio Detección automática con su dirección de correo electrónico y la contraseña; a su vez, los servicios de proporcionan al usuario con información como:
  
- Información de conexión para la conectividad interna y externa a Exchange Server.
    
- La ubicación del servidor de buzón de correo del usuario.
    
- Direcciones URL de las características de Outlook como información de libre u ocupado, Mensajería unificada y la libreta de direcciones sin conexión.
    
- Configuración del servidor Outlook en cualquier lugar.
    
El servicio Detección automática debe configurarse antes de que se puede integrar Skype para Business Server 2015 y Exchange Server. Puede comprobar si se ha configurado el servicio Detección automática ejecutando el siguiente comando desde el Shell de administración de Exchange Server y comprobar el valor de la propiedad AutoDiscoverServiceInternalUri:
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si este valor está en blanco, deberá asignar un URI al servicio de detección automática. Normalmente, este identificador URI debe ser similar a esta:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Puede asignar el URI de detección automática ejecutando un comando similar al siguiente:
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obtener información detallada sobre el servicio de detección automática, vea la [Descripción del servicio de detección automática](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Después de que se ha configurado el servicio Detección automática, a continuación, debe modificar el Skype para opciones de configuración de OAuth de servidor empresarial; Esto garantiza que ese Skype para Business Server sabe dónde encontrar el servicio Detección automática. Para modificar las opciones de configuración de OAuth en Skype para Business Server 2015, ejecute el siguiente comando desde dentro de la Skype para Shell de administración de servidor empresarial. Cuando se ejecuta este comando, asegúrese de que se especifique el URI para el servicio de detección automática que se ejecutan en el servidor de Exchange y que use **autodiscover.svc** para que apunte a la ubicación del servicio en lugar de **autodiscover.xml** (que apunta al archivo XML usada por el servicio):
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> El parámetro Identity en el comando anterior es opcional; eso es porque Skype para Business Server sólo le permite tener una colección único global de opciones de configuración de OAuth. Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple: 
  
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
  
> [!NOTE]
> Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto. 
  
Además de configurar el servicio Detección automática, también debe crear un registro DNS para el servicio que apunta al servidor de Exchange. Por ejemplo, si el servicio de detección automática se encuentra en autodiscover.litwareinc.com necesitará crear un registro DNS para autodiscover.litwareinc.com que se resuelve en el nombre de dominio completo de su servidor de Exchange (por ejemplo, ATL-exchange-001.litwareinc.com).
  
Si va a integrar Skype para Business Server con Exchange Online, los pasos siguientes se encuentran en [Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), en caso contrario, vea [integrar Skype para Business Server 2015 con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Compatibilidad con la característica
<a name="feature_support"> </a>

En la siguiente tabla se detalla las características admitidas en diversas combinaciones de online o local para Exchange y Skype para la empresa.
  
||**2013/Exchange 2016/2010 (local) + Skype para Business Server 2015 (local)**|**Exchange Online + Skype para Business Server 2015 (local)**|**Exchange 2010 (local) + Skype para profesionales en línea**|**Exchange 2016/2013(on premises) + Skype para profesionales en línea**|**Exchange Online + Skype para la empresa en línea**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presencia en Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Responder a través de MI, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Presencia en Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Responder a través de MI, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de OWA  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Mensajería instantánea y presencia en clientes móviles  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Unirse a reuniones en línea en clientes móviles  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Lista de contactos (por medio del almacén de contactos unificado)  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Alta resolución fotos de contactos (requiere Lync 2013 o Skype para clientes empresariales como mínimo. No se admiten para LWA, aplicaciones móviles, Lync 2010, Lync para Mac y otros los clientes más antiguos).  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|Delegación de reuniones  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de exchange del usuario  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Buscar contenido archivado  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Correo de voz de mensajería unificada de Exchange  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Historial de conversaciones en el servidor  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
   
## <a name="see-also"></a>Vea también
<a name="feature_support"> </a>

[Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar OAuth entre Skype para profesionales Online y Exchange local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar Skype para Business Server 2015 con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Cómo integrar Exchange Server 2013 con Lync Server 2013, Skype para profesionales en línea o una implementación híbrida de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configuración de las aplicaciones asociadas en Skype para Business Server 2015 y Microsoft Exchange Server](https://go.microsoft.com/fwlink/p/?LinkId=746495)