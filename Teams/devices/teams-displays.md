---
title: Pantallas de Microsoft Teams
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: En este artículo se proporciona información general sobre las características compatibles con las pantallas de Microsoft Teams.
ms.openlocfilehash: 8b06078633dd8c7ee43c2ee98ad1f3e4751d3a51
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606029"
---
# <a name="microsoft-teams-displays"></a>Pantallas de Microsoft Teams

Las pantallas de Microsoft Teams son una categoría de dispositivos de Teams dedicados todo en uno que cuentan con una pantalla táctil ambiental y una experiencia de manos libres con tecnología de Cortana. Este artículo proporciona información general sobre las pantallas de Teams y puede ayudarle a planear, entregar y administrar pantallas de Teams en su organización.

Las pantallas de Teams reúnen sus características&ndash;favoritas de Teams en un solo dispositivo: chat, reuniones, llamadas, calendario y archivos&ndash;. Con las pantallas de Teams, los usuarios pueden usar un micrófono, una cámara y altavoces (o auriculares Bluetooth) para disfrutar de una experiencia de llamada y reunión confiable. Las pantallas de Teams se integran con los equipos Windows de los usuarios para ofrecer una experiencia complementaria que permite una interacción perfecta entre dispositivos.

Para obtener más información, consulte [Introducción a las pantallas de Teams](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Se muestran las características compatibles con Teams

Además de las [características compatibles con los teléfonos de Teams](phones-for-teams.md#features-supported-by-teams-phones), las siguientes características son únicas para las pantallas de Teams:

- **Pantallas dedicadas para Teams** Los usuarios pueden acceder a todas las características principales de Teams, como chat, reuniones, llamadas, equipos y canales, archivos y mucho más.
- **Experiencia ambiental** Los usuarios pueden mantenerse al tanto de su trabajo con pantallas siempre activadas y de vista rápida para ver las actividades y notificaciones importantes sin tener que cambiar el contexto en su dispositivo de trabajo principal. Los usuarios también pueden personalizar las pantallas de Teams personalizando el fondo a través de la configuración.
- **Manos libres con Cortana** Los usuarios pueden interactuar con las pantallas de Teams con su voz para unirse a reuniones y presentarlas sin esfuerzo, dictar respuestas a un chat de Teams, comprobar lo que hay en el calendario y mucho más.
- **Dejar una nota en la pantalla de bloqueo** Los invitados pueden elegir dejar notas de audio, vídeo y texto, y los usuarios pueden comprobar las notas que dejan los invitados y ver quién ha pasado por aquí.  

## <a name="required-licenses"></a>Licencias necesarias

Las licencias de Teams se pueden comprar como parte de [Microsoft 365 y Office 365 suscripciones](/office365/servicedescriptions/teams-service-description). Para obtener más información sobre las licencias necesarias para usar las pantallas de Teams, consulte [Llamadas de voz y vídeo con Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Para obtener más información sobre cómo obtener Teams, consulte [Cómo obtener acceso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Implementar pantallas de Teams con Intune

Para obtener más información sobre cómo implementar pantallas de Teams con Intune, vea [Implementar teléfonos y pantallas de Teams](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Administrar pantallas de Teams en su organización

Para administrar los dispositivos de visualización de Teams, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Pantallas de Teams**. Desde aquí, puedes cambiar el perfil de configuración del dispositivo, administrar las actualizaciones, reiniciar dispositivos, agregar y quitar etiquetas de dispositivo y mucho más. Para obtener más información, consulte [Administrar los dispositivos en Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurar el escritorio rápido en pantallas de Teams

El hot desking permite a los usuarios de su organización reservar áreas de trabajo temporales de antemano a través de Teams y Outlook, o desde el propio dispositivo. Cuando la característica de escritorio rápido está habilitada, los usuarios inician sesión en Teams y se muestran con sus credenciales de Microsoft 365 para acceder a sus reuniones, chats y archivos. Al cerrar sesión, toda su información personal se quita del dispositivo.

Para empezar, deberá adquirir [licencias de Salas de Microsoft Teams](../rooms/rooms-licensing.md) y crear cuentas de recursos para cada presentación de Teams. Consulte [Crear cuentas de recursos para salas y dispositivos compartidos de Teams](../rooms/with-office-365.md) para crear cuentas de recursos.

Después de crear cuentas de recursos, puede crear y asignar una directiva para habilitar el escritorio rápido. Consulte [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy) para obtener más información.

> [!IMPORTANT]
> Dado que varias personas usan las pantallas de Teams con escritorio rápido en áreas de trabajo compartidas, las reglas de acceso condicional y otras configuraciones de identidad en su entorno, como la autenticación multifactor, pueden afectar a estos dispositivos y causar problemas de inicio de sesión. Para obtener instrucciones sobre cómo proteger los dispositivos compartidos, consulte [Procedimientos recomendados de autenticación para dispositivos Android compartidos de Teams](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Actualizar los teléfonos de Teams a las pantallas de Teams

Pantallas de Teams es la evolución de los teléfonos de Teams. Puede actualizar los teléfonos de Teams de su organización a las pantallas de Teams con el Centro de administración de Microsoft Teams. Esta opción solo está disponible para los teléfonos que admiten la actualización a Las pantallas de Teams. Para obtener más información, consulte [Actualizar los teléfonos de Teams a las pantallas de Teams](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Vea también

[Presentación de las pantallas de Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Teléfonos para Teams](phones-for-teams.md)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)

[Actualizar teléfonos IP a pantallas de Teams](upgrade-phones-to-displays.md)

[Asistencia por voz de Cortana en Teams](../cortana-in-teams.md)