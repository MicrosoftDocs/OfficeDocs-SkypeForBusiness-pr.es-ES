---
title: Configurar los teléfonos de área común para Microsoft Teams
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
- admindeeplinkMAC
- admindeeplinkTEAMS
description: Aprenda a configurar teléfonos de área común para vestíbulos, áreas de recepción y salas de conferencias.
ms.openlocfilehash: 06005f853ac125478ae1fd99dba2d022c5eb0100
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392160"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>Configurar teléfonos de área común para Microsoft Teams

Un teléfono de área común normalmente se coloca en un área como un vestíbulo u otra área que está disponible para muchas personas para realizar una llamada: una zona de recepción, sala de espera o teléfono de conferencias. Los teléfonos de área común han iniciado sesión con cuentas vinculadas a una licencia **de dispositivos compartidos de Microsoft Teams**.

En este artículo se ofrece información general sobre cómo implementar y configurar los dispositivos de teléfono de Teams como teléfonos de área comunes para espacios compartidos. Para obtener una experiencia de sala de reuniones más completa, incluida la audioconferencia, considere la posibilidad de comprar una licencia **de Salas de Teams** dedicada con un dispositivo Salas de Teams en su lugar. Para obtener más información sobre Salas de Teams, vea [Salas de Microsoft Teams](rooms/index.md).

> [!NOTE]
> Las cuentas de teléfonos de área común los objetos creados en Skype Empresarial Server no se pueden migrar a Microsoft Teams. Siga los pasos de este artículo para volver a crear esas cuentas para Teams y, si es necesario, migrar la conectividad de la red telefónica conmutada (RTC).

## <a name="step-1---buy-the-licenses"></a>Paso 1: comprar las licencias

En primer lugar, debe comprar una licencia **de Dispositivos compartidos de Teams** y asegurarse de que tiene un teléfono certificado. Para buscar y obtener más información sobre los teléfonos certificados, vaya a [Microsoft dispositivos de Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. En la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), ve a **Servicios** **de compra de facturación** > .

2. Si la sección **Ver por categoría** aún no se muestra, vaya a **Comprar desde Microsoft** y seleccione **Ver productos**. A continuación, seleccione **Colaboración y comunicación**.  

3. En la lista de productos, busque **Microsoft Dispositivos compartidos de Teams** y seleccione **Detalles**.

4. Escriba el número de licencias que necesita y seleccione **Comprar**.

> [!NOTE]
> Si usa Intune en su entorno y tiene reglas de acceso condicional que requieren el cumplimiento del dispositivo, tendrá que asignar una **Azure Active Directory Premium Plan 1** y **Intune** licencia a la cuenta de dispositivo para el teléfono de área común.
>
> Los teléfonos de área comunes pueden verse afectados por reglas de acceso condicional y otras configuraciones de identidad, como la autenticación multifactor. Consulte [Procedimientos recomendados de autenticación para dispositivos Android de Teams](devices/authentication-best-practices-for-android-devices.md) para obtener más información.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Paso 2: Crear una nueva cuenta de usuario y asignar licencias

### <a name="using-the-microsoft-365-admin-center"></a>Usar el Centro de administración de Microsoft 365

Si va a implementar más de un teléfono de área común a la vez, obtenga información sobre cómo crear cuentas y asignar licencias [con PowerShell](#using-powershell).

Si vas a implementar un dispositivo:

1. En la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), vaya a **Usuarios** > **activos** > **Agregar un usuario**.

2. Escriba un nombre de usuario como `Main` el nombre y `Reception` el segundo nombre.

3. Escriba un nombre para mostrar si no genera automáticamente uno como `Main Reception`.

4. Escriba un nombre de usuario como `MainReception` o `Mainlobby`.

5. Establece manualmente la contraseña de tu teléfono de área común. Para establecer la contraseña, desactive **Crear automáticamente una contraseña** y **requerir que este usuario cambie su contraseña la primera vez que inicie sesión**.  

    > [!IMPORTANT]
    > Es muy recomendable establecer manualmente una contraseña para teléfonos de área común para evitar problemas de inicio de sesión para los usuarios finales.

6. Seleccione la ubicación de uso del dispositivo y asigne la licencia **Dispositivos compartidos de Teams** a la cuenta. Si se necesitan otras licencias, como Planes de llamadas, asígnelas.

