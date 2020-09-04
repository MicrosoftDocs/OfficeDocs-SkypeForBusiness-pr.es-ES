---
title: Plan para la integración de Skype Empresarial y Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumen: Revise este tema para obtener información sobre cómo integrar Skype empresarial Server con Exchange Server 2016 o Exchange Server 2013.'
ms.openlocfilehash: d5d2a50e3b3b376bc27a407313944a31dc1352f6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359266"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan para la integración de Skype Empresarial y Exchange
 
**Resumen:** Consulte este tema para obtener información sobre cómo integrar Skype empresarial Server con Exchange Server 2016 o Exchange Server 2013.
  
Antes de integrar Skype empresarial Server y Exchange Server, debe asegurarse de que Exchange Server y Skype empresarial Server están completamente instalados y en funcionamiento. 
  
Para obtener más información acerca de la instalación de Exchange Server, consulte la documentación de planeación e implementación de Exchange Server para su versión de Exchange. 
   
Una vez que los servidores estén en funcionamiento, debe asignar certificados de autenticación de servidor a servidor a Skype empresarial Server y Exchange Server; Estos certificados permiten que Skype empresarial Server y Exchange Server puedan intercambiar información y comunicarse entre sí. Cuando instale Exchange Server, se creará automáticamente un certificado autofirmado con el nombre certificado de autenticación de Microsoft Exchange Server. Este certificado, que puede encontrarse en el almacén de certificados del equipo local, debe usarse para la autenticación de servidor a servidor en Exchange Server. Para obtener información detallada acerca de la asignación de certificados en Exchange Server, consulte [configurar el flujo de correo y el acceso de cliente](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Para Skype empresarial Server, puede usar un certificado de Skype empresarial Server existente como certificado de autenticación de servidor a servidor; por ejemplo, el certificado predeterminado también puede usarse como certificado OAuthTokenIssuer. Skype empresarial Server permite usar cualquier certificado de servidor web como certificado para la autenticación de servidor a servidor, siempre que:
  
- El certificado incluya el nombre del dominio SIP en el campo Asunto.
    
- Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.
    
- El certificado tenga una longitud de al menos 2048 bits.
    
Para obtener más información sobre los certificados de autenticación de servidor a servidor para Skype empresarial Server, consulte [asignar un certificado de autenticación de servidor a servidor a Skype empresarial Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Después de que se hayan asignado los certificados, debe configurar el servicio Detección automática en Exchange Server. En Exchange Server, el servicio de detección automática configura los perfiles de usuario y proporciona acceso a los servicios de Exchange cuando los usuarios inician sesión en el sistema. Los usuarios presentan el servicio de detección automática con su dirección de correo electrónico y contraseña; a su vez, los servicios proporcionan al usuario información como la siguiente:
  
- Información de conexión para la conectividad interna y externa a Exchange Server.
    
- La ubicación del servidor de buzones de correo del usuario.
    
- Direcciones URL de las características de Outlook como información de libre u ocupado, Mensajería unificada y la libreta de direcciones sin conexión.
    
- Configuración del servidor Outlook Anywhere.
    
El servicio Detección automática debe estar configurado para poder integrar Skype empresarial Server y Exchange Server. Puede comprobar si el servicio de detección automática se ha configurado ejecutando el siguiente comando desde el shell de administración de Exchange Server y comprobando el valor de la propiedad AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si este valor está en blanco, deberá asignar un URI al servicio de detección automática. Normalmente, este URI tendrá un aspecto similar al siguiente: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Puede asignar el URI de detección automática ejecutando un comando similar al siguiente:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obtener más información sobre el servicio Detección automática, consulte [servicio Detección automática](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Una vez configurado el servicio de detección automática, debe modificar las opciones de configuración de OAuth de Skype empresarial Server; Esto garantiza que Skype empresarial Server sepa dónde encontrar el servicio Detección automática. Para modificar las opciones de configuración de OAuth en Skype empresarial Server, ejecute el siguiente comando desde dentro del shell de administración de Skype empresarial Server. Al ejecutar este comando, asegúrese de especificar el URI para el servicio de detección automática que se está ejecutando en el servidor de Exchange y de que usa **Autodiscover. SVC** para apuntar a la ubicación del servicio en lugar de **autodiscover.xml** (que apunta al archivo XML usado por el servicio):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> El parámetro Identity en el comando anterior es opcional; Esto se debe a que Skype empresarial Server solo permite tener una única colección global de opciones de configuración de OAuth. Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto. 
  
Además de configurar el servicio Detección automática, también debe crear un registro DNS para el servicio que apunta al servidor Exchange. Por ejemplo, si el servicio de detección automática está ubicado en autodiscover.litwareinc.com, deberá crear un registro DNS para autodiscover.litwareinc.com que se resuelva en el nombre de dominio completo del servidor Exchange (por ejemplo, atl-exchange-001.litwareinc.com).
  
Si va a integrar Skype empresarial Server con Exchange Online, los pasos siguientes se encuentran en [Configure Integration between on-premises Skype for Business Server and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), en caso contrario, consulte [integrar Skype empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Compatibilidad con características
<a name="feature_support"> </a>

>[!Important]
> Skype empresarial online se retirará el 31 de julio de 2021 después de que las integraciones de Exchange que se enumeran a continuación que incluyan el servicio ya no sean compatibles.

En la tabla siguiente se detallan las características admitidas en varias combinaciones de en línea o locales para Exchange y Skype empresarial.
  
||**Exchange 2016/2013/2010 (local) + Skype empresarial Server (local)**|**Exchange Online + Skype empresarial Server (local)**|**Exchange 2010 (local) + Skype empresarial online**|**Exchange 2016/2013 (local) + Skype empresarial online**|**Exchange Online + Skype empresarial online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presencia en Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Responder a través de mensajería instantánea, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Presencia en Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Responder a través de mensajería instantánea, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de OWA  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook Web App  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Mensajería instantánea y presencia en clientes móviles  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Unirse a reuniones en línea en clientes móviles  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Lista de contactos (a través del almacén de contactos unificado)  <br/> |Y (necesita Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Foto de contacto de alta resolución (requiere clientes de Lync 2013 o Skype empresarial como mínimo. No se admite para LWA, aplicaciones móviles, Lync 2010, Lync para Mac y otros clientes anteriores).  <br/> |Y (necesita Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |
|Delegación de reuniones  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |v  <br/> |
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Y (necesita Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Buscar contenido archivado  <br/> |Y (necesita Exchange 2016/2013)  <br/> |v  <br/> |N  <br/> |N  <br/> |v  <br/> |
|Correo de voz de mensajería unificada de Exchange  <br/> |v  <br/> |v  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Historial de conversaciones del servidor  <br/> |v  <br/> |v  <br/> |N  <br/> |v  <br/> |v  <br/> |

> [!NOTE]
> Hay un servicio de correo de voz en la nube que es compatible con Skype empresarial online, Skype empresarial Server 2019, Skype empresarial Server 2015 y Lync Server 2013.
> 

## <a name="see-also"></a>Recursos adicionales
<a name="feature_support"> </a>

[Configurar la integración entre Skype empresarial Server local y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar OAuth entre Skype empresarial online y Exchange local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar Skype empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Cómo integrar Exchange Server 2013 con una implementación híbrida de Lync Server 2013, Skype empresarial online o Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurar aplicaciones de socio en Skype empresarial Server y Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
