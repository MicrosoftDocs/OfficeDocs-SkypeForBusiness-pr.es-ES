---
title: Microsoft Teams pantallas
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: En este artículo se proporciona información general sobre las características compatibles con Microsoft Teams pantallas.
ms.openlocfilehash: 8c8004edd12042ca27e77e545f23b8770f8d1899
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926333"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams pantallas

Microsoft Teams pantallas son una categoría de dispositivos de Teams dedicados todo en uno que incluyen una pantalla táctil ambiente y una experiencia manos libres con tecnología de Cortana. En este artículo se proporciona información general sobre Teams pantallas y puede ayudarle a planear, entregar y administrar Teams pantallas de su organización.

Teams muestra reúne sus características favoritas Teams&ndash; chat, reuniones, llamadas, calendario y archivos&ndash; en un único dispositivo. Con Teams pantallas, los usuarios pueden usar un micrófono, una cámara y unos altavoces (o Bluetooth auriculares) para una experiencia de reunión y llamadas confiables. Teams pantallas se integra con los equipos Windows los usuarios para aportar una experiencia complementaria que permite una interacción sin problemas entre dispositivos.

Para obtener más información, consulte Introducción [a Teams pantallas](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Características compatibles con Teams pantallas

Además de las [características compatibles con Teams teléfonos](phones-for-teams.md#features-supported-by-teams-phones), las siguientes características son únicas para Teams pantallas:

- **Pantallas dedicadas para Teams** Los usuarios pueden acceder a todas las características principales de Teams, como chat, reuniones, llamadas, equipos y canales, archivos y mucho más.
- **Experiencia ambiental** Los usuarios pueden mantenerse al día de su trabajo fácilmente con pantallas siempre en marcha y con un vistazo para ver actividades y notificaciones importantes sin cambiar el contexto en su dispositivo de trabajo principal. Los usuarios también pueden personalizar Teams pantallas personalizando el fondo a través de la configuración.
- Manos libres con **Cortana** Los usuarios pueden interactuar con Teams pantallas con su voz para unirse y presentar sin esfuerzo en reuniones, dictar respuestas a un chat de Teams, comprobar lo que hay en el calendario y mucho más.
- **Dejar una nota en la pantalla de bloqueo** Los invitados pueden elegir dejar notas de audio, vídeo y texto, y los usuarios pueden comprobar las notas que dejan los invitados y ver quién ha pasado por aquí.  

## <a name="required-licenses"></a>Licencias necesarias

Teams licencias se pueden comprar como parte de Microsoft 365 [y Office 365 suscripciones](/office365/servicedescriptions/teams-service-description). Para obtener más información sobre las licencias necesarias para usar Teams pantallas, vea Llamadas y [videollamadas con Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Para obtener más información sobre cómo obtener Teams, consulte [¿Cómo puedo obtener acceso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Implementar Teams pantallas con Intune

Para obtener más información sobre cómo implementar Teams pantallas con Intune, vea Implementar Teams [teléfonos y Teams pantallas](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Administrar Teams pantallas en su organización

Para administrar los Teams de pantalla, en la navegación izquierda del centro de administración de Microsoft Teams, vaya a **Teams pantallas**. Desde aquí, puede cambiar el perfil de configuración del dispositivo, administrar actualizaciones, reiniciar dispositivos, agregar y quitar etiquetas de dispositivo y mucho más. Para obtener más información, vea [Administrar los dispositivos en Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurar el servicio de escritorio en Teams pantallas

El escritorio en caliente permite a los usuarios de su organización reservar áreas de trabajo temporales por adelantado a través de Teams y Outlook, o desde el propio dispositivo. Cuando el servicio de escritorio rápido está habilitado, los usuarios inician sesión en Teams se muestran con sus Microsoft 365 credenciales para acceder a sus reuniones, chats y archivos. Al cerrar sesión, toda su información personal se quita del dispositivo.

Para empezar, deberá adquirir licencias de Salas de Microsoft Teams Estándar y crear cuentas de recursos para cada Teams pantalla. Vea [Implementar Salas de Microsoft Teams con Office 365](../rooms/with-office-365.md) para crear cuentas de recursos.

Después de crear cuentas de recursos, puede crear y asignar una directiva para habilitar el hot desking. Vea [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) para obtener más información.

> [!IMPORTANT]
> Como varias personas usan Teams pantallas con escritorio rápido en áreas de trabajo compartidas, las reglas de acceso condicional y otras configuraciones de identidad de su entorno, como la autenticación multifactor, pueden afectar a estos dispositivos y causar problemas de inicio de sesión. Para obtener instrucciones sobre cómo proteger dispositivos compartidos, vea Procedimientos recomendados de autenticación [para dispositivos Teams Dispositivos Android](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Actualizar Teams teléfonos a Teams pantallas

Teams pantallas es la evolución de Teams teléfonos. Puede actualizar Teams teléfonos de su organización para Teams pantallas con el centro Microsoft Teams administración. Esta opción solo está disponible para teléfonos compatibles con la actualización a Teams pantallas. Para obtener más información, vea [Actualizar Teams teléfonos para Teams pantallas](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Vea también

[Presentación de Microsoft Teams pantallas](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Teléfonos para Teams](phones-for-teams.md)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)

[Actualizar teléfonos IP a Teams pantallas](upgrade-phones-to-displays.md)

[Cortana de voz en Teams](../cortana-in-teams.md)