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
description: 'Resumen: Revisar este tema para obtener información sobre cómo integrar Skype para Business Server 2015 con 2016 de Exchange Server o Exchange Server 2013.'
ms.openlocfilehash: 6d3d88183cfb99597829f01aae70b1c5cdd6f09a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan para la integración de Skype Empresarial y Exchange
 
**Resumen:** Revisar este tema para obtener información sobre cómo integrar Skype para Business Server 2015 con 2016 de Exchange Server o Exchange Server 2013.
  
Para poder integrar Skype para 2015 de Business Server y Exchange Server, debe asegurarse de que Exchange Server y Skype para Business Server 2015 están completamente instalados y funcionar. 
  
Para obtener más información acerca de cómo instalar Exchange Server, consulte la documentación de Exchange Server planificación e implementación para la versión de Exchange. 
  
Para obtener más información acerca de cómo instalar Skype para Business Server 2015, vea [Implementar Skype para Business Server 2015](../../deploy/deploy.md).
  
Después de que los servidores están en funcionamiento, debe asignar los certificados de autenticación de servidor a servidor a ambos Skype para 2015 de Business Server y Exchange Server; Estos certificados permiten Skype para 2015 de Business Server y Exchange Server para intercambiar información y comunicarse entre sí. Al instalar Exchange Server, se crea un certificado firmado automáticamente con el nombre de certificado de autenticación de Microsoft Exchange Server para usted. Este certificado, que puede encontrarse en el almacén de certificados del equipo local, se debe utilizar para la autenticación de servidor a servidor en Exchange Server. Para obtener más información sobre la asignación de certificados en Exchange Server, consulte [Configurar el flujo de correo y de acceso de cliente](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Para Skype para Business Server 2015 puede utilizar un Skype existente para el certificado de servidor de Business como el certificado de autenticación de servidor a servidor; Por ejemplo, el certificado predeterminado también puede utilizarse como el certificado OAuthTokenIssuer. Skype para el año 2015 de Business Server le permite utilizar cualquier certificado de servidor Web como el certificado de autenticación de servidor a servidor, siempre que:
  
- El certificado incluya el nombre del dominio SIP en el campo Asunto.
    
- Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.
    
- El certificado tenga una longitud de al menos 2048 bits.
    
Para obtener más información acerca de los certificados de autenticación de servidor a servidor de Skype para Business Server 2015, vea [asignar un certificado de autenticación de servidor a servidor a Skype para Business Server 2015](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Una vez se han asignado los certificados, a continuación, debe configurar el servicio de detección automática en Exchange Server. En Exchange Server, el servicio Detección automática configura perfiles de usuario y proporciona acceso a los servicios de Exchange cuando los usuarios inician sesión en el sistema. Los usuarios presentan el servicio Detección automática con su dirección de correo electrónico y contraseña; a su vez, los servicios proporcionan al usuario información como:
  
- Información de conexión para la conectividad interna y externa a Exchange Server.
    
- La ubicación del servidor de buzones del usuario.
    
- Direcciones URL de las características de Outlook como información de libre u ocupado, Mensajería unificada y la libreta de direcciones sin conexión.
    
- Configuración del servidor Outlook en cualquier lugar.
    
El servicio Detección automática debe configurarse para poder integrar Skype para 2015 de Business Server y Exchange Server. Puede comprobar o no se ha configurado el servicio Detección automática ejecutando el siguiente comando desde el Shell de administración de Exchange Server y comprobando el valor de la propiedad AutoDiscoverServiceInternalUri:
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Si este valor está en blanco, deberá asignar un URI al servicio de detección automática. Normalmente este URI tendrá un aspecto similar a este:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Puede asignar el URI de detección automática ejecutando un comando similar al siguiente:
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obtener más información acerca del servicio de detección automática, consulte la [Descripción del servicio de detección automática](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Una vez que se ha configurado el servicio Detección automática, a continuación, debe modificar el Skype para la configuración de Business Server OAuth; Esto garantiza que ese Skype para Business Server sabe dónde encontrar el servicio Detección automática. Para modificar las opciones de configuración OAuth en Skype para Business Server 2015, ejecute el siguiente comando desde dentro el Skype para el Shell de administración de servidor de empresa. Al ejecutar este comando, asegúrese de que especifica el identificador URI para el servicio de detección automática que se ejecuta en el Exchange Server y utilizar **autodiscover.svc** para que apunte a la ubicación del servicio en lugar de **autodiscover.xml** (que señala al archivo XML utilizada por el servicio):
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> El parámetro Identity en el comando anterior es opcional; eso es porque Skype para Business Server sólo permite tener una colección global única de configuración OAuth. Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple: 
  
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
  
> [!NOTE]
> Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto. 
  
Además de configurar el servicio de detección automática, también debe crear un registro DNS para el servicio que señala a su Exchange Server. Por ejemplo, si el servicio de detección automática se encuentra en autodiscover.litwareinc.com debe crear un registro DNS para autodiscover.litwareinc.com que se resuelve en el nombre de dominio completo de su Exchange Server (por ejemplo, ATL-exchange-001.litwareinc.com).
  
Si está integrando Skype para Business Server con Exchange Online, los pasos siguientes en [Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), en caso contrario, consulte [integrar Skype para Business Server 2015 con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Compatibilidad con la característica
<a name="feature_support"> </a>

La siguiente tabla detalla las características admitidas en diversas combinaciones de en línea y en los locales de intercambio y Skype para el negocio.
  
||**2013/2016 de Exchange/2010 (en locales) + Skype para Business Server 2015 (en instalaciones)**|**Exchange Online + Skype para Business Server 2015 (en instalaciones)**|**Exchange 2010 (en locales) + Skype para los negocios en línea**|**Intercambio de 2016/2013(on premises) + Skype para los negocios en línea**|**Exchange Online + Skype para el negocio en línea**|
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
|Foto de contacto alta resolución (requiere 2013 de Lync o Skype para clientes de empresa como mínimo. No se admiten para LWA, aplicaciones móviles, Lync 2010, Lync para Mac y otros los clientes más antiguos).  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|Delegación de reuniones  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Registros de llamadas y el historial de conversaciones perdidas se escriben en el buzón de exchange del usuario  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Contenido de archivado (mensajería instantánea y reuniones) en Exchange  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Buscar contenido archivado  <br/> |Y (requiere Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Correo de voz de mensajería unificada de Exchange  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Historial de conversaciones en el servidor  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
   
## <a name="see-also"></a>Vea también
<a name="feature_support"> </a>

#### 

[Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar OAuth entre Skype para los negocios en línea y Exchange en instalaciones](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)
#### 

[Integrar Skype para Business Server 2015 con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Cómo integrar Exchange Server 2013 con Lync Server 2013, Skype para los negocios en línea o una implementación de Lync Server 2013 híbrido](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurar aplicaciones de socios en Skype para 2015 de Business Server y Microsoft Exchange Server](https://go.microsoft.com/fwlink/p/?LinkId=746495)

