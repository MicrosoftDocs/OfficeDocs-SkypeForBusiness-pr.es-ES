---
title: Guía de seguridad para Microsoft Teams
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
ms.openlocfilehash: 3486df0ca12303a9351c756df4184f160e95ab34
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868699"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Usar Microsoft Teams de forma segura en equipos compartidos

Siempre que sea posible, *se recomienda* a las empresas emplear un enfoque de Confianza cero con los dispositivos cliente que hacen uso de las funciones de administración de dispositivos, las comprobaciones de estado del dispositivo y la aplicación de directivas, el cifrado a nivel de dispositivo y otras características de seguridad.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Imagen de Confianza cero que muestra en círculos azules los principios básicos de la Confianza cero: la comprobación explícita, los privilegios mínimos y la suposición de vulneraciones.":::

Los administradores pueden crear condiciones muy seguras si *insisten* en la comprobación, en los privilegios mínimos y en la suposición de que se va a intentar comprometer la seguridad; estos principios llevan a tomar medidas que reducen el riesgo para los usuarios y los datos.

> [!TIP]
> Para un examen más profundo de los principios de Confianza cero, puede ver [estos vídeos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Consejos para usar Microsoft Teams de forma segura desde un equipo compartido.

Si bien puede que esto no sea posible o práctico en todos los escenarios, sigue siendo importante que los administradores de seguridad sigan lo mejor que puedan las instrucciones para el uso de Teams en un equipo compartido o en un dispositivo no administrado.

Deben elaborarse planes para ceñirse a las directrices tan pronto como sea posible.

1. Haga uso de las funciones de seguridad de la plataforma del sistema operativo.
    1. Asegúrese de que el sistema operativo se haya configurado para instalar actualizaciones automáticas desde el proveedor del sistema operativo (lo que, en el caso de Microsoft Systems, se puede realizar mediante [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)). 
    2. Asegúrese de que todas las funciones de cifrado de dispositivo, como [**BitLocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview), estén habilitadas y de que la clave utilizada para acceder al dispositivo esté protegida.  Tenga en cuenta que la mayoría de los [**dispositivos modernos con Windows 10 son compatibles con BitLocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10). 
    1. Utilice funciones antivirus como las ofrecidas por [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) en sus dispositivos.
    1. Se recomienda encarecidamente el uso de [cuentas de usuario independientes](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) para cada usuario del sistema.
    1. *No* conceda ni utilice privilegios de administrador para las funciones no administrativas (como navegar por la web, ejecutar Teams, etc.).

2. Aproveche las funciones de seguridad del explorador.
    1. Utilice sesiones de exploración privada para minimizar los datos y el historial que se conservan en el disco. Por ejemplo, use [la exploración de InPrivate en Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [la exploración en modo incógnito de Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) o las funcionalidades que ofrezca su explorador para navegar de forma privada. 
    1. Se recomienda cambiar el comportamiento del sistema para activar la exploración privada *de forma predeterminada*. 

3. Utilice el explorador para desplazarse a la [aplicación web de Teams](https://teams.microsoft.com) (también conocido como cliente *web*) y utilícela, en lugar de usar el cliente descargable de Teams.

4. Cuando termine de usar el sistema compartido, debe: 
    1. [Cerrar la sesión de Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Cerrar todas las pestañas y ventanas del explorador.
    1. Cerrar sesión en el dispositivo.

Los elementos anteriores no constituyen una lista completa de las prácticas recomendadas o de los controles de seguridad que cubren todos los casos. Por tanto, puede que existan acciones adicionales que se puedan llevar a cabo en su entorno (por ejemplo, puede que los administradores de seguridad decidan usar Vínculos seguros y Datos adjuntos seguros para Teams si tiene [ATP de Office 365 Plan 1 o 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)). Sin embargo, estos pasos son un punto de partida para crear instrucciones de uso de Teams en dispositivos compartidos.

## <a name="more-information"></a>Más información

[BitLocker en Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker para Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[Seguridad de punto de conexión en Intune](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

[Habilitar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Antivirus de Microsoft defender en la Seguridad de Windows y [ejecutar exámenes](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Artículo del Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Cliente web de Teams o aplicación web de Teams](https://docs.microsoft.com/microsoftteams/get-clients#web-client)

[Seguridad y Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide)
