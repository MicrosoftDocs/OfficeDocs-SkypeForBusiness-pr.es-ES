---
title: Configurar la sala de espera de reunión de Microsoft Teams para reuniones confidenciales
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Aprenda a configurar la sala de espera de reuniones de Teams para mejorar la seguridad de las reuniones confidenciales mediante directivas de administración, etiquetas de confidencialidad y plantillas de reunión.
ms.openlocfilehash: 1905bc337f0260e86b2351da5015b8e1ba641bf4
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800156"
---
# <a name="configure-the-microsoft-teams-meeting-lobby-for-sensitive-meetings"></a>Configurar la sala de espera de reunión de Microsoft Teams para reuniones confidenciales

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

La sala de espera de la reunión es una herramienta que puede usar para asegurarse de que no se admitan personas inapropiadas en las reuniones. Al mantener diferentes tipos de participantes en la sala de espera, los organizadores de la reunión pueden supervisarlos y asegurarse de que les resulte adecuado asistir a la reunión.

De forma predeterminada, las personas de su organización e [invitados](guest-access.md) son admitidos a las reuniones directamente y los participantes de dominios de confianza y participantes anónimos deben esperar en la sala de espera para ser admitidos por un organizador de la reunión. Los organizadores de reuniones pueden cambiar esta configuración predeterminada para cada reunión que creen.

El administrador de Teams puede controlar la sala de espera y otras opciones relacionadas mediante directivas de reunión, plantillas de reunión y etiquetas de confidencialidad para personalizar la experiencia de diferentes usuarios y tipos de reuniones.

En la tabla siguiente se enumeran las características que puede usar para ayudar a administrar la experiencia de sala de espera de su organización y dónde configurarlas.

|Setting|directiva de Administración|Etiqueta de confidencialidad|Plantilla|Organizador de la reunión|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Anunciar cuándo se unen o abandonan los autores de llamadas de acceso telefónico local|No|No|Sí|Sí|
|Los usuarios anónimos y los autores de llamadas de acceso telefónico local pueden iniciar una reunión|Sí|No|No|No|
|Los usuarios anónimos pueden unirse a una reunión|Sí|No|No|No|
|Personas marcación puede omitir la sala de espera|Sí|Sí|Sí|Sí|
|Quién puede omitir la sala de espera|Sí|Sí|Sí|Sí|

Para obtener información sobre cómo usar plantillas y etiquetas de confidencialidad para configurar la configuración de reuniones, vea [Información general sobre plantillas de reunión personalizadas en Microsoft Teams](custom-meeting-templates-overview.md) y [Usar etiquetas de confidencialidad para proteger elementos de calendario, reuniones de Teams y chat](/microsoft-365/compliance/sensitivity-labels-meetings).

> [!Note]
> La configuración de reuniones en etiquetas de confidencialidad y plantillas de reunión personalizadas requieren Teams Premium.

## <a name="lobby-settings-for-different-types-of-meetings"></a>Configuración de la sala de espera para diferentes tipos de reuniones

Las siguientes opciones están disponibles para las personas que pueden omitir la sala de espera:

- Todos
- Usuarios de mi organización y de organizaciones de confianza e invitados
- Usuarios en mi organización e invitados
- Usuarios en mi organización
- Personas invitados
- Organizadores y co-organizadores

Aunque el organizador de la reunión suele elegir qué configuración usar para cada reunión, puede exigir una configuración determinada con una plantilla de reunión o una etiqueta de confidencialidad.

Si su organización requiere que determinados tipos de reuniones no sean atendidas por personas de fuera de la organización, considere la posibilidad de una plantilla de reunión que solo permita a los usuarios de su organización omitir la sala de espera. Así se asegura de que las personas de fuera de la organización a las que accidentalmente se ha invitado o enviado un vínculo de reunión no pueden unirse a la reunión directamente.

Si su organización tiene reuniones donde se comparte información altamente confidencial y necesita asegurarse de que solo asistan ciertas personas, considere la posibilidad de usar una plantilla de reunión o una etiqueta de confidencialidad que solo permita a los organizadores de la reunión omitir la sala de espera. Esto garantiza que los organizadores puedan consultar a cada participante entrante para asegurarse de que deben estar en la reunión. Esto también impide que la reunión se inicie hasta que se una un organizador.

Para reuniones confidenciales en general, considere la posibilidad de usar la opción **Personas invitados**. Esto garantiza que las personas que no tienen una invitación a la reunión (incluidas las invitaciones reenviadas) pasen por la sala de espera. (El organizador de la reunión también puede impedir el reenvío al crear la reunión).

Para obtener información sobre el uso conjunto de plantillas de reunión y etiquetas de confidencialidad, vea [Usar juntas las plantillas de reunión, las etiquetas de confidencialidad y las directivas de administración de Teams para reuniones confidenciales](meeting-templates-sensitivity-labels-policies.md).

### <a name="attendees-calling-in-by-phone"></a>Asistentes llamando por teléfono

De forma predeterminada, los asistentes que llaman por teléfono pasan por la sala de espera. Los administradores pueden cambiar este valor predeterminado con los **usuarios de acceso telefónico local pueden omitir la** directiva de la reunión del administrador de la sala de espera. Si desea exigir que esta configuración esté activada o desactivada, debe usar una plantilla de reunión o una etiqueta de confidencialidad.

Si hay circunstancias en las que desea permitir que los autores de las llamadas omitan la sala de espera, los organizadores de la reunión pueden controlar esta configuración, o puede exigirla a través de una plantilla de reunión o una etiqueta de confidencialidad.

#### <a name="join-and-leave-notifications"></a>Notificaciones para unirse y dejar de recibir notificaciones

Los organizadores de la reunión tienen la opción de que los asistentes llamen por teléfono y que se anuncie cuando se unan o abandonen una reunión. Si desea asegurarse de que se anuncian los asistentes por teléfono para determinados tipos de reuniones, puede aplicar esta configuración con una plantilla de reunión.

## <a name="meeting-with-anonymous-participants"></a>Reunión con participantes anónimos

A menos que permita que todos omitan la sala de espera, los participantes anónimos deben pasar por la sala de espera para asistir a la reunión. A continuación, los organizadores de la reunión pueden decidir si se debe admitir a estos participantes.

Si su organización no permite que participantes anónimos se unan a reuniones, puede desactivar la opción **Los usuarios anónimos pueden unirse a una reunión** en el Centro de administración de Teams. Para obtener más información, consulte [Administrar la configuración de reuniones en Microsoft Teams](/microsoftteams/meeting-settings-in-teams).

Si tiene determinados grupos en su organización, como el marketing, que necesitan organizar reuniones con participantes anónimos y otros (como la investigación) que no deberían, puede usar las directivas de reunión de Teams para configurar unirse a una reunión anónima para diferentes grupos. (Tendrá que activar la configuración **usuarios anónimos pueden unirse a una reunión** mencionada anteriormente para que funcione. Para obtener más información, consulte [Configuración de la directiva de reunión: participantes & invitados](/microsoftteams/meeting-policies-participants-and-guests).

## <a name="related-topics"></a>Temas relacionados

[Configurar reuniones de Teams con tres niveles de protección](configure-meetings-three-tiers-protection.md)

[Administrar reuniones externas y chatear en Microsoft Teams](/microsoftteams/manage-external-access)
