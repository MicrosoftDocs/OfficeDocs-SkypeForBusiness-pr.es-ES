---
title: Plan para la integración de Skype Empresarial y Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumen: Revise este tema para obtener información sobre cómo integrar Skype empresarial Server con Exchange Server 2016 o Exchange Server 2013.'
ms.openlocfilehash: f62ad2475fe17668e82b06b1b4a0f19b6a2ee7c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297403"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan para la integración de Skype Empresarial y Exchange
 
**Resumen:** Consulte este tema para obtener información sobre cómo integrar Skype empresarial Server con Exchange Server 2016 o Exchange Server 2013.
  
Para poder integrar Skype empresarial Server y Exchange Server, debe asegurarse de que tanto Exchange Server como Skype empresarial Server estén completamente instalados y en funcionamiento. 
  
Para obtener más información sobre cómo instalar Exchange Server, consulte la documentación de planeación e implementación de Exchange Server para su versión de Exchange. 
   
Después de que los servidores estén en funcionamiento, debe asignar certificados de autenticación de servidor a servidor para Skype empresarial Server y Exchange Server; Estos certificados permiten que Skype empresarial Server y Exchange Server interintercambien información y se comuniquen entre sí. Al instalar Exchange Server, se crea automáticamente un certificado autofirmado con el nombre de autenticación de Microsoft Exchange Server. Este certificado, que puede encontrarse en el almacén de certificados del equipo local, debe usarse para la autenticación de servidor a servidor en Exchange Server. Para obtener más información sobre cómo asignar certificados en Exchange Server, consulte [configurar el flujo de correo y el acceso de clientes](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
En Skype empresarial Server, puede usar un certificado existente de Skype empresarial Server como certificado de autenticación de servidor a servidor. por ejemplo, el certificado predeterminado también puede usarse como certificado OAuthTokenIssuer. Skype empresarial Server le permite usar cualquier certificado de servidor web como certificado para la autenticación de servidor a servidor, siempre y cuando:
  
- El certificado incluya el nombre del dominio SIP en el campo Asunto.
    
- Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.
    
- El certificado tenga una longitud de al menos 2048 bits.
    
Para obtener más información sobre los certificados de autenticación de servidor a servidor para Skype empresarial Server, consulte [asignar un certificado de autenticación de servidor a servidor a Skype empresarial Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Después de asignar los certificados, debe configurar el servicio Detección automática en Exchange Server. En Exchange Server, el servicio de detección automática configura perfiles de usuario y proporciona acceso a los servicios de Exchange cuando los usuarios inician sesión en el sistema. Los usuarios presentan el servicio de detección automática con su dirección de correo electrónico y contraseña; a su vez, los servicios proporcionan al usuario información como la siguiente:
  
- Información de conexión para conectividad interna y externa a Exchange Server.
    
- La ubicación del servidor de buzones del usuario.
    
- Direcciones URL de las características de Outlook como información de libre u ocupado, Mensajería unificada y la libreta de direcciones sin conexión.
    
- Configuración del servidor Outlook en cualquier lugar.
    
El servicio de detección automática debe estar configurado para poder integrar Skype empresarial Server y Exchange Server. Puede comprobar si el servicio de detección automática se ha configurado ejecutando el siguiente comando desde el shell de administración de Exchange Server y comprobando el valor de la propiedad AutoDiscoverServiceInternalUri:
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si este valor está en blanco, deberá asignar un URI al servicio de detección automática. Por lo general, este URI tendrá un aspecto similar al siguiente:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Puede asignar el URI de detección automática ejecutando un comando similar al siguiente:
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obtener más información sobre el servicio de detección automática, consulte [servicio Detección automática](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Después de configurar el servicio de detección automática, debe modificar la configuración de OAuth de Skype empresarial Server. Esto garantiza que Skype empresarial Server sepa dónde encontrar el servicio de detección automática. Para modificar la configuración de OAuth en Skype empresarial Server, ejecute el siguiente comando desde el shell de administración de Skype empresarial Server. Al ejecutar este comando, asegúrese de especificar el URI para el servicio de detección automática que se está ejecutando en el servidor de Exchange y de que usa **Autodiscover. SVC** para apuntar a la ubicación del servicio en lugar de Autodiscover **. XML** (que apunta al archivo XML utilizado por el servicio):
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> El parámetro Identity en el comando anterior es opcional; Esto se debe a que Skype empresarial Server solo le permite tener una única colección global de valores de configuración de OAuth. Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto. 
  
Además de configurar el servicio Detección automática, también debe crear un registro DNS para el servicio que apunta al servidor de Exchange. Por ejemplo, si el servicio de detección automática se encuentra en autodiscover.litwareinc.com necesitará crear un registro DNS para autodiscover.litwareinc.com que se resuelva en el nombre de dominio completo de su servidor de Exchange (por ejemplo, atl-exchange-001.litwareinc.com).
  
Si está integrando Skype empresarial Server con Exchange Online, los pasos siguientes están en [configurar la integración entre Skype empresarial Server local y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md); de lo contrario, consulte [integrar Skype empresarial Server con Exchange. Servidor](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Compatibilidad con la característica
<a name="feature_support"> </a>

En la tabla siguiente se detallan las características compatibles con diversas combinaciones de las locales o en línea para Exchange y Skype empresarial.
  
||**Exchange 2016/2013/2010 (local) + Skype empresarial Server (local)**|**Exchange Online + Skype empresarial Server (local)**|**Exchange 2010 (local) + Skype empresarial online**|**Exchange 2016/2013 (local) + Skype empresarial online**|**Exchange Online + Skype empresarial online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presencia en Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Responder a través de MI, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Presencia en Outlook Web App  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Responder a través de MI, llamadas RTC, llamadas de Skype o videollamadas desde un correo electrónico de OWA  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Programar y unirse a reuniones en línea a través de Outlook Web App  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Mensajería instantánea y presencia en clientes móviles  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Unirse a reuniones en línea en clientes móviles  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Publicar el estado según la información de disponibilidad del calendario de Outlook  <br/> |Y  <br/> |S  <br/> |S  <br/> |S  <br/> |Y  <br/> |
|Lista de contactos (por medio del almacén de contactos unificado)  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Foto de contacto de alta resolución (requiere Lync 2013 o clientes de Skype para empresas como mínimo. No se admiten para LWA, aplicaciones móviles, Lync 2010, Lync para Mac y otros los clientes más antiguos).  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |S  <br/> |S  <br/> |
|Delegación de reuniones  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Buscar contenido archivado  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Correo de voz de mensajería unificada de Exchange  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Historial de conversaciones en el servidor  <br/> |Y  <br/> |S  <br/> |N  <br/> |S  <br/> |S  <br/> |

> [!NOTE]
> Hay un servicio de buzón de voz en la nube que es compatible con Skype empresarial online, Skype empresarial Server 2019, Skype empresarial Server 2015 y Lync Server 2013.
> 

## <a name="see-also"></a>Vea también
<a name="feature_support"> </a>

[Configurar la integración entre Skype empresarial Server local y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar OAuth entre Skype Empresarial Online y Exchange local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar Skype empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Cómo integrar Exchange Server 2013 con Lync Server 2013, Skype empresarial online o una implementación híbrida de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurar aplicaciones de socio en Skype empresarial Server y Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
