---
title: Usar Teams con servicios de escritorio remoto
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar Microsoft Teams con servicios de escritorio remoto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ac88778fca7034446d0ec42a0a4a65d7c76f979
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278910"
---
# <a name="teams-in-remote-desktop-services"></a>Teams en Servicios de Escritorio remoto

En este artículo se describen los requisitos y limitaciones para usar Microsoft Teams en un entorno de servicios de escritorio remoto (RDS).

## <a name="what-is-rds"></a>¿Qué es RDS?

Servicios de Escritorio remoto (RDS) es la plataforma elegida para crear soluciones de virtualización para cada cliente final que necesite. RDS le permite ofrecer aplicaciones virtualizadas individuales, proporcionar acceso móvil y remoto seguro de escritorio y proporcionar a los usuarios finales la capacidad de ejecutar sus aplicaciones y escritorios desde la nube.

RDS ofrece flexibilidad, eficiencia de costos y extensibilidad. RDS se entrega a través de una amplia variedad de opciones de implementación, como Windows Server 2016 para implementaciones locales, Microsoft Azure para implementaciones en la nube y una matriz sólida de soluciones de asociados.
Según el entorno y las preferencias, puede configurar la solución RDS para la virtualización basada en sesiones, como una infraestructura de escritorio virtual (VDI)

Actualmente, Teams en un entorno de servicios de Escritorio remoto está disponible con soporte técnico para la funcionalidad de colaboración y chat. Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams en VDI con chat y colaboración

Si su organización desea usar solo las características de chat y colaboración en Teams, puede establecer directivas a nivel de usuario para desactivar la funcionalidad de llamadas y reuniones en Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Establecer directivas para desactivar la funcionalidad de llamadas y reuniones

Puede establecer directivas mediante el Centro de administración de Microsoft Teams o PowerShell. Es posible que los cambios de la directiva tarden algún tiempo (unas horas) en propagarse. Si no ve los cambios de una cuenta determinada inmediatamente, inténtelo de nuevo en unas horas.

[**Directivas de llamadas:**](teams-calling-policy.md)Teams incluye la directiva de llamadas DisallowCalling integrada, en la que todas las características de llamada están desactivadas. Asigne la directiva DisallowCalling a todos los usuarios de su organización que usan Teams en un entorno virtualizado.

[**Directivas de reunión:**](meeting-policies-in-teams.md)Teams incluye la directiva de reunión AllOff integrada, en la que se desactivarán todas las características de la reunión. Asigne la directiva AllOff a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Asignar directivas mediante el Centro de administración de Microsoft Teams

Para asignar la directiva de llamada DisallowCalling y la directiva de reunión AllOff a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios.**
2. Seleccione el usuario seleccionando a la izquierda del nombre de usuario y, a continuación, **seleccione Editar configuración.**
3. Siga estos pasos:

    a.  En **Directiva de llamada,** **seleccione No permitir llamada.**

    b.  En **Directiva de reunión,** seleccione **AllOff.**

4. Seleccione **Aplicar.**

Para asignar una directiva a varios usuarios a la vez:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.
2. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, seleccione la &#x2713; (marca de verificación) en la parte superior de la tabla.
3. Seleccione **Editar configuración,** realice los cambios que desee y, a continuación, **seleccione Aplicar.**

O bien, también puede seguir estos pasos:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la directiva que desea asignar. Por ejemplo:

    - Vaya a **directivas de** llamadas  >  **de** voz y, a continuación, seleccione No **permitir llamada.**
    - Vaya a **Directivas de reuniones**  >  **y,** a continuación, seleccione **AllOff.**

2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, seleccione **Guardar.**

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para asignar la directiva de llamada DisallowCalling a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para obtener más información sobre cómo usar PowerShell para administrar directivas de llamadas, consulte [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la directiva de reunión AllOff a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de reuniones, consulte [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)
