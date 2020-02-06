---
title: Configurar la integración entre Skype empresarial Server local y Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumen: Integre Skype empresarial Server y Outlook Web App.'
ms.openlocfilehash: 2496cc7c2f357c4e1afa73dea18f304c6a7f9607
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797041"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurar la integración entre Skype empresarial Server local y Outlook Web App

**Resumen:** Integre Skype empresarial Server y Outlook Web App.

Los clientes que usan implementaciones locales de Skype empresarial Server pueden configurar la interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange online en un modo de implementación híbrida. Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App. Para habilitar esta integración, debe configurar el servidor perimetral en su implementación local de Skype empresarial Server completando las siguientes tareas:

- Configurar un espacio de direcciones SIP compartido

- Configurar un proveedor de hospedaje en el servidor perimetral

- Comprobar la replicación del almacén de administración central actualizado

## <a name="configure-a-shared-sip-address-space"></a>Configurar un espacio de direcciones SIP compartido

Para integrar Skype empresarial Server local con Exchange Online, debe configurar un espacio de direcciones SIP compartido. El mismo espacio de direcciones de dominio SIP es compatible con Skype empresarial Server y el servicio Exchange Online.

Con el shell de administración de Skype empresarial Server, configure el servidor perimetral para la Federación ejecutando el cmdlet **set-CSAccessEdgeConfiguration** , con los parámetros que se muestran en el siguiente ejemplo:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- El parámetro **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Skype empresarial Server y Exchange Online.

Para obtener detalles sobre el uso del shell de administración de Skype empresarial Server, consulte [Shell de administración de Skype empresarial Server](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar un proveedor de hospedaje en el servidor perimetral

Con el shell de administración de Skype empresarial Server, configure un proveedor de hospedaje en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** , con los parámetros del siguiente ejemplo:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si utiliza Office 365 operado por 21Vianet en China, reemplace el valor del parámetro ProxyFqdn de este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn". Si usa Office 365 GCC High, reemplace el valor del parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") por el FQDN de GCC High: "exap.um.office365.us".

- **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online"). Los valores que contienen espacios deben aparecer en comillas dobles.

- **Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Este parámetro debe estar configurado en True.

- **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido. Este parámetro debe estar configurado en True.

- **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Skype empresarial Server. Este parámetro debe estar configurado en False.

- **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje. Para Exchange Online, el FQDN es exap.um.outlook.com.

- **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está contenido dentro de la topología de su servidor de Skype empresarial. Este parámetro debe estar configurado en False.

- **VerificationLevel** Indica el nivel de comprobación permitido para los mensajes que se envían al proveedor hospedado y desde él. Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje. Si no se especifica este nivel, el mensaje se rechazará como no verificable.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Comprobar la replicación del almacén de administración central actualizada

Los cambios que realice con los cmdlets de las secciones anteriores se aplican automáticamente al servidor perimetral y generalmente tardan menos de un minuto en replicarse. Puede validar el estado de la replicación y, a continuación, confirmar que los cambios se aplicaron a su servidor perimetral mediante los siguientes cmdlets.

Para comprobar las actualizaciones de replicación, en un servidor interno de la implementación de Skype empresarial Server, ejecute el siguiente cmdlet:

```powershell
Get-CsManagementStoreReplicationStatus
```
Compruebe si el valor UpToDate se muestra como verdadero para todas las réplicas.

Para confirmar que se aplicaron los cambios, en el servidor perimetral, ejecute el siguiente cmdlet:

```powershell
Get-CsHostingProvider -LocalStore
```
Compruebe si la información mostrada coincide con los cambios comprometidos en los pasos anteriores.

## <a name="see-also"></a>Vea también

[Proporcionar correo de voz a los usuarios de Skype empresarial Server en mensajería unificada de Exchange hospedada](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Integración de mensajería unificada de Exchange hospedada en Skype empresarial Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
