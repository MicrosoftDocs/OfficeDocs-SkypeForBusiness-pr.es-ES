---
title: 'Panel de control: información general'
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: En este artículo se proporciona información general sobre el nuevo Panel de control.
ms.openlocfilehash: 355a8b93e428b860a775ad01cf31df726c644654
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887308"
---
# <a name="control-panel"></a>Panel de control

El Panel de control actual es una nueva versión del Panel de control heredado, con el que existe en tándem. El nuevo Panel de control se llegó a crear a partir de la actualización acumulativa de julio de 2019. Ayuda a administrar la configuración de servidores, usuarios, clientes y dispositivos en el entorno de una organización.

Es posible que el Panel de control heredado no funcione porque la tecnología Silverlight ha llegado a la fase de fin de soporte técnico el 12 de octubre de 2021. Para obtener más información, [vea Silverlight End of Support](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788).

> [!NOTE]
> Para obtener información sobre el Panel de control heredado, vea [Panel de control](../SfbServer/management-tools/install-and-open-administrative-tools.md)y vaya a la sección Skype Empresarial Server Panel de **control**.

## <a name="access-control-panel"></a>Panel de control de acceso

Para iniciar el nuevo Panel de control en el explorador, escriba https:// &lt; pool-FQDN &gt; /macp o una dirección URL sencilla configurada.

El nuevo Panel de control incluye elementos de menú usados habitualmente que cubren la mayoría de las necesidades de la organización. Hay algunos elementos de menú del Panel de control heredado que no están disponibles en el nuevo Panel de control. Sin embargo, hay una opción para que el usuario pueda aprovechar las funcionalidades de esos elementos de menú a través de cmdlets de PowerShell. Para obtener más información, consulte la tabla siguiente.

> [!NOTE]
> La documentación de otros elementos de menús estará disponible posteriormente por fases.

## <a name="client"></a>Client

|Submenú  |Origen de información para cmdlet  |
|---------|---------|
|Directiva de versiones de clientes:         |    [Directiva de versión de cliente](use-powershell-client-menu.md#client-version-policy)     |
|Configuración de versiones de cliente      |  [Configuración de versiones de cliente](use-powershell-client-menu.md#client-version-configuration)       |
|Actualización de dispositivos    | [Actualización de dispositivos](use-powershell-client-menu.md#device-update)        |
|Dispositivo de la prueba     | [Dispositivo de la prueba](use-powershell-client-menu.md#test-device)        |
|Configuración de registro de dispositivo         |    [Configuración de registro de dispositivo](use-powershell-client-menu.md#device-log-configuration)     |
|Configuración de dispositivo         |    [Configuración de dispositivos](use-powershell-client-menu.md#device-configuration)     |
|Directiva de movilidad         |    [Directiva de movilidad](use-powershell-client-menu.md#mobility-policy)     |
|Configuración de notificaciones de inserción         |    [Configuración de notificaciones de inserción](use-powershell-client-menu.md#push-notification-configuration)     |

## <a name="security"></a>Seguridad

|Submenú  |Origen de información para cmdlet  |
|---------|---------|
|Registrador         |    [Registrador](use-powershell-security-menu.md#registrar)     |
|Servicio Web      |  [Servicio Web](use-powershell-security-menu.md#web-service)       |
|Directiva de PIN    | [Directiva de PIN](use-powershell-security-menu.md#pin-policy)        |

## <a name="im-and-presence"></a>Mensajería instantánea y presencia

|Submenú  |Origen de información para cmdlet  |
|---------|---------|
|Filtro de archivo         |    [Filtro de archivo](use-powershell-im-and-presence-menu.md#file-filter)     |
|Filtro para direcciones URL      |  [Filtro para direcciones URL](use-powershell-im-and-presence-menu.md#url-filter)       |
