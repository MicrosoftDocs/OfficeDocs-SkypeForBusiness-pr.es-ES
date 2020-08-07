---
title: Teléfonos para Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: En este artículo se describe la lista de teléfonos que están certificados para Microsoft Teams y las características compatibles con los teléfonos certificados para Microsoft Teams.
ms.openlocfilehash: b017e02b2d3d2bdc6b01886929d034abb6650384
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583959"
---
# <a name="phones-for-microsoft-teams"></a>Teléfonos para Microsoft Teams

Microsoft Teams es compatible con una cartera de teléfonos de escritorio para usuarios que requieren una experiencia de teléfono tradicional. Este artículo proporciona una descripción completa de los teléfonos de los equipos y puede ayudarle a planear, entregar y administrar teléfonos de Microsoft Teams como parte de su solución de sistema de Microsoft Phone. 

Para ofrecer una experiencia de alta calidad y confiable de Microsoft Teams en teléfonos, estamos asociados y trabajando activamente con Yealink, Crestron, Lenovo, Polycom y AudioCodes con el fin de desarrollar y certificar una amplia cartera de teléfonos de escritorio y dispositivos de audio de sala de conferencias. Para obtener la información más reciente y actualizada sobre los dispositivos de Teams, vaya a [Teams Marketplace](https://office.com/teamsdevices).

## <a name="features-supported-by-teams-phones"></a>Características admitidas por teléfonos de Teams
Los teléfonos certificados por Teams tienen una amplia variedad de características para ayudar a los usuarios a realizar sus trabajos y ayudarle a administrar su uso. Este es un resumen de las características disponibles en los teléfonos certificados por Teams:

- **Autenticación** Los teléfonos usan la autenticación moderna para simplificar el inicio de sesión y mejorar la seguridad. Los usuarios pueden iniciar sesión escribiendo su nombre de usuario y contraseña en el teléfono o iniciando sesión desde otro dispositivo como PC/smartphone.
- **Historial de llamadas y marcación rápida** Los usuarios tienen acceso rápido a sus contactos, el historial de llamadas y el buzón de voz. Pueden administrar fácilmente sus contactos y entradas de marcación con rapidez directamente desde su teléfono.
- **Reuniones y llamadas** Los usuarios pueden ver sus programaciones y unirse fácilmente a las reuniones con Teams JOIN en un solo toque.
- **Grupos de llamadas** Los agentes de telefonía que participan en los grupos de llamadas pueden administrar fácilmente su disponibilidad y aceptar o rechazar llamadas entrantes de la cola de llamadas.
- **Delegación de usuarios** Los asistentes ejecutivos y los administradores pueden administrar los teléfonos de sus ejecutivos y interceptar las llamadas entrantes; hacer llamadas en nombre del Ejecutivo; toma el control de las llamadas que el Ejecutivo ha puesto en espera. y supervisa si el Ejecutivo está en una llamada, en espera, etc.
- **Entrada de lápiz en caliente** Los usuarios pueden obtener sus contactos, reuniones y otras preferencias, simplemente iniciando sesión en un teléfono. Cuando haya terminado, podrán cerrar sesión y dejar el teléfono listo para el siguiente usuario.
- **Vídeo** Los teléfonos con soporte de video permiten a los usuarios unirse a llamadas y videoconferencias como si estuvieran en sus equipos. Los usuarios pueden mantener su privacidad usando el interruptor de la cámara del teléfono y el interruptor de silenciar el micrófono cuando estén disponibles.
- **Mejor juntos** Los teléfonos pueden bloquear y desbloquear de manera integrada cuando se conectan a su PC con Windows, con un cliente de escritorio de 64 bits.
- **Accesibilidad** Los teléfonos tienen varias características de accesibilidad, como el texto de alto contraste, para que cualquier persona pueda usarlos más fácilmente.
- **Soporte de E911 dinámico y mejorado** Los usuarios con sesión iniciada que llaman a 911 verán su ubicación en el teléfono. 
    > [!IMPORTANT]
    > Si un teléfono no ha iniciado sesión, o si no tiene una conexión a Internet, no se pueden hacer llamadas de 911. Si esto sucede, se muestra una notificación en el teléfono.

Además de las características anteriores, puede controlar qué capacidades están disponibles según el tipo de licencia y la Directiva de teléfono asignadas al usuario que inicia sesión en el teléfono. Por ejemplo, los usuarios que inicien sesión en un teléfono con sus cuentas personales pueden acceder a la gama completa de características: llamadas, reuniones, buzón de voz, etc. Las cuentas a las que se ha asignado una licencia telefónica común que inician sesión en un teléfono, no obstante, solo pueden obtener acceso a una variedad de características limitadas; el historial de llamadas y las programaciones de reuniones no se pueden conservar, por ejemplo, para proteger la privacidad de los usuarios.

## <a name="required-licenses"></a>Licencias necesarias

Las licencias de Microsoft Teams se pueden comprar como parte de sus [suscripciones a microsoft 365 y Office 365](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description). Para obtener más información sobre las licencias necesarias para usar Microsoft Teams en teléfonos, consulte [licencias de sistema telefónicas](https://products.office.com/microsoft-teams/voice-calling)disponibles.

Para obtener más información sobre la obtención de equipos, consulte [¿Cómo puedo obtener acceso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-your-phones-via-intune"></a>Implementa tus teléfonos a través de Intune

### <a name="conditional-access"></a>Acceso condicional

El acceso condicional es una característica de Azure Active Directory que le ayuda a garantizar que los dispositivos que tengan acceso a los recursos de Office 365 estén administrados correctamente y sean seguros.  Si aplica directivas de acceso condicional al servicio de Teams, los dispositivos con Android (incluido un teléfono de Teams) que tengan acceso a teams deben estar inscritos en Intune y su configuración debe cumplir sus directivas.  Si el dispositivo no se ha inscrito en Intune o si está inscrito pero su configuración no cumple con las directivas, el acceso condicional evitará que un usuario inicie sesión en el dispositivo o use la aplicación de Teams.

Normalmente, las directivas de cumplimiento definidas en Intune se asignan a grupos de usuarios.  Esto significa que si asigna una directiva de cumplimiento de Android a user@contoso.com, esa Directiva se aplicará por igual a su smartphone Android y a cualquier dispositivo de Teams basado en Android en el que se inicie sesión user@contoso.com.

Si usa el acceso condicional, que requiere que se exija la inscripción de Intune, en su organización, hay un par de cosas que debe configurar para permitir una inscripción correcta de Intune:

- **Licencia de Intune** El usuario que inicia sesión en Microsoft Teams Phone debe tener una licencia para Intune.  Siempre y cuando los teléfonos de Microsoft Teams estén iniciados en una cuenta de usuario que tenga una licencia válida de Intune, el teléfono se inscribirá automáticamente en Microsoft Intune como parte del proceso de inicio de sesión.
- **Configurar Intune** Debe tener configurado un inquilino de Intune configurado correctamente para la inscripción de administrador de dispositivos Android.

### <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar Intune para inscribir dispositivos basados en Android

Los dispositivos basados en Android se administran en Intune a través de administración de administrador de dispositivos de Android (DA). Antes de que los dispositivos puedan ser inscritos en Intune, hay que realizar algunos pasos básicos.  Si ya está administrando dispositivos con Intune hoy, probablemente ya haya realizado todas estas acciones.  De lo contrario, esto es lo que debe hacer:

1. Establezca la autoridad de MDM (administración de dispositivos móviles) de Intune.  Si nunca ha usado Intune antes, debe configurar la autoridad de MDM antes de poder inscribir dispositivos. Para obtener más información, vea [establecer la entidad de administración de dispositivos móviles](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Este es un paso que debe realizarse una sola vez al crear un nuevo inquilino de Intune.
2. Habilitar la inscripción de administrador de dispositivos Android. Los dispositivos de equipos basados en Android se administran como dispositivos de administrador de dispositivos con Intune.  La inscripción de administrador de dispositivos está desactivada de forma predeterminada para los inquilinos recién creados.  Para obtener más información, consulte inscripción en el [Administrador de dispositivos Android](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Asignar licencias a los usuarios. Los usuarios de los dispositivos de equipos que se inscriban en Intune deben tener asignada una licencia válida de Intune. Para obtener más información, vea [asignar licencias a los usuarios para que puedan inscribir dispositivos en Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Asignar directivas de cumplimiento para el administrador del dispositivo.  Crear una directiva de cumplimiento de administrador de dispositivos de Android y asignarla al grupo de Azure Active Directory que contenga los usuarios que iniciarán sesión en los dispositivos de Teams. Para obtener más información, consulte [usar directivas de cumplimiento para establecer reglas para los dispositivos que administra con Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="manage-your-phones"></a>Administrar los teléfonos

Un administrador de inquilinos puede administrar y mantener actualizados todos los dispositivos de su equipo a través del centro de administración de Teams. Para obtener más información, consulte [administrar los dispositivos en Microsoft Teams](https://docs.microsoft.com/microsoftteams/devices/device-management). 

## <a name="see-also"></a>Vea también

[Marketplace de equipos](https://office.com/teamsdevices)

[Teléfonos IP certificados para Microsoft Teams](teams-ip-phones.md)
