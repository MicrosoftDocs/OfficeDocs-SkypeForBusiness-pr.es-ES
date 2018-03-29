---
title: Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumen: Integrar Skype para Business Server y Outlook Web App.'
ms.openlocfilehash: 4ac4d6a71f8006e813d09631f8ccf28742940ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-2015-and-outlook-web-app"></a>Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App
 
**Resumen:** Integrar Skype para Business Server y Outlook Web App.
  
Los clientes que utilizan Skype local para implementaciones de servidor de negocios 2015 pueden configurar interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange Online en un modo de implementación híbrida. Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App. Para habilitar esta integración, debe configurar el servidor perimetral en su Skype local para la implementación de Business Server realizando las siguientes tareas: 
  
- Configurar un espacio de direcciones SIP compartido
    
- Configurar un proveedor de hospedaje en el servidor perimetral
    
- Comprobar la replicación del almacén de Administración Central actualizado
    
## <a name="configure-a-shared-sip-address-space"></a>Configurar un espacio de direcciones SIP compartido

Para integrar Skype locales para el año 2015 de servidor empresariales con Exchange Online, debe configurar un espacio de direcciones compartido de SIP. El mismo espacio de dirección de dominio SIP es compatible con Skype para Business Server y el servicio en línea de Exchange.
  
Mediante el Skype para negocios de Shell de administración de servidor, configure el servidor perimetral para la federación ejecutando el cmdlet **Set-CSAccessEdgeConfiguration** , con los parámetros que se muestra en el ejemplo siguiente:
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** parámetro especifica si se permiten que los usuarios internos comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos puedan comunicarse con usuarios en un escenario de espacio de direcciones compartido SIP con Skype para Business Server y Exchange Online.
    
Para obtener más información acerca de cómo utilizar el Skype para negocios de Shell de administración de servidor, vea [Skype para el Shell de administración de negocio servidor 2015](../../manage/management-shell.md).
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar un proveedor de hospedaje en el servidor perimetral

Utilizando el Skype para negocios de Shell de administración de servidor, configurar un proveedor de hospedaje en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** , utilizando los parámetros en el ejemplo siguiente:
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si utiliza Office 365 operado por 21Vianet en China, reemplace el valor del parámetro **ProxyFqdn** de este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn".
  
- **Identidad** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online"). Los valores que contienen espacios deben aparecer en comillas dobles.
    
- **Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Este parámetro debe estar configurado en True.
    
- **EnabledSharedAddressSpace** indica si se utilizará el proveedor de hospedaje en un escenario de espacio de direcciones compartido de SIP. Este parámetro debe estar configurado en True.
    
- **HostsOCSUsers** indica si se utiliza el proveedor de hospedaje para hospedar Office Communications Server o Skype para Business Server. Este parámetro debe estar configurado en False.
    
- **ProxyFQDN** especifica el nombre de dominio completo (FQDN) del servidor proxy utilizado por el proveedor de hospedaje. Para Exchange Online, el FQDN es exap.um.outlook.com.
    
- **IsLocal** indica si el servidor proxy utilizado por el proveedor de hospedaje está dentro de su Skype para la topología de servidores de empresa. Este parámetro debe estar configurado en False.
    
- **VerificationLevel** Indica el nivel de comprobación permitido para los mensajes que se envían a y desde el proveedor alojado. Especifique **UseSourceVerification**, que se basa en el nivel de comprobación que se incluye en los mensajes enviados desde el proveedor de hospedaje. Si no se especifica este nivel, se rechazará el mensaje como no comprobable.
    
## <a name="verify-replication-of-the-updated-central-management-store"></a>Comprobar la replicación del almacén de administración central actualizada

Los cambios realizados mediante los cmdlets en las secciones anteriores se aplican automáticamente en el servidor perimetral y normalmente tardan menos de un minuto para replicar. Puede validar el estado de la replicación y, a continuación, confirme que los cambios se aplicaron a su servidor perimetral utilizando los siguientes cmdlets.
  
Para comprobar las actualizaciones de replicación en un servidor interno en su Skype para la implementación de Business Server, ejecute el siguiente cmdlet:
  
```
Get-CsManagementStoreReplicationStatus
```

Para confirmar que se han aplicado los cambios en el servidor perimetral, ejecute el siguiente cmdlet:
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a>Vea también

#### 

[Proporcionar Skype para Business Server 2015 correo en MU de Exchange alojado de voz de los usuarios](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[Alojado Exchange integración de mensajería unificada en Skype para Business Server 2015](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)

