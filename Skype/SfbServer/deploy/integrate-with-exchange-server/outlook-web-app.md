---
title: Configurar la integración entre local Skype para Business Server y Outlook Web App
ms.reviewer: ''
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
ms.openlocfilehash: 3bd5131fcdba3d3253021c711910b18f46e93ce4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884873"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurar la integración entre local Skype para Business Server y Outlook Web App

**Resumen:** Integrar Skype para Business Server y Outlook Web App.

Los clientes que usen local Skype para las implementaciones de Business Server pueden configurar interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange Online en un modo de implementación híbrida. Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App. Para habilitar esta integración, debe configurar el servidor perimetral en su Skype local para la implementación de Business Server al completar las tareas siguientes:

- Configurar un espacio de direcciones SIP compartido

- Configurar un proveedor de hospedaje en el servidor perimetral

- Comprobar la replicación del almacén de Administración Central actualizado

## <a name="configure-a-shared-sip-address-space"></a>Configurar un espacio de direcciones SIP compartido

Para integrar local Skype para Business Server con Exchange Online, debe configurar un espacio de direcciones SIP compartido. El mismo espacio de dirección de dominio SIP es compatible con Skype para Business Server y el servicio Exchange Online.

Mediante el Skype para Shell de administración de servidor empresarial, configure el servidor perimetral para la federación ejecutando el cmdlet **Set-CSAccessEdgeConfiguration** , mediante los parámetros mostrados en el siguiente ejemplo:

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- El parámetro **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Skype para Business Server y Exchange Online.

Para obtener información detallada sobre el uso de la Skype para Shell de administración de servidor empresarial, vea [Skype para Shell de administración de servidor empresarial](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar un proveedor de hospedaje en el servidor perimetral

Mediante el Skype para Shell de administración de negocio Server, configure un proveedor de hospedaje en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** , mediante los parámetros en el ejemplo siguiente:

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si utiliza Office 365 operado por 21Vianet en China, reemplace el valor del parámetro ProxyFqdn de este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn". Si usa Office 365 GCC alta, reemplace el valor para el parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") con el FQDN de GCC alta: "exap.um.office365.us".

- **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online"). Los valores que contienen espacios deben aparecer en comillas dobles.

- **Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Este parámetro debe estar configurado en True.

- **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido. Este parámetro debe estar configurado en True.

- **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Skype para Business Server. Este parámetro debe estar configurado en False.

- **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje. Para Exchange Online, el FQDN es exap.um.outlook.com.

- **IsLocal** indica si el servidor proxy utilizado por el proveedor de hospedaje está dentro de su Skype de topología de servidores de negocio. Este parámetro debe estar configurado en False.

- **VerificationLevel** Indica el nivel de comprobación permitido para los mensajes que se envían a y desde el proveedor hospedado. Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje. Si no se especifica este nivel, el mensaje se rechazará como no se puede comprobar.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Comprobar la replicación del almacén de administración central actualizada

Los cambios realizados mediante el uso de los cmdlets en las secciones anteriores se aplican automáticamente al servidor perimetral y suele tardar menos de un minuto para replicar. Puede validar el estado de la replicación y, a continuación, confirme que se han aplicado los cambios en el servidor perimetral mediante el uso de los cmdlets siguientes.

Para comprobar la replicación de las actualizaciones, en un servidor interno de su Skype para la implementación de Business Server, ejecute el siguiente cmdlet:

```
Get-CsManagementStoreReplicationStatus
```
Compruebe si el valor de actualizados se está mostrando en TRUE para todas las réplicas.

Para confirmar que se han aplicado los cambios, en el servidor perimetral, ejecute el siguiente cmdlet:

```
Get-CsHostingProvider -LocalStore
```
Comprobar si la información que se muestra coincide con los cambios confirmados en los pasos anteriores.

## <a name="see-also"></a>Consulte también

[Especificación de Skype para Business Server en MU de Exchange hospedado del correo de voz de los usuarios](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Hospedado integración mensajería unificada de Exchange en Skype para Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
