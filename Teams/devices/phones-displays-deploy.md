---
title: Implementar equipos y equipos con el uso de Intune
ms.author: v-lanac
author: lanachin
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
description: Este artículo proporciona una descripción general de las características de Microsoft teams que se admiten.
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787641"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Implementar equipos y equipos con el uso de Intune

Este artículo le ofrece información general sobre cómo implementar teléfonos y equipos de equipos con Intune.

## <a name="conditional-access"></a>Acceso condicional

El acceso condicional es una característica de Azure Active Directory (Azure AD) que le ayuda a garantizar que los dispositivos que tienen acceso a los recursos de Office 365 estén administrados correctamente y sean seguros.  Si aplica directivas de acceso condicional al servicio de Teams, los dispositivos Android (incluidos los teléfonos y equipos de Teams) los equipos de acceso deben estar inscritos en Intune y su configuración debe cumplir sus directivas.  Si el dispositivo no se ha inscrito en Intune, o si se ha inscrito pero su configuración no cumple con las directivas, el acceso condicional evitará que un usuario inicie sesión en la aplicación de Teams o la use en el dispositivo.

Normalmente, las directivas de cumplimiento definidas en Intune se asignan a grupos de usuarios.  Esto significa que si asigna una directiva de cumplimiento de Android a user@contoso.com, esa Directiva se aplicará por igual a su smartphone Android y a cualquier dispositivo de Teams basado en Android en el que se inicie sesión user@contoso.com.

Si usa el acceso condicional, que requiere que se exija la inscripción de Intune, en su organización, hay un par de cosas que debe configurar para permitir una inscripción correcta de Intune:

- **Licencia de Intune** El usuario que inicia sesión en el dispositivo de Teams debe tener una licencia para Intune.  Siempre y cuando el dispositivo de Teams haya iniciado sesión con una cuenta de usuario válida, el dispositivo se inscribirá automáticamente en Microsoft Intune como parte del proceso de inicio de sesión.
- **Configurar Intune** Debe tener configurado un inquilino de Intune configurado correctamente para la inscripción de administrador de dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar Intune para inscribir dispositivos basados en Android

Los dispositivos basados en Android se administran en Intune a través de administración de administrador de dispositivos de Android (DA). Antes de que los dispositivos puedan ser inscritos en Intune, hay que realizar algunos pasos básicos.  Si ya está administrando dispositivos con Intune hoy, probablemente ya haya realizado todas estas acciones.  De lo contrario, esto es lo que debe hacer:

1. Establezca la autoridad de MDM (administración de dispositivos móviles) de Intune.  Si nunca ha usado Intune antes, debe configurar la autoridad de MDM antes de poder inscribir dispositivos. Para obtener más información, vea [establecer la entidad de administración de dispositivos móviles](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Este es un paso que debe realizarse una sola vez al crear un nuevo inquilino de Intune.
2. Habilitar la inscripción de administrador de dispositivos Android. Los dispositivos de equipos basados en Android se administran como dispositivos de administrador de dispositivos con Intune.  La inscripción de administrador de dispositivos está desactivada de forma predeterminada para los inquilinos recién creados.  Para obtener más información, consulte inscripción en el [Administrador de dispositivos Android](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Asignar licencias a los usuarios. Los usuarios de los dispositivos de equipos que se inscriban en Intune deben tener asignada una licencia válida de Intune. Para obtener más información, vea [asignar licencias a los usuarios para que puedan inscribir dispositivos en Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Asignar directivas de cumplimiento para el administrador del dispositivo.  Crear una directiva de cumplimiento de administrador de dispositivos de Android y asignarla al grupo de Azure Active Directory que contenga los usuarios que iniciarán sesión en los dispositivos de Teams. Para obtener más información, consulte [usar directivas de cumplimiento para establecer reglas para los dispositivos que administra con Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Consulte también

[Teléfonos para Teams](phones-for-teams.md)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)

[Teams muestra](teams-displays.md)

[Administrar los dispositivos en Teams](device-management.md)

[Marketplace de equipos](https://office.com/teamsdevices)
