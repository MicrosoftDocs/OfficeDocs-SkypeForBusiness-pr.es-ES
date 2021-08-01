---
title: 'Guía de seguridad para Microsoft Teams: use Teams de forma segura en equipos compartidos'
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Instrucciones para usar Microsoft Teams de forma segura desde un equipo compartido en el lugar de trabajo.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc886b2783d1398a85e00927a224968d65a9539b
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646011"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Usar Microsoft Teams de forma segura en equipos compartidos

Siempre que sea posible, *se recomienda* a las empresas emplear un enfoque de Confianza cero con los dispositivos cliente que hacen uso de las funciones de administración de dispositivos, las comprobaciones de estado del dispositivo y la aplicación de directivas, el cifrado a nivel de dispositivo y otras características de seguridad.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Imagen de Confianza cero que muestra en círculos azules los principios básicos de la Confianza cero: la comprobación explícita, los privilegios mínimos y la suposición de vulneraciones.":::

Los administradores pueden crear condiciones seguras si *insisten* en la comprobación, en los privilegios mínimos y en la suposición de que se va a intentar comprometer la seguridad; estos principios llevan a tomar medidas que reducen el riesgo para los usuarios y los datos.

> [!TIP]
> Para un examen más profundo de los principios de Confianza cero, puede ver [estos vídeos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Consejos para usar Microsoft Teams de forma segura desde un equipo compartido.

Si bien puede que esto no sea posible o práctico en todos los escenarios, sigue siendo importante que los administradores de seguridad sigan lo mejor que puedan las instrucciones para el uso de Teams en un equipo compartido o en un dispositivo no administrado.

Deben elaborarse planes para ceñirse a las directrices tan pronto como sea posible.

1. Haga uso de las funciones de seguridad de la plataforma del sistema operativo.
    1. Asegúrese de que el sistema operativo se haya configurado para instalar actualizaciones automáticas desde el proveedor del sistema operativo (lo que, en el caso de Microsoft Systems, se puede realizar mediante [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)). 
    1. Asegúrese de que todas las funciones de cifrado de dispositivo, como [**BitLocker**](/windows/security/information-protection/bitlocker/bitlocker-overview), estén habilitadas y de que la clave utilizada para acceder al dispositivo esté protegida. Tenga en cuenta que la mayoría de los dispositivos de [**Windows 10 modernos admiten bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10). 
    1. Utilice funciones antivirus como las ofrecidas por [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) en sus dispositivos.
    1. Se recomienda encarecidamente el uso de [cuentas de usuario independientes](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) para cada usuario del sistema.
    1. *No* conceda ni utilice privilegios de administrador para las funciones no administrativas (como navegar por la web, ejecutar Teams, etc.).

Si no se pueden cumplir las instrucciones anteriores, le recomendamos que use los procedimientos recomendados de seguridad adicionales del explorador:

1. Aplique las funcionalidades de seguridad del explorador.
    1. Utilice sesiones de exploración privada para minimizar los datos y el historial que se conservan en el disco. Por ejemplo, use [la exploración de InPrivate en Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [la exploración en modo incógnito de Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) o las funcionalidades que ofrezca su explorador para navegar de forma privada. 
    1. Se recomienda cambiar el comportamiento del sistema para activar la exploración privada *de forma predeterminada*. 

2. Utilice el explorador para desplazarse a la [aplicación web de Teams](https://teams.microsoft.com) (también conocido como cliente *web*) y utilícela, en lugar de usar el cliente descargable de Teams.

3. Cuando termine de usar el sistema compartido, debe: 
    1. [Cerrar la sesión de Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Cerrar todas las pestañas y ventanas del explorador.
    1. Cerrar sesión en el dispositivo.

Los elementos anteriores no constituyen una lista completa de las prácticas recomendadas o de los controles de seguridad y no abarcan todos los casos. Por tanto, puede que se deban tomar acciones adicionales en su entorno (por ejemplo, puede que los administradores de seguridad decidan usar Vínculos seguros y Datos adjuntos seguros para Teams si tiene [ATP de Office 365 Plan 1 o 2](/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)). Sin embargo, estos pasos son un punto de partida para crear instrucciones de uso de Teams en dispositivos compartidos.

## <a name="more-information"></a>Más información

[BitLocker en Configuration Manager](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker para Windows 10 en Intune](/mem/intune/protect/encrypt-devices)

[Seguridad de punto de conexión en Intune](/mem/intune/protect/endpoint-security)

[Habilitar](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Antivirus de Microsoft defender en la Seguridad de Windows y [ejecutar exámenes](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Artículo del Centro de seguridad de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Cliente web de Teams o aplicación web de Teams](./get-clients.md#web-client)

[Seguridad y Microsoft Teams](./teams-security-guide.md)