> [!NOTE]
> No es necesario agregar una licencia con las características del sistema telefónico. Se incluye con la licencia **de Dispositivos compartidos de Teams** .
>
> Si no está usando Microsoft Sistema telefónico con enrutamiento directo o Conexión de operadores, es posible que desee agregar licencias de **planes de llamadas**. Para obtener más información sobre las licencias, consulte [Microsoft licencias complementarias de Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Con PowerShell

Use PowerShell cuando desee crear y asignar licencias para más de una cuenta de usuario a la vez. Para obtener más información, vea [Crear cuentas de usuario de Microsoft 365 con PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) y [Asignar licencias de Microsoft 365 a cuentas de usuario con PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

## <a name="step-3---set-policies-for-common-area-phones"></a>Paso 3: Establecer directivas para teléfonos de área comunes

Use directivas para controlar qué características están disponibles para los usuarios en teléfonos de área común.

### <a name="ip-phone-policies"></a>Directivas de teléfonos IP

La directiva de teléfono IP de Teams solo se puede modificar si la cuenta que inicia sesión en el teléfono tiene una licencia distinta de una licencia **de Dispositivos compartidos de Teams** .  Si tiene una licencia con una suscripción de Microsoft 365 E3 o E5, o una suscripción a Office 365 Enterprise E1, E3 o E5, puede modificar la directiva de teléfono IP.  Si usas una licencia **de Salas de Teams** en tu cuenta de teléfono de área común, solo podrás usar `MeetingRoomSignIn` el modo. `MeetingRoomSignIn` no está disponible en la mayoría de los teléfonos de área comunes. Para obtener más información sobre las invalidaciones admitidas para la interfaz del teléfono, vea [Establecer Microsoft interfaz de usuario de dispositivos Android de Teams](/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection).

Con la directiva Teléfono IP de Teams, establezca el [parámetro SignInMode](/powershell/module/skype/new-csteamsipphonepolicy#parameters) para `CommonAreaPhoneSignIn` habilitar la experiencia de teléfono de área común en el dispositivo telefónico de Teams.

Para configurar otros parámetros, considere la posibilidad de crear una [directiva de teléfono IP](/powershell/module/skype/new-csteamsipphonepolicy). Por ejemplo, si un teléfono de área común se usa en un área pública, establezca una directiva de teléfono IP para restringir la búsqueda en la Libreta global de direcciones de su organización y bloquear el servicio de escritorio rápido. Para obtener más información, consulte [Establecer la interfaz de usuario de los dispositivos Android de Teams](/microsoftteams/devices/Teams-Android-devices-user-interface).

### <a name="calling-policies"></a>Directivas de llamada

Use directivas de llamada para habilitar llamadas privadas, mediante desvío de llamadas o llamadas simultáneas en teléfonos de área común. Para obtener más información, consulte [Llamadas y desvío de llamadas en Teams](teams-calling-policy.md).

De forma predeterminada, el parque de llamadas no está habilitado para los teléfonos de área común. Deberá crear una directiva para habilitarla. Para obtener más información, consulte [Estacionar llamadas y recuperar llamadas en Microsoft Teams](call-park-and-retrieve.md).

> [!NOTE]
> Después de asignar una directiva, cierra sesión en el teléfono y vuelve a iniciarla. Una asignación de directiva puede tardar hasta una hora en surtir efecto.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Paso 4: Adquirir y asignar números de teléfono

Consulte [Administrar los números de teléfono de su organización para](manage-phone-numbers-landing-page.md) obtener información sobre cómo adquirir y asignar números de teléfono en función de la opción de conectividad con RTC.

## <a name="step-5---sign-in"></a>Paso 5: Iniciar sesión

Después de crear y configurar una cuenta de usuario, puedes iniciar sesión en un teléfono. En función del número de teléfonos que implemente, tiene tres opciones de inicio de sesión:

- [Inicio de sesión local](#local-sign-in).
- [Inicia sesión desde otro dispositivo](#sign-in-from-another-device).
- [Inicie sesión con el Centro de administración de Teams](#sign-in-using-the-teams-admin-center).

### <a name="local-sign-in"></a>Inicio de sesión local

Para iniciar sesión localmente con un nombre de usuario y contraseña:

1. Enciende el teléfono del área común.
2. Selecciona **Iniciar sesión en este dispositivo**.
3. Sigue las instrucciones de inicio de sesión en el dispositivo. Una vez que haya iniciado sesión, el teléfono mostrará la experiencia de usuario del teléfono de área común.

> [!NOTE]
> Si usa una directiva de configuración personalizada que desancla la aplicación de llamadas, el teclado de marcado no aparece en el teléfono del área común. Para obtener más información sobre las directivas de configuración de Teams, vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams](teams-app-setup-policies.md).

### <a name="sign-in-from-another-device"></a>Iniciar sesión desde otro dispositivo

También puedes iniciar sesión en un teléfono de área común desde otro dispositivo mediante un código. Cuando inicies sesión de esta manera, deberás introducir el nombre de usuario y la contraseña en otro dispositivo, en lugar de en el teléfono en sí.

1. En el teléfono del área común, busca el código que se muestra en la pantalla de inicio de sesión.
2. En otro dispositivo, ve a [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin).
3. Escribe el código y sigue las instrucciones para completar el inicio de sesión.

### <a name="sign-in-using-the-teams-admin-center"></a>Iniciar sesión con el Centro de administración de Teams

Como administrador, puede aprovisionar e iniciar sesión de forma remota en teléfonos de área común desde el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851). Este método es el método de inicio de sesión más eficaz al implementar un gran número de teléfonos a la vez. Consulte [Aprovisionamiento remoto e inicie sesión en dispositivos Android de Teams para](devices/remote-provision-remote-login.md) obtener más información.

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>Paso 6: Configurar las llamadas avanzadas en teléfonos de área común (opcional)

De forma predeterminada, la experiencia de llamadas básicas estará en la pantalla principal del teléfono del área común, pero puede activar una experiencia de llamada avanzada.

Las siguientes características de llamadas avanzadas están disponibles para los modelos de dispositivos de teléfono de Teams compatibles con una licencia de **Dispositivos compartidos de Teams** y las últimas actualizaciones de Teams (versión mínima: 1449/1.0.94.2022061702):

- [Estacionar llamadas y recuperar.](call-park-and-retrieve.md)
- [Correo de voz basado en la nube a través de Exchange Online Plan 2](set-up-phone-system-voicemail.md).
  - Para deshabilitar el correo de voz basado en la nube, consulte [Configuración de usuario del correo de voz con PowerShell](/powershell/module/skype/set-csonlinevoicemailusersettings).
- [Colas de llamadas](create-a-phone-system-call-queue.md).
- [Operadores automáticos](create-a-phone-system-auto-attendant.md).
- [Recogida de llamadas grupales](call-sharing-and-group-call-pickup.md).
- [Reglas de reenvío](teams-calling-policy.md).

Para usar estas características de llamada avanzadas en modelos de dispositivos de teléfono de Teams compatibles, puede activar el botón de alternancia **Llamada avanzada** en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) o en el dispositivo de teléfono de Teams que haya iniciado sesión en su cuenta de Dispositivos compartidos de Teams.

La activación de las funcionalidades de llamadas avanzadas requiere que compre modelos de hardware que puedan admitir todas las capacidades necesarias.

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>Activar las llamadas avanzadas en el Centro de administración de Teams

1. Inicie sesión en el [Centro de administración de Teams](https://admin.teams.microsoft.com/dashboard) con una cuenta de administrador de Microsoft 365.
1. En el menú de la izquierda, vaya a **Teléfonos** de **dispositivos** >  de Teams > y seleccione la pestaña **Perfiles de configuración**.
1. En la lista, seleccione el perfil de configuración asignado a su teléfono de área común.
1. En la sección **Configuración de llamadas** , busque el botón de alternancia **Llamada avanzada** .
1. Activa el botón de alternancia.
1. En la parte inferior de la página, seleccione el botón **Guardar** .

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>Activar las llamadas avanzadas desde un dispositivo de teléfono de Teams

1. Después de iniciar sesión en su dispositivo de teléfono de Teams, vaya a **Configuración** > **del dispositivo** >  **Administración solo** > **Llamadas**.
1. Busque el botón de alternancia **Llamada avanzada** y actíbalo.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha configurado e iniciado sesión en teléfonos de área común para su organización, puede administrarlos en el Centro de administración de Teams. Consulte [Microsoft Teams: Administrar los dispositivos](devices/device-management.md) para obtener más información.

## <a name="related-articles"></a>Artículos relacionados

- [Actualice Microsoft dispositivos de Teams de forma remota](devices/remote-update.md).
- [Administrar Microsoft etiquetas de dispositivo de Teams](devices/manage-device-tags.md).
- [Microsoft supervisión del estado del dispositivo de Teams](alerts/device-health-status.md).
