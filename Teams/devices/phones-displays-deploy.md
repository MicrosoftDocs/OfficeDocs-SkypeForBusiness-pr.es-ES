---
title: Implementar los teléfonos de Teams y las pantallas de Teams con Intune
ms.author: v-cichur
author: cichur
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
localization_priority: Normal
description: En este artículo se proporciona información general sobre las características compatibles con microsoft Teams.
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120782"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Implementar los teléfonos de Teams y las pantallas de Teams con Intune

En este artículo se ofrece información general sobre cómo implementar los teléfonos de Teams y las pantallas de Teams con Intune.

## <a name="conditional-access"></a>Acceso condicional

El acceso condicional es una característica de Azure Active Directory (Azure AD) que le ayuda a garantizar que los dispositivos que acceden a sus recursos de Office 365 se administran correctamente y son seguros.  Si aplica directivas de acceso condicional al servicio teams, los dispositivos Android (incluidos los teléfonos de Teams y las pantallas de Teams) que tienen acceso a Teams deben estar inscritos en Intune y su configuración debe cumplir con sus directivas.  Si el dispositivo no está inscrito en Intune o si está inscrito pero su configuración no cumple con las directivas, Acceso condicional impedirá que un usuario inicie sesión en o use la aplicación Teams en el dispositivo.

Normalmente, las directivas de cumplimiento definidas en Intune se asignan a grupos de usuarios.  Esto significa que si asigna una directiva de cumplimiento de Android a user@contoso.com, dicha directiva se aplicará por igual a su smartphone Android y a cualquier dispositivo de Teams basado en Android en el que user@contoso.com sesión.

Si usa acceso condicional, que requiere que se aplique la inscripción de Intune, en su organización, hay un par de cosas que debe configurar para permitir una inscripción correcta de Intune:

- **Licencia de Intune** El usuario que inicie sesión en el dispositivo de Teams debe tener licencia para Intune.  Siempre que el dispositivo teams haya iniciado sesión en una cuenta de usuario que tenga una licencia válida de Intune, el dispositivo se inscribirá automáticamente en Microsoft Intune como parte del proceso de inicio de sesión.
- **Configurar Intune** Debe tener un espacio empresarial de Intune configurado correctamente para la inscripción del administrador de dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar Intune para inscribir dispositivos basados en Android de Teams

Los dispositivos basados en Android de Teams se administran en Intune a través de la administración del administrador de dispositivos Android (DA). Antes de que los dispositivos se puedan inscribir en Intune, hay algunos pasos básicos para realizar.  Si ya está administrando dispositivos con Intune hoy, es probable que ya haya hecho todas estas cosas.  Si no es así, esto es lo que debe hacer:

1. Establecer Intune MDM (administración de dispositivos móviles) Autoridad.  Si nunca ha usado Intune antes, debe establecer la autoridad mdma antes de poder inscribir dispositivos. Para obtener más información, vea Establecer la autoridad de administración [de dispositivos móviles.](/intune/fundamentals/mdm-authority-set)  Este es un paso único que debe realizarse al crear un nuevo inquilino de Intune.
2. Habilitar la inscripción del administrador de dispositivos Android. Los dispositivos teams basados en Android se administran como dispositivos de administrador de dispositivos con Intune.  La inscripción del administrador de dispositivos está desactivada de forma predeterminada para los inquilinos recién creados.  Para obtener más información, vea Inscripción [del administrador de dispositivos Android.](/intune/enrollment/android-enroll-device-administrator)
3. Asignar licencias a los usuarios. Los usuarios de dispositivos de Teams que se inscriban en Intune deben tener asignada una licencia válida de Intune. Para obtener más información, vea Asignar licencias a los usuarios [para que puedan inscribir dispositivos en Intune.](/intune/fundamentals/licenses-assign)
4. Asignar directivas de cumplimiento del administrador de dispositivos.  Cree una directiva de cumplimiento del administrador de dispositivos Android y asígnela al grupo de Azure Active Directory que contiene los usuarios que iniciarán sesión en los dispositivos de Teams. Para obtener más información, vea Usar directivas de cumplimiento para establecer reglas para [dispositivos que administra con Intune.](/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Vea también

[Teléfonos para Teams](phones-for-teams.md)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)

[Se muestra Teams](teams-displays.md)

[Administrar los dispositivos en Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)