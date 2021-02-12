---
title: Implementar teléfonos y pantallas de Teams con Intune
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
description: En este artículo se ofrece información general sobre las características compatibles con las pantallas de Microsoft Teams.
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825420"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Implementar teléfonos y pantallas de Teams con Intune

Este artículo le ofrece información general sobre cómo implementar teléfonos y pantallas de Teams con Intune.

## <a name="conditional-access"></a>Acceso condicional

El acceso condicional es una característica de Azure Active Directory (Azure AD) que le ayuda a garantizar que los dispositivos que acceden a sus recursos de Office 365 se administran correctamente y son seguros.  Si aplica directivas de acceso condicional al servicio de Teams, los dispositivos Android (incluidos los teléfonos y pantallas de Teams) que tienen acceso a Teams deben estar inscritos en Intune y su configuración debe cumplir con sus directivas.  Si el dispositivo no está inscrito en Intune, o si está inscrito pero su configuración no cumple con las directivas, el acceso condicional impedirá que un usuario inicie sesión o use la aplicación Teams en el dispositivo.

Normalmente, las directivas de cumplimiento definidas en Intune se asignan a grupos de usuarios.  Esto significa que, si asigna una directiva de cumplimiento de Android a user@contoso.com, esa directiva se aplicará por igual a su smartphone Android y a cualquier dispositivo de Teams basado en Android en el que user@contoso.com sesión.

Si usa el acceso condicional, que requiere que se aplique la inscripción de Intune, en su organización, debe configurar un par de cosas para permitir una inscripción correcta de Intune:

- **Licencia de Intune** El usuario que inicie sesión en el dispositivo Teams debe tener licencia para Intune.  Siempre que el dispositivo teams haya iniciado sesión en una cuenta de usuario que tenga una licencia válida de Intune, el dispositivo se inscribirá automáticamente en Microsoft Intune como parte del proceso de inicio de sesión.
- **Configurar Intune** Debe tener un espacio empresarial de Intune configurado correctamente para la inscripción del administrador de dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar Intune para inscribir dispositivos basados en Android de Teams

Los dispositivos basados en Android de Teams se administran en Intune a través de la administración del administrador de dispositivos Android (DA). Antes de que los dispositivos se puedan inscribir en Intune, hay algunos pasos básicos que realizar.  Si ya administra dispositivos con Intune hoy, es probable que ya haya hecho todas estas cosas.  Si no es así, esto es lo que debe hacer:

1. Establezca la autoridad de MDM (administración de dispositivos móviles) de Intune.  Si nunca ha usado Intune antes, debe establecer la autoridad de MDM para poder inscribir dispositivos. Para obtener más información, vea [Establecer la autoridad de administración de dispositivos móviles.](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)  Este es un paso único que tiene que realizarse al crear un nuevo espacio empresarial de Intune.
2. Habilite la inscripción del administrador de dispositivos Android. Los dispositivos de Teams basados en Android se administran como dispositivos de administrador de dispositivos con Intune.  La inscripción del administrador del dispositivo está desactivada de forma predeterminada para los inquilinos recién creados.  Para obtener más información, consulte la [inscripción del administrador de dispositivos Android.](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)
3. Asigne licencias a los usuarios. Los usuarios de dispositivos de Teams que se inscriban en Intune deben tener asignada una licencia válida de Intune. Para obtener más información, vea Asignar licencias a los usuarios [para que puedan inscribir dispositivos en Intune.](https://docs.microsoft.com/intune/fundamentals/licenses-assign)
4. Asigne directivas de cumplimiento de administrador de dispositivos.  Cree una directiva de cumplimiento de administrador de dispositivos Android y asígnela al grupo de Azure Active Directory que contiene los usuarios que iniciarán sesión en los dispositivos de Teams. Para obtener más información, vea Usar directivas de cumplimiento para establecer reglas para los dispositivos [que administra con Intune.](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Consulte también

[Teléfonos para Teams](phones-for-teams.md)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)

[Teams muestra](teams-displays.md)

[Administrar los dispositivos en Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
