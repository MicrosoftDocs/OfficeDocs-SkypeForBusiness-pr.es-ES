---
title: Usar Teams con servicios de escritorio remoto
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar Microsoft Teams con servicios de escritorio remoto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e18aa0ad95033550d0ef2f7c6049e700d917798
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606099"
---
# <a name="teams-in-remote-desktop-services"></a>Teams en Servicios de Escritorio remoto

En este artículo se describen los requisitos y limitaciones para usar Microsoft Teams en un entorno de servicios de escritorio remoto (RDS).

## <a name="what-is-rds"></a>¿Qué es RDS?

Servicios de Escritorio remoto (RDS) es la plataforma de elección para crear soluciones de virtualización para cada necesidad de los clientes finales. RDS le permite entregar aplicaciones virtualizadas individuales, proporcionar acceso seguro a escritorio móvil y remoto, y proporcionar a los usuarios finales la capacidad de ejecutar sus aplicaciones y escritorios desde la nube.

RDS ofrece flexibilidad de implementación, rentabilidad y extensibilidad. RDS se entrega a través de una variedad de opciones de implementación, entre las que se incluyen Windows Server 2016 para implementaciones locales, Microsoft Azure para implementaciones en la nube y una sólida gama de soluciones de partners.
Según el entorno y las preferencias, puede configurar la solución RDS para la virtualización basada en sesión, como una infraestructura de escritorio virtual (VDI)

Actualmente, Teams en un entorno de servicios de escritorio remoto está disponible con soporte técnico para la colaboración y la funcionalidad de chat. Para garantizar una experiencia de usuario óptima, siga las instrucciones de este artículo.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Equipos en RDS con chat y colaboración

Si su organización quiere usar solo las características de chat y colaboración en Teams, puede establecer directivas a nivel de usuario para desactivar las funciones de llamadas y reuniones en Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Establecer directivas para desactivar la funcionalidad de llamadas y reuniones

Puede establecer directivas mediante el Centro de administración de Microsoft Teams o PowerShell. Es posible que los cambios de directiva tarden algún tiempo (algunas horas) en propagarse. Si no ves los cambios de una cuenta determinada inmediatamente, vuelve a intentarlo en unas pocas horas.

[**Directivas de llamada:**](teams-calling-policy.md) Teams incluye la directiva de llamadas DisallowCalling integrada, en la que se desactivan todas las características de llamada. Asigne la directiva No permitir llamada a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

[**Directivas de reunión**](meeting-policies-overview.md): Teams incluye la directiva de reunión AllOff integrada, en la que se desactivan todas las características de reunión. Asigne la directiva AllOff a todos los usuarios de su organización que usen Teams en un entorno virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Asignar directivas mediante el Centro de administración de Microsoft Teams

Para asignar la directiva de llamada DisallowCalling y la directiva de reunión AllOff a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios**.
2. Seleccione el usuario seleccionando a la izquierda del nombre de usuario y, a continuación, seleccione **Editar configuración**.
3. Siga estos pasos:

    a.  En **Directiva de llamadas**, seleccione **No permitir llamadas**.

    b.  En **Directiva de reunión**, seleccione **AllOff**.

4. Seleccione **Aplicar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.
2. En la columna **&#x2713;** (marca de verificación), seleccione los usuarios. Para seleccionar todos los usuarios, seleccione la &#x2713; (marca de verificación) en la parte superior de la tabla.
3. Selecciona **Editar configuración**, realiza los cambios que quieras y, a continuación, selecciona **Aplicar**.

O bien, también puede hacer lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la directiva que quiera asignar. Por ejemplo:

    - Vaya a **Directivas de llamadas** de **voz** >  y, a continuación, seleccione **No permitir llamadas**.
    - Vaya a **Directivas** >  de **reunión de** reuniones y, después, seleccione **AllOff**.

2. Seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando termine de agregar usuarios, seleccione **Guardar**.

#### <a name="assign-policies-using-powershell"></a>Asignar directivas con PowerShell

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para asignar la directiva de llamada DisallowCalling a un usuario.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de llamada, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

En el ejemplo siguiente se muestra cómo usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para asignar la directiva de reunión AllOff a un usuario.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para obtener más información sobre el uso de PowerShell para administrar directivas de reunión, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).