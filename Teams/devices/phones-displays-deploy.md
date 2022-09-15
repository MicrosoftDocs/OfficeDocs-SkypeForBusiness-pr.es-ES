---
title: Implemente teléfonos, pantallas de Teams, paneles de Teams y Salas de Microsoft Teams en Android con Intune
author: CarolynRowe
ms.author: crowe
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
description: En este artículo se ofrece información general sobre las características compatibles con dispositivos Android de Microsoft Teams.
ms.openlocfilehash: 388848019806740074401400d0fad6847751489e
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705999"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Implemente teléfonos, pantallas de Teams, paneles de Teams y Salas de Microsoft Teams en Android con Intune

Este artículo le ofrece información general sobre cómo implementar teléfonos, pantallas de Teams, paneles de Teams y Salas de Microsoft Teams en Android con Intune.

## <a name="conditional-access"></a>Acceso condicional

El acceso condicional es una característica de Azure Active Directory (Azure AD) que le ayuda a garantizar que los dispositivos que tengan acceso a los recursos de Office 365 se administren y protejan correctamente. Si aplica directivas de acceso condicional al servicio Teams, los dispositivos Android (incluidos teléfonos, pantallas de Teams, paneles de Teams y Salas de Microsoft Teams en Android) que tengan acceso a Teams deben inscribirse en Intune y su configuración debe cumplir con las directivas.  Si el dispositivo no está inscrito en Intune, o si está inscrito pero su configuración no cumple con sus directivas, el acceso condicional impedirá que un usuario inicie sesión en la aplicación de Teams en el dispositivo o la use.

Normalmente, las directivas de cumplimiento definidas dentro de Intune se asignan a grupos de usuarios.  Esto significa que, si asigna una directiva de cumplimiento de Android a user@contoso.com, dicha directiva se aplicará igualmente a su smartphone Android y a cualquier dispositivo de Teams basado en Android en el que user@contoso.com inicie sesión.

Si usa acceso condicional, que requiere que se aplique la inscripción de Intune, en su organización, hay un par de cosas que debe configurar para permitir una inscripción correcta de Intune:

- **Intune licencia** El usuario que inicie sesión en el dispositivo teams debe tener licencia para Intune.  Siempre que el dispositivo teams haya iniciado sesión en una cuenta de usuario que tenga una licencia de Intune válida, el dispositivo se inscribirá automáticamente en Microsoft Intune como parte del proceso de inicio de sesión.
- **Configurar Intune** Debes tener configurada correctamente Intune inquilino configurado para la inscripción de Administrador de dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar Intune para inscribir dispositivos basados en Android de Teams

Los dispositivos basados en Android de Teams se administran mediante Intune a través de la administración de Android Device Administrator (DA). Antes de que los dispositivos se puedan inscribir en Intune, hay algunos pasos básicos que realizar.  Si ya estás administrando dispositivos con Intune hoy, probablemente ya has hecho todas estas cosas.  Si no es así, esto es lo que debes hacer:

> [!NOTE]
> - Si los administradores de inquilinos quieren que los teléfonos de área común se inscriban en Intune, deben agregar una licencia de Intune a la cuenta y seguir los pasos para la inscripción en Intune.
> - Si la cuenta de usuario usada para iniciar sesión en un dispositivo de Teams no tiene licencia para Intune, Intune directivas de cumplimiento y restricciones de inscripción deben deshabilitarse para la cuenta.
> - Si la cuenta de usuario que se usa para iniciar sesión en un dispositivo de Teams tiene licencia para Intune, el dispositivo teams se inscribirá automáticamente en Intune.



1. Establezca Intune entidad de administración de MDM (administración de dispositivos móviles).  

   Si nunca has usado Intune antes, debes establecer la autoridad MDM para poder inscribir dispositivos. Para obtener más información, vea [Establecer la autoridad de administración de dispositivos móviles](/intune/fundamentals/mdm-authority-set).  Este es un paso único que debe realizarse al crear un nuevo espacio empresarial de Intune.
1. Habilita la inscripción del administrador de dispositivos Android.
  
   Los dispositivos de Teams basados en Android se administran como dispositivos de administrador de dispositivos con Intune.  La inscripción del administrador de dispositivos está desactivada de manera predeterminada para los inquilinos recién creados. Consulta [Inscripción del administrador de dispositivos Android](/intune/enrollment/android-enroll-device-administrator).
1. Asignar licencias a usuarios. 
 
   Los usuarios de dispositivos teams que se inscriban en Intune deben tener asignada una licencia de Intune válida. Para obtener más información, vea [Asignar licencias a usuarios para que puedan inscribir dispositivos en Intune](/intune/fundamentals/licenses-assign).
1. Asignar directivas de cumplimiento de Administrador de dispositivos.  

   1. Crear una directiva de cumplimiento de Administrador de dispositivos Android.

   1. Asígnelo al grupo de Azure Active Directory que contiene los usuarios que iniciarán sesión en los dispositivos de Teams. Vea [Usar directivas de cumplimiento para establecer reglas para dispositivos que administra con Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Vea también

[Teléfonos para Teams](phones-for-teams.md)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)

[Teams muestra](teams-displays.md)

[Administrar los dispositivos en Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
