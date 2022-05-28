---
title: Microsoft Teams pantallas
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
search.appverid: MET150
ms.localizationpriority: medium
description: En este artículo se ofrece información general sobre las características compatibles con las pantallas de Microsoft Teams.
ms.openlocfilehash: 4b724370ff348f41b8d4c4406a218e1dd1ba0709
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760872"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams pantallas

Microsoft Teams pantallas son una categoría de dispositivos de Teams dedicados todo en uno que cuentan con una pantalla táctil ambiental y una experiencia de manos libres con tecnología de Cortana. Este artículo proporciona información general sobre las pantallas de Teams y puede ayudarle a planear, entregar y administrar Teams pantallas de su organización.

Teams pantallas reúne sus características&ndash;favoritas de Teams chat, reuniones, llamadas, calendario y archivos&ndash;en un único dispositivo. Con Teams pantallas, los usuarios pueden usar un micrófono, cámara y altavoces (o auriculares Bluetooth) para disfrutar de una experiencia de llamada y reunión confiable. Teams pantallas se integra con los equipos Windows de los usuarios para ofrecer una experiencia complementaria que permite una interacción perfecta entre dispositivos.

Para obtener más información, echa un vistazo a [Comenzar con pantallas de Teams](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Características compatibles con pantallas de Teams

Además de las [características compatibles con los teléfonos Teams](phones-for-teams.md#features-supported-by-teams-phones), las siguientes características son únicas de las pantallas Teams:

- **Pantallas dedicadas para Teams** Los usuarios pueden acceder a todas las principales características Teams, como chat, reuniones, llamadas, equipos y canales, archivos y mucho más.
- **Experiencia ambiental** Los usuarios pueden mantenerse al tanto de su trabajo con pantallas siempre activadas y de vista rápida para ver las actividades y notificaciones importantes sin tener que cambiar el contexto en su dispositivo de trabajo principal. Los usuarios también pueden personalizar Teams pantallas personalizando el fondo a través de la configuración.
- **Manos libres con Cortana** Los usuarios pueden interactuar con Teams pantallas usando su voz para unirse y presentar sin esfuerzo en reuniones, dictar respuestas a un chat Teams, comprobar lo que hay en el calendario y mucho más.
- **Dejar una nota en la pantalla de bloqueo** Los invitados pueden elegir dejar notas de audio, vídeo y texto, y los usuarios pueden comprobar las notas que dejan los invitados y ver quién ha pasado por aquí.  

## <a name="required-licenses"></a>Licencias necesarias

las licencias de Teams se pueden comprar como parte de [las suscripciones de Microsoft 365 y Office 365](/office365/servicedescriptions/teams-service-description). Para obtener más información sobre las licencias necesarias para usar pantallas de Teams, consulte [Llamadas de voz y vídeo con Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Para obtener más información sobre cómo obtener Teams, consulte [Cómo obtener acceso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Implementar pantallas de Teams con Intune

Para obtener más información sobre cómo implementar pantallas de Teams con Intune, consulta [Implementar teléfonos Teams y pantallas de Teams](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Administrar Teams pantallas en la organización

Para administrar los dispositivos de pantalla Teams, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Teams pantallas**. Desde aquí, puedes cambiar el perfil de configuración del dispositivo, administrar las actualizaciones, reiniciar dispositivos, agregar y quitar etiquetas de dispositivo y mucho más. Para obtener más información, consulta [Administrar los dispositivos en Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurar el escritorio caliente en pantallas de Teams

El hot desking permite a los usuarios de tu organización reservar áreas de trabajo temporales de antemano a través de Teams y Outlook, o desde el propio dispositivo. Cuando el escritorio rápido está habilitado, los usuarios inician sesión en Teams se muestra con sus credenciales de Microsoft 365 para acceder a sus reuniones, chats y archivos. Al cerrar sesión, toda su información personal se quita del dispositivo.

Para empezar, deberá adquirir licencias de Salas de Microsoft Teams Estándar y crear cuentas de recursos para cada Teams visualización. Vea [Crear cuentas de recursos para salas y dispositivos de Teams compartidos](../rooms/with-office-365.md) para crear cuentas de recursos.

Después de crear cuentas de recursos, puede crear y asignar una directiva para habilitar el escritorio rápido. Consulte [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) para obtener más información.

> [!IMPORTANT]
> Dado que varias personas usan las pantallas de Teams con escritorio rápido en áreas de trabajo compartidas, las reglas de acceso condicional y otras configuraciones de identidad en su entorno, como la autenticación multifactor, pueden afectar a estos dispositivos y causar problemas de inicio de sesión. Para obtener instrucciones sobre cómo proteger los dispositivos compartidos, vea [Procedimientos recomendados de autenticación para dispositivos de Teams Android compartidos](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Actualizar los teléfonos Teams a pantallas Teams

Teams pantallas es la evolución de los teléfonos Teams. Puede actualizar los teléfonos Teams de su organización a Teams pantallas con el Centro de administración de Microsoft Teams. Esta opción solo está disponible para los teléfonos que admiten la actualización a pantallas de Teams. Para obtener más información, consulta [Actualizar los teléfonos Teams a pantallas de Teams](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Vea también

[Presentación de pantallas de Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Teléfonos para Teams](phones-for-teams.md)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)

[Actualizar los teléfonos IP a pantallas Teams](upgrade-phones-to-displays.md)

[Cortana asistencia de voz en Teams](../cortana-in-teams.md)