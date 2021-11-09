---
title: Configurar la integración entre las Skype Empresarial Server locales y Outlook Web App
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumen: integrar Skype Empresarial Server y Outlook Web App.'
ms.openlocfilehash: cebb8fed6b87dac6ec2c981730d303994c952741
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853684"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurar la integración entre las Skype Empresarial Server locales y Outlook Web App

**Resumen:** Integre Skype Empresarial Server y Outlook Web App.

Los clientes que usan implementaciones locales Skype Empresarial Server pueden configurar la interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange Online en un modo de implementación híbrida. Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App. Para habilitar esta integración, debe configurar el servidor perimetral en la implementación Skype Empresarial Server local completando las siguientes tareas:

- Configurar un espacio de direcciones SIP compartido

- Configurar un proveedor de hospedaje en el servidor perimetral

- Comprobar la replicación del almacén de administración central actualizado

## <a name="configure-a-shared-sip-address-space"></a>Configurar un espacio de direcciones SIP compartido

Para integrar las direcciones locales Skype Empresarial Server con Exchange Online, debe configurar un espacio de direcciones SIP compartido. El mismo espacio de direcciones de dominio SIP es compatible tanto con Skype Empresarial Server como con Exchange Online servicio.

Con el Shell de administración de Skype Empresarial Server, configure el servidor perimetral para la federación ejecutando el cmdlet **Set-CSAccessEdgeConfiguration,** con los parámetros que se muestran en el ejemplo siguiente:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- El parámetro **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Skype Empresarial Server y Exchange Online.

Para obtener más información acerca del uso Skype Empresarial Server Shell de administración, [vea Skype Empresarial Server Shell de administración](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar un proveedor de hospedaje en el servidor perimetral

Con el Shell de administración de Skype Empresarial Server, configure un proveedor de hospedaje en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider,** usando los parámetros del ejemplo siguiente:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Si usa Microsoft 365 o Office 365 operado por 21Vianet en China, reemplace el valor del parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn". Si usa Microsoft 365 o Office 365 GCC High, reemplace el valor del parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") por el FQDN de GCC High: "exap.um.office365.us".

- **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online"). Los valores que contienen espacios deben aparecer en comillas dobles.

- **Enabled** indica si la conexión de red entre su dominio y el proveedor de hospedaje está habilitada. Este parámetro debe estar configurado en True.

- **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido. Este parámetro debe estar configurado en True.

- **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Skype Empresarial Server. Este parámetro debe estar configurado en False.

- **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje. Para Exchange Online, el FQDN es exap.um.outlook.com.

- **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está contenido en la topología Skype Empresarial Server cliente. Este parámetro debe estar configurado en False.

- **VerificationLevel** Indica el nivel de comprobación permitido para los mensajes que se envían al proveedor hospedado y desde este. Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje. Si no se especifica este nivel, el mensaje se rechazará por no serverificable.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Comprobar la replicación del almacén de administración central actualizada

Los cambios realizados mediante el uso de los cmdlets de las secciones anteriores se aplican automáticamente al servidor perimetral y, por lo general, tardar menos de un minuto en replicarse. Puede validar el estado de replicación y, a continuación, confirmar que los cambios se aplicaron al servidor perimetral mediante los cmdlets siguientes.

Para comprobar las actualizaciones de replicación, en un servidor interno de la implementación Skype Empresarial Server, ejecute el siguiente cmdlet:

```powershell
Get-CsManagementStoreReplicationStatus
```
Compruebe si el valor UpToDate muestra TRUE para todas las réplicas.

Para confirmar que se aplicaron los cambios, en el servidor perimetral, ejecute el siguiente cmdlet:

```powershell
Get-CsHostingProvider -LocalStore
```
Compruebe doblemente si la información mostrada coincide con los cambios confirmados en los pasos anteriores.

## <a name="see-also"></a>Consulte también

[Proporcionar Skype Empresarial Server de voz de los usuarios en la mensajería unificada Exchange hospedada](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Integración Exchange mensajería unificada hospedada en Skype Empresarial Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)