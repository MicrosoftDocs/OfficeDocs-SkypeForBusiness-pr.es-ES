---
title: Plan para la integración de Skype Empresarial y Exchange
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumen: revise este tema para obtener información sobre cómo integrar Skype Empresarial Server con Exchange Server 2016 o Exchange Server 2013.'
---

# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan para la integración de Skype Empresarial y Exchange
 
**Resumen:** Revise este tema para obtener información sobre cómo integrar Skype Empresarial Server con Exchange Server 2016 o Exchange Server 2013.
  
Antes de poder integrar Skype Empresarial Server y Exchange Server, debe asegurarse de que Exchange Server y Skype Empresarial Server estén completamente instalados y en funcionamiento. 
  
Para obtener más información acerca de Exchange Server, consulte la documentación Exchange Server planeación e implementación de la versión de Exchange. 
   
Después de que los servidores estén en funcionamiento, debe asignar certificados de autenticación de servidor a servidor a Skype Empresarial Server y Exchange Server; estos certificados permiten Skype Empresarial Server y Exchange Server  intercambiar información y comunicarse entre sí. Al instalar Exchange Server, se crea un certificado autofirmado con el nombre Microsoft Exchange Server certificado de autenticación automáticamente. Este certificado, que se puede encontrar en el almacén de certificados de equipo local, debe usarse para la autenticación de servidor a servidor en Exchange Server. Para obtener más información sobre cómo asignar certificados en Exchange Server, vea [Configure Mail Flow and Client Access](/exchange/configure-mail-flow-and-client-access-exchange-2013-help).
  
Por Skype Empresarial Server puede usar un certificado de Skype Empresarial Server existente como certificado de autenticación de servidor a servidor; por ejemplo, el certificado predeterminado también se puede usar como certificado OAuthTokenIssuer. Skype Empresarial Server permite usar cualquier certificado de servidor web como certificado para la autenticación de servidor a servidor siempre que:
  
- El certificado incluya el nombre del dominio SIP en el campo Asunto.
    
- Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.
    
- El certificado tenga una longitud de al menos 2048 bits.
    
Para obtener más información acerca de los certificados de autenticación de servidor a servidor para Skype Empresarial Server, vea Asignar un certificado de autenticación de servidor [a servidor a Skype Empresarial Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Después de asignar los certificados, debe configurar el servicio de detección automática en Exchange Server. En Exchange Server, el servicio de detección automática configura perfiles de usuario y proporciona acceso a Exchange servicios cuando los usuarios inician sesión en el sistema. Los usuarios presentan el servicio de detección automática con su dirección de correo electrónico y contraseña; a su vez, los servicios proporcionan al usuario información como:
  
- Información de conexión para la conectividad interna y externa a Exchange Server.
    
- Ubicación del servidor de buzones del usuario.
    
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

Para obtener más información sobre el servicio de detección automática, consulte [Servicio de detección automática](/Exchange/architecture/client-access/autodiscover).
  
Después de configurar el servicio de detección automática, debe modificar las opciones de configuración de OAuth de Skype Empresarial Server; esto garantiza que Skype Empresarial Server sabe dónde encontrar el servicio de detección automática. Para modificar las opciones de configuración de OAuth en Skype Empresarial Server, ejecute el siguiente comando desde el Shell Skype Empresarial Server administración. Al ejecutar este comando, asegúrese de especificar el URI para el servicio de detección automática que se ejecuta en su Exchange Server y de usar **autodiscover.svc** para apuntar a la ubicación del servicio en lugar de **autodiscover.xml** (que apunta al archivo XML usado por el servicio):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> El parámetro Identity del comando anterior es opcional; esto se debe a Skype Empresarial Server solo permite tener una única colección global de opciones de configuración de OAuth. Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto. 
  
Además de configurar el servicio de detección automática, también debe crear un registro DNS para el servicio que apunta a su Exchange Server. Por ejemplo, si el servicio de detección automática se encuentra en autodiscover.litwareinc.com deberá crear un registro DNS para autodiscover.litwareinc.com que se resuelva en el nombre de dominio completo de su Exchange Server (por ejemplo, atl-exchange-001.litwareinc.com).
  
Si va a integrar Skype Empresarial Server con Exchange Online, los siguientes pasos se encuentran en Configurar la integración entre Skype Empresarial Server locales y [Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), de lo contrario, vea [Integrar Skype Empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Compatibilidad con características
<a name="feature_support"> </a>

>[!Important]
> Skype Empresarial Online se retiró el 31 de julio de 2021. Las Exchange que se enumeran a continuación que incluyen el servicio ya no son compatibles.

En la tabla siguiente se detallan las características admitidas en varias combinaciones de elementos locales o en línea para Exchange y Skype Empresarial.
  
|&nbsp;|Exchange 2016/2013/2010 (local) + Skype Empresarial Server (local)|Exchange Online + Skype Empresarial Server (local)**|**Exchange 2010 (local) + Skype Empresarial Online|Exchange 2016/2013(local) + Skype Empresarial Online**|**Exchange Online + Skype Empresarial Online|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presencia en Outlook   |v   |v   |v   |v   |v   |
|Responder a través de mensajería instantánea, llamada RTC, Skype o videollamada desde un correo Outlook correo electrónico   |v   |v   |v   |v   |v   |
|Programar y unirse a reuniones en línea a través de Outlook   |v   |v   |v   |v   |v   |
|Presencia en Outlook Web App   |v   |v   |N   |N   |v   |
|Responder a través de mensajería instantánea, llamada RTC, Skype o videollamada desde un correo electrónico de OWA   |v   |v   |N   |N   |v   |
|Programar y unirse a reuniones en línea a través de Outlook Web App   |v   |v   |N   |N   |v   |
|Mensajería instantánea/presencia en clientes móviles   |v   |v   |v   |v   |v   |
|Unirse a reuniones en línea en clientes móviles   |v   |v   |v   |v   |v   |
|Estado de publicación basado en Outlook de disponibilidad del calendario   |v   |v   |v   |v   |v   |
|Lista de contactos (a través del Almacén de contactos unificado)   |Y (necesita Exchange 2016/2013)   |v   |N   |N   |v   |
|Foto de contacto de alta resolución (requiere Lync 2013 o Skype Empresarial clientes como mínimo. No compatible con LWA, aplicaciones móviles, Lync 2010, Lync para Mac y otros clientes antiguos).   |Y (necesita Exchange 2016/2013)   |v   |N   |v   |v   |
|Delegación de reuniones   |v   |v   |v   |v   |v   |
|El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de exchange del usuario   |v   |v   |v   |v   |v   |
|Contenido de archivado (MI y reunión) en Exchange   |Y (necesita Exchange 2016/2013)   |v   |N   |N   |v   |
|Buscar contenido archivado   |Y (necesita Exchange 2016/2013)   |v   |N   |N   |v   |
|Exchange de voz de mensajería unificada   |v   |v   |N   |N   |N   |
|Historial de conversaciones del lado servidor   |v   |v   |N   |v   |v   |

> [!NOTE]
> Hay un servicio Correo de voz en la nube compatible con Skype Empresarial Online, Skype Empresarial Server 2019, Skype Empresarial Server 2015 y Lync Server 2013.
> 

## <a name="see-also"></a>Vea también
<a name="feature_support"> </a>

[Configurar la integración entre las Skype Empresarial Server locales y Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar OAuth entre Skype Empresarial Online y Exchange local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar Skype Empresarial Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Cómo integrar Exchange Server 2013 con Lync Server 2013, Skype Empresarial Online o una implementación híbrida de Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Configurar aplicaciones asociadas en Skype Empresarial Server y Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)