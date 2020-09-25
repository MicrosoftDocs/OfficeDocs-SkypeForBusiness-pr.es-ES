---
title: Iniciar sesión en Microsoft Teams con la autenticación moderna
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: Información sobre cómo funciona la autenticación moderna, cómo cambiar de cuenta y cómo solucionar problemas con la autenticación moderna. Incluye cómo indicar a Teams que ignore el rellenado previo del nombre de usuario (UPN) en el inicio de sesión.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02c5889752ca730de84f8ca7bbaf240d30df63a2
ms.sourcegitcommit: 70ceb3a3c3483234ec9f3fed6117144abf59ca75
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "48246137"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Iniciar sesión en Microsoft Teams con la autenticación moderna
==========================

Microsoft recomienda que las organizaciones usen las versiones más recientes de Windows 10 con una configuración de Hybrid Domain Join o Azure AD Join. Usar las últimas versiones garantiza que las cuentas de los usuarios estén desbloqueadas en el Administrador de cuentas web de Windows, el cual, a su vez, activará el inicio de sesión único para Teams y para otras aplicaciones de Microsoft. El inicio de sesión único ofrece una mejor experiencia de usuario (inicio de sesión silencioso) y una mejor posición de seguridad.

Microsoft Teams usa la autenticación moderna para mantener la experiencia de inicio de sesión sencilla y segura. Para ver cómo inician sesión en Teams los usuarios, consulte [Iniciar sesión en Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Cómo funciona la autenticación moderna

La autenticación moderna es un proceso que permite a Teams saber si un usuario ya ingresó sus credenciales (como su correo electrónico y contraseña de trabajo) en otro lugar, por lo que no es necesario volver a escribirlos para iniciar la aplicación. La experiencia variará de acuerdo con un par de factores, como si los usuarios están trabajando en Windows o en Mac. También puede variar en función de si la organización tiene habilitada la autenticación de un solo factor o la autenticación multifactor. Generalmente, la autenticación multifactor requiere comprobar las credenciales a través de un teléfono, proporcionar un código único, escribir un PIN o presentar una huella digital. Este es un resumen de cada escenario de autenticación moderna.

### <a name="windows-users"></a>Usuarios de Windows

- Si los usuarios ya han iniciado sesión en Windows o en otras aplicaciones de Office con su cuenta profesional o educativa, cuando inicien Teams, se les dirigirá directamente a la aplicación. No es necesario que introduzcan sus credenciales.

- Microsoft recomienda usar la versión 1903 o posterior de Windows 10 para disfrutar de la mejor experiencia de inicio de sesión único.

- Si los usuarios no han iniciado sesión en su cuenta profesional o educativa de Microsoft en ningún otro lugar, cuando inicien Teams, se les pedirá que proporcionen la autenticación multifactor o de un solo factor (MFA o SFA). Este proceso depende de los requerimientos que su organización haya decidido establecer para el procedimiento de inicio de sesión.

- Si los usuarios inician sesión en un equipo unido a un dominio, cuando inicien Teams, es posible que se le pida que realicen un paso de autenticación más, en función de si la organización decidió requerir MFA o si el equipo ya requiere MFA para iniciar sesión. Si su equipo ya requiere MFA para iniciar sesión, cuando abran Teams, la aplicación se iniciará automáticamente.

- En equipos unidos a un dominio, cuando el SSO no es posible, Teams puede rellenar previamente la pantalla de inicio de sesión con el nombre de usuario principal (UPN). Hay casos en los que es posible que no quiera esto, especialmente si su organización usa diferentes UPN locales y en Azure Active Directory. Si ese es el caso, puede usar la siguiente clave del registro de Windows para desactivar el rellenado previo del UPN:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > La opción para omitir o ignorar el rellenado previo para los nombres de usuario que terminan en ".local" o ".corp" está activada de forma predeterminada, por lo que no es necesario establecer una clave del registro para desactivarlos.

### <a name="mac-users"></a>Usuarios de Mac

En MacOS, Teams solicitará a los usuarios que escriban su nombre de usuario y credenciales, y también podría pedir una autenticación multifactor en función de la configuración de su organización. Una vez que los usuarios escriben sus credenciales, no se les pedirá que las proporcionen nuevamente. A partir de ese momento, Teams se inicia automáticamente siempre y cuando estén trabajando en el mismo equipo.

## <a name="teams-for-ios-and-android-users"></a>Teams para usuarios de iOS y Android

Al iniciar sesión, los usuarios de dispositivos móviles verán una lista de todas las cuentas de Microsoft 365 que tengan la sesión actualmente iniciada o que hayan iniciado sesión anteriormente en su dispositivo. Los usuarios pueden pulsar en cualquiera de las cuentas para iniciar sesión. Hay dos escenarios para el inicio de sesión en un dispositivo móvil:

1. Si la cuenta seleccionada está actualmente conectada a otras aplicaciones de Office 365 o Microsoft 365, entonces el usuario será llevado directamente a Teams. No es necesario que el usuario introduzca sus credenciales.

2. Si el usuario no ha iniciado sesión en su cuenta de Microsoft 365 en ningún otro lugar, se le pedirá que proporcione una autenticación de factor único o una autenticación multifactor (SFA o MFA), dependiendo de las directivas de inicio de sesión desde un dispositivo móvil configuradas para la organización.

> [!NOTE]
> Para que los usuarios puedan experimentar la experiencia de inicio de sesión tal y como se describe en esta sección, sus dispositivos deben ejecutar Teams para iOS, versión 2.0.13 (compilación 2020061704) o posterior, o bien Teams para Android, versión 1416/1.0.0.2020061702 o posterior.

### <a name="adding-multiple-accounts-to-teams"></a>Agregar varias cuentas a Teams

Teams para iOS y Android admite la adición de varias cuentas de un solo dispositivo a Teams. Las siguientes imágenes muestran cómo los usuarios pueden agregar varias cuentas en Teams.

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Agregando varias cuentas en Teams":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a>Utilizar la administración de la movilidad de la empresa para controlar qué cuentas pueden acceder a Teams

Teams para iOS y Android ofrece a los administradores de IT la posibilidad de enviar las configuraciones de las cuentas a las cuentas de Microsoft 365. Esta capacidad funciona con cualquier proveedor de Administración de dispositivos móviles (MDM) que utilice el canal de  [Configuración de aplicaciones administradas](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) para iOS o el canal [ Android Enterprise](https://developer.android.com/work/managed-configurations)  para Android.

Para los usuarios inscritos en Microsoft Intune, puede desplegar los ajustes de configuración de la cuenta utilizando Intune en el Portal Azure.

Una vez que se ha configurado la cuenta en el proveedor MDM y después de que el usuario inscriba su dispositivo, en la página de inicio de sesión, Teams para iOS y Android solo mostrará la(s) cuenta(s) permitida(s) en la página de inicio de sesión de Teams. El usuario puede acceder a cualquiera de las cuentas permitidas en esta página para iniciar sesión.

Establezca los siguientes parámetros de configuración en el portal de Azure Intune para los dispositivos administrados.

|Plataforma |Clave  |Valor  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **Habilitado**: la única cuenta permitida es la cuenta de usuario administrada definida por la clave IntuneMAMUPN.<br> **Deshabilitado** (o cualquier valor que no sea una coincidencia insensible a las mayúsculas y minúsculas con **Habilitado**): cualquier cuenta está permitida.        |
|iOS     |   **IntuneMAMUPN**      |   UPN de la cuenta permitida para acceder a Teams.<br> En el caso de los dispositivos inscritos en Intune, se puede utilizar el símbolo {{nombre del usuario principal}} para representar la cuenta de usuario inscrito.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    Sólo se permiten las cuentas de usuario administradas definidas por esta clave.<br> Uno o más punto y coma [;] - UPN delimitados.<br> En el caso de los dispositivos inscritos en Intune, se puede utilizar el símbolo {{nombre del usuario principal}} para representar la cuenta de usuario inscrito.

Una vez que se haya establecido la configuración de la cuenta, Teams restringirá la posibilidad de iniciar sesión, de modo que sólo se concederá acceso a las cuentas permitidas en los dispositivos inscritos.

Para crear una directiva de configuración de aplicaciones para dispositivos iOS/iPadOS administrados, consulte  [Agregar directivas de configuración de aplicaciones para dispositivos iOS/iPadOS administrados](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).

Para crear una directiva de configuración de aplicaciones para dispositivos android administrados, consulte  [Agregar directivas de configuración de aplicaciones para dispositivos android administrados ](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).

## <a name="switching-accounts-after-completing-modern-authentication"></a>Cambiar de cuentas después de completar la autenticación moderna

Si los usuarios trabajan en un equipo unido a un dominio (por ejemplo, si su espacio empresarial ha habilitado Kerberos), no podrán cambiar de cuenta de usuario una vez hayan completado la autenticación moderna. Si los usuarios no están trabajando en un equipo unido a un dominio, podrán cambiar de cuenta.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Cerrar la sesión de Teams una vez completada la autenticación moderna

Para cerrar la sesión de Teams, los usuarios pueden hacer clic en su imagen de perfil en la parte superior de la aplicación y seleccionar **Cerrar sesión**. También pueden hacer clic con el botón derecho en el icono de la aplicación en la barra de tareas y seleccionar **Cerrar sesión**. Una vez que haya finalizado la sesión en Teams, deberán volver a escribir sus credenciales para iniciar la aplicación.

### <a name="signing-out-of-teams-for-ios-and-android"></a>Cerrando sesión en Teams para iOS y Android

Los usuarios de dispositivos móviles pueden cerrar sesión en Teams dirigiéndose al menú y eligiendo el menú **Más**, para luego elegir **Cerrar sesión**. Una vez que se hayan cerrado sesión, los usuarios deberán volver a introducir sus credenciales la próxima vez que inicien la aplicación.

> [!NOTE]
> Teams para Android utiliza el inicio de sesión único (SSO) para simplificar la experiencia de inicio de sesión. Los usuarios deben asegurarse de cerrar la sesión de **todas** las aplicaciones de Microsoft, además de Teams, para poder cerrar la sesión completamente en la plataforma Android.

## <a name="global-sign-in-and-sign-out"></a>Inicio y cierre de sesión global

La aplicación para Android de Teams ahora es compatible con el inicio y el cierre de sesión global para ofrecer una experiencia de inicio y cierre de sesión libre de complicaciones para los trabajadores primera línea. Los empleados pueden elegir un dispositivo del grupo de dispositivos compartidos y realizar un inicio de sesión único para "hacerlo suyo" por la duración del turno. Al final de su turno, deben poder cerrar sesión de forma global en el dispositivo. Este proceso quita toda su información personal y de la compañía del dispositivo para que pueda devolverlo al grupo de dispositivos. Para obtener esta funcionalidad, el dispositivo debe estar en modo compartido. Para obtener información sobre cómo configurar un dispositivo compartido, consulte [Cómo usar un modo de dispositivo compartido en Android](https://docs.microsoft.com/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

La experiencia de inicio de sesión tiene un aspecto similar al de la experiencia de inicio de sesión estándar de Teams, mientras que el cierre de sesión tendrá un aspecto parecido al de las dos imágenes siguientes:

![se muestra el teléfono móvil con cierre de sesión](media/global-SignOut.png)  

## <a name="urls-and-ip-address-ranges"></a>Intervalos de direcciones IP y URL

Teams requiere conectividad a Internet. Para comprender los puntos de conexión que deben ser accesibles para los clientes que usan Teams en los planes de Office 365, gobierno y otras nubes, consulte [Intervalos de la dirección IP y URL de Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> En la actualidad, Teams necesita acceso (puerto TCP 443) al servicio de Google ssl.gstatic.com (<https://ssl.gstatic.com)> para todos los usuarios, esto sucede aunque no esté usando Gstatic. Teams quitará este requisito pronto (principios de 2020), y actualizaremos este artículo en consecuencia en ese momento.

## <a name="troubleshooting-modern-authentication"></a>Solución de problemas de la autenticación moderna

La autenticación moderna está disponible para cualquier organización que use Teams. Si los usuarios no pueden completar el proceso, es posible que se haya producido algún error en el dominio o en la cuenta profesional o educativa de Microsoft de su organización.

Para obtener más información, consulte [¿por qué tengo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
