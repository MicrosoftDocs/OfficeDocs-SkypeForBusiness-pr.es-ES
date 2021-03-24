---
title: Configurar la integración entre Skype Empresarial Server local y Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: integrar Skype Empresarial Server y Outlook Web App.'
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109696"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurar la integración entre Skype Empresarial Server local y Outlook Web App

**Resumen:** Integrar Skype Empresarial Server y Outlook Web App.

Los clientes que usan implementaciones locales de Skype Empresarial Server pueden configurar la interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange Online en un modo de implementación híbrida. Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App. Para habilitar esta integración, debe configurar el servidor perimetral en la implementación local de Skype Empresarial Server completando las siguientes tareas:

- Configurar un espacio de direcciones SIP compartido

- Configurar un proveedor de hospedaje en el servidor perimetral

- Comprobar la replicación del almacén de administración central actualizado

## <a name="configure-a-shared-sip-address-space"></a>Configurar un espacio de direcciones SIP compartido

Para integrar Skype Empresarial Server local con Exchange Online, debe configurar un espacio de direcciones SIP compartido. El mismo espacio de direcciones de dominio SIP es compatible con Skype Empresarial Server y el servicio Exchange Online.

Con el Shell de administración de Skype Empresarial Server, configure el servidor perimetral para la federación ejecutando el cmdlet **Set-CSAccessEdgeConfiguration,** con los parámetros que se muestran en el ejemplo siguiente:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- El parámetro **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Skype Empresarial Server y Exchange Online.

Para obtener más información acerca del uso del Shell de administración de Skype Empresarial Server, vea Shell de administración [de Skype Empresarial Server](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar un proveedor de hospedaje en el servidor perimetral

Con el Shell de administración de Skype Empresarial Server, configure un proveedor de hospedaje en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider,** usando los parámetros del ejemplo siguiente:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si usa Microsoft 365 u Office 365 operado por 21Vianet en China, reemplace el valor del parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn". Si usa Microsoft 365 u Office 365 GCC High, reemplace el valor del parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") por el FQDN de GCC High: "exap.um.office365.us".

- **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online"). Los valores que contienen espacios deben aparecer en comillas dobles.

- **Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Este parámetro debe estar configurado en True.

- **EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido. Este parámetro debe estar configurado en True.

- **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Skype Empresarial Server. Este parámetro debe estar configurado en False.

- **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje. Para Exchange Online, el FQDN es exap.um.outlook.com.

- **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está contenido en la topología de Skype Empresarial Server. Este parámetro debe estar configurado en False.

- **VerificationLevel** Indica el nivel de comprobación permitido para los mensajes que se envían al proveedor hospedado y desde este. Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje. Si no se especifica este nivel, el mensaje se rechazará por no serverificable.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Comprobar la replicación del almacén de administración central actualizada

Los cambios realizados mediante el uso de los cmdlets de las secciones anteriores se aplican automáticamente al servidor perimetral y, por lo general, tardar menos de un minuto en replicarse. Puede validar el estado de replicación y, a continuación, confirmar que los cambios se aplicaron al servidor perimetral mediante los cmdlets siguientes.

Para comprobar las actualizaciones de replicación, en un servidor interno de la implementación de Skype Empresarial Server, ejecute el siguiente cmdlet:

```powershell
Get-CsManagementStoreReplicationStatus
```
Compruebe si el valor UpToDate muestra TRUE para todas las réplicas.

Para confirmar que se aplicaron los cambios, en el servidor perimetral, ejecute el siguiente cmdlet:

```powershell
Get-CsHostingProvider -LocalStore
```
Compruebe doblemente si la información mostrada coincide con los cambios confirmados en los pasos anteriores.

## <a name="see-also"></a>Ver también

[Proporcionar correo de voz de usuarios de Skype Empresarial Server en mensajería unificada hospedada de Exchange](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Integración de mensajería unificada de Exchange hospedada en Skype Empresarial Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)