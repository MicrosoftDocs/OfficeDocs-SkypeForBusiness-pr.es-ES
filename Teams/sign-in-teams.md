---
title: Iniciar sesión en Microsoft Teams con la autenticación moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Información sobre cómo funciona la autenticación moderna, cómo cambiar de cuenta y cómo solucionar problemas con la autenticación moderna. Incluye cómo indicar a Teams que ignore el rellenado del nombre del usuario (UPN) en el inicio de sesión.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32e231fbcef2991e13ec5b496e6ed61eb677ee20
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665762"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Iniciar sesión en Microsoft Teams con la autenticación moderna
==========================

Microsoft recomienda que las organizaciones usen las versiones más recientes de Windows 10 con una configuración de Hybrid Domain Join o Azure AD Join. Así se asegura de que las cuentas de los usuarios se encuentren en el administrador de cuentas web de Windows, que, a su vez, activará el inicio de sesión único para Teams y otras aplicaciones de Microsoft. Esto ofrece una mejor experiencia de usuario (inicio de sesión silencioso) y una mejor postura de seguridad.

Microsoft Teams usa la autenticación moderna para mantener la experiencia de inicio de sesión sencilla y segura. Para ver cómo inician sesión en Teams los usuarios, consulte [Iniciar sesión en Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Cómo funciona la autenticación moderna

La autenticación moderna es un proceso que permite que Teams sepa que los usuarios ya escribieron sus credenciales (como el correo electrónico y la contraseña del trabajo) en otro lugar, por lo que no es necesario volver a escribirlos para iniciar la aplicación. La experiencia variará según un par de factores, como si los usuarios están trabajando en Windows o en un equipo Mac. También puede variar en función de si la organización tiene habilitada la autenticación de un solo factor o la autenticación multifactor (por lo general, la autenticación multifactor requiere comprobar las credenciales a través de un teléfono, proporcionar un código único, escribir un PIN o presentar una huella digital). Este es un resumen de cada escenario de autenticación moderna.

### <a name="windows-users"></a>Usuarios de Windows

- Si los usuarios ya han iniciado sesión en Windows o en otras aplicaciones de Office con su cuenta profesional o educativa, cuando inicien Teams, se les dirigirá directamente a la aplicación. No es necesario que introduzcan sus credenciales.

- Microsoft recomienda usar la versión 1903 o posterior de Windows 10 para disfrutar de la mejor experiencia de inicio de sesión único.

- Si los usuarios no han iniciado sesión en su cuenta profesional o educativa de Microsoft en ningún otro lugar, cuando inicien Teams, se les pedirá que proporcionen la autenticación multifactor o de un solo factor (SFA o MFA), en función de lo que la organización haya decidido.

- Si los usuarios inician sesión en un equipo unido a un dominio, cuando inicien Teams, es posible que se le pida que realicen un paso de autenticación más, en función de si la organización decidió requerir MFA o si el equipo ya requiere MFA para iniciar sesión. Si su equipo ya requiere MFA para iniciar sesión, cuando abran Teams, la aplicación se iniciará automáticamente.

- En equipos unidos a un dominio, cuando el SSO no es posible, Teams puede rellenar previamente la pantalla de inicio de sesión con el nombre de usuario principal (UPN). Hay casos en los que es posible que no quiera esto, especialmente si su organización usa diferentes UPN locales y en Azure Active Directory. Si ese es el caso, puede usar la siguiente clave del registro de Windows para desactivar el rellenado previo del UPN:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > La opción para omitir o ignorar el rellenado previo para los nombres de usuario que terminan en ".local" o ".corp" está activada de forma predeterminada, por lo que no es necesario establecer una clave del registro para desactivarlos.


### <a name="mac-users"></a>Usuarios de Mac

En MacOS, Teams solicitará a los usuarios que escriban el nombre de usuario y las credenciales y puede pedir la autenticación multifactor en función de la configuración de su organización. Una vez que los usuarios escriben sus credenciales, no se les pedirá que las proporcionen nuevamente. A partir de ese momento, Teams se inicia automáticamente siempre y cuando estén trabajando en el mismo equipo.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Cambiar de cuentas después de completar la autenticación moderna

Si los usuarios trabajan en un equipo unido a un dominio (por ejemplo, si su espacio empresarial ha habilitado Kerberos), no podrán cambiar de cuenta de usuario una vez hayan completado la autenticación moderna. Si los usuarios no están trabajando en un equipo unido a un dominio, podrán cambiar de cuenta.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Cerrar la sesión de Teams una vez completada la autenticación moderna

Para cerrar la sesión de Teams, los usuarios pueden hacer clic en su imagen de perfil en la parte superior de la aplicación y seleccionar **Cerrar sesión**. También pueden hacer clic con el botón derecho en el icono de la aplicación en la barra de tareas y seleccionar **Cerrar sesión**. Una vez que haya finalizado la sesión en Teams, deberán volver a escribir sus credenciales para iniciar la aplicación.

## <a name="urls-and-ip-address-ranges"></a>Intervalos de direcciones IP y URL

Teams requiere conectividad a Internet. Para saber qué puntos de conexión deben ser accesibles para los clientes que usan Teams en planes de Microsoft 365 u Office 365, así como en la nube de la administración pública y otras nubes, lea [Intervalos de direcciones IP y URL de Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> En la actualidad, Teams necesita acceso (puerto TCP 443) al servicio de Google ssl.gstatic.com (<https://ssl.gstatic.com)> para todos los usuarios, esto sucede aunque no esté usando Gstatic. Teams quitará este requisito pronto (principios de 2020), y actualizaremos este artículo en consecuencia en ese momento.

## <a name="troubleshooting-modern-authentication"></a>Solución de problemas de la autenticación moderna

La autenticación moderna está disponible para cualquier organización que use Teams, por lo que si los usuarios no pueden completar el proceso, es posible que se haya producido un error en el dominio o en la cuenta profesional o educativa de Microsoft de su organización.

Para obtener más información, consulte [¿por qué tengo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)
