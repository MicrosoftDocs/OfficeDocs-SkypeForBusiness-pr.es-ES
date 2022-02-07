---
title: 'Implementar Teams teléfonos, Teams pantallas, Teams paneles y Salas de Microsoft Teams en Android con Intune'
ms.author: serdars
author: SerdarSoysal
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
description: En este artículo se proporciona información general sobre las características compatibles Microsoft Teams dispositivos Android.
---

# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Implementar Teams teléfonos, Teams pantallas, Teams paneles y Salas de Microsoft Teams en Android con Intune

En este artículo se proporciona información general sobre cómo implementar Teams teléfonos, Teams pantallas, Teams paneles y Salas de Microsoft Teams en Android con Intune.

## <a name="conditional-access"></a>Acceso condicional

El acceso condicional es una Azure Active Directory (Azure AD) que le ayuda a garantizar que los dispositivos que obtienen acceso Office 365 los recursos se administran correctamente y son seguros.  Si aplica directivas de acceso condicional al servicio Teams, los dispositivos Android (incluidos teléfonos Teams, pantallas de Teams, paneles de Teams y Salas de Microsoft Teams en Android) que accedan Teams deben estar inscritos en Intune y su configuración debe cumplir con las directivas.  Si el dispositivo no está inscrito en Intune o si está inscrito, pero su configuración no cumple con las directivas, Acceso condicional impedirá que un usuario inicie sesión en o use la aplicación Teams en el dispositivo.

Normalmente, las directivas de cumplimiento definidas en Intune se asignan a grupos de usuarios.  Esto significa que, si asigna una directiva de cumplimiento de Android a user@contoso.com, dicha directiva se aplicará por igual a su smartphone Android y a cualquier dispositivo de Teams basado en Android en el que user@contoso.com sesión.

Si usa acceso condicional, que requiere que se aplique la inscripción de Intune, en su organización, hay un par de cosas que debe configurar para permitir una inscripción correcta de Intune:

- **Licencia de Intune** El usuario que inicia sesión en Teams dispositivo debe tener licencia para Intune.  Siempre que el dispositivo Teams haya iniciado sesión en una cuenta de usuario que tenga una licencia válida de Intune, el dispositivo se inscribirá automáticamente en Microsoft Intune como parte del proceso de inicio de sesión.
- **Configurar Intune** Debe tener un espacio empresarial de Intune configurado correctamente para la inscripción del administrador de dispositivos Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar Intune para inscribir Teams dispositivos basados en Android

Teams dispositivos basados en Android son administrados por Intune a través de la administración del administrador de dispositivos Android (DA). Antes de que los dispositivos se puedan inscribir en Intune, hay algunos pasos básicos para realizar.  Si ya está administrando dispositivos con Intune hoy, es probable que ya haya hecho todas estas cosas.  Si no es así, esto es lo que debe hacer:

> [!NOTE]
> - Si los administradores de inquilinos quieren que los teléfonos de área común se inscriba en Intune, deben agregar una licencia de Intune a la cuenta y seguir los pasos para la inscripción de Intune.
> - Si la cuenta de usuario usada para iniciar sesión en un dispositivo Teams no tiene licencia para Intune, las directivas de cumplimiento de Intune y las restricciones de inscripción deben deshabilitarse para la cuenta.



1. Establecer Intune MDM (administración de dispositivos móviles) Autoridad.  

   Si nunca ha usado Intune antes, debe establecer la autoridad mdma antes de poder inscribir dispositivos. Para obtener más información, vea [Establecer la autoridad de administración de dispositivos móviles](/intune/fundamentals/mdm-authority-set).  Este es un paso único que debe realizarse al crear un nuevo inquilino de Intune.
1. Habilitar la inscripción del administrador de dispositivos Android.
  
   Los dispositivos Teams basados en Android se administran como dispositivos de administrador de dispositivos con Intune.  La inscripción del administrador de dispositivos está desactivada de forma predeterminada para los inquilinos recién creados. Consulte Inscripción [del administrador de dispositivos Android](/intune/enrollment/android-enroll-device-administrator).
1. Asignar licencias a los usuarios. 
 
   Los usuarios Teams dispositivos que se inscriban en Intune deben tener asignada una licencia válida de Intune. Para obtener más información, vea [Asignar licencias a los usuarios para que puedan inscribir dispositivos en Intune](/intune/fundamentals/licenses-assign).
1. Asignar directivas de cumplimiento del administrador de dispositivos.  

   1. Crear una directiva de cumplimiento del administrador de dispositivos Android.

   1. Asígnelo al grupo Azure Active Directory que contiene los usuarios que iniciarán sesión en los Teams dispositivos. Vea [Usar directivas de cumplimiento para establecer reglas para los dispositivos que administra con Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Vea también

[Teléfonos para Teams](phones-for-teams.md)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)

[Teams pantallas](teams-displays.md)

[Administrar los dispositivos en Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
