---
title: Iniciar sesión en Microsoft Teams con la autenticación moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Cómo iniciar sesión en Microsoft Teams mediante la autenticación moderna.
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79f04161c070ff4818fdb2dfc212e5c3fc98b2b0
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845141"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Iniciar sesión en Microsoft Teams con la autenticación moderna
==========================

Microsoft Teams usa la autenticación moderna para que la experiencia de inicio de sesión sea sencilla y segura. Para ver cómo los usuarios inician sesión en Teams, lea [iniciar sesión en Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Cómo funciona la autenticación moderna

La autenticación moderna es un proceso que permite a los equipos saber que los usuarios ya han escrito sus credenciales (como el correo electrónico y la contraseña del trabajo) en otro lugar y no es necesario que las vuelvan a escribir para iniciar la aplicación. La experiencia variará en función de un par de factores, como si los usuarios estuvieran trabajando en Windows o en un equipo Mac. También variará dependiendo de si su organización ha habilitado la autenticación de factor único o la autenticación multifactor (la autenticación multifactor generalmente implica comprobar las credenciales a través de un teléfono, lo que proporciona un código único, escribe un PIN o presentar una huella digital). Este es un resumen de cada escenario de autenticación moderna.

### <a name="windows-users"></a>Usuarios de Windows 

- Si los usuarios ya han iniciado sesión en otras aplicaciones de Office a través de su cuenta de Office 365 Enterprise, cuando inicien Teams se les dirigirá directamente a la aplicación. No es necesario que introduzcan sus credenciales.

- Si los usuarios no han iniciado sesión en su cuenta de Office 365 Enterprise en ningún otro lugar, cuando inicien Teams, se les pedirá que proporcionen autenticación multifactor o de factor único (fútbolso o MFA), en función de lo que su organización haya decidido que le gustaría proceso.

- Si los usuarios han iniciado sesión en un equipo unido a un dominio, cuando inicien Teams, es posible que se le pida un paso más de autenticación, en función de si su organización optó por requerir MFA o si su equipo ya requiere MFA para iniciar sesión. Si su equipo ya requiere que MFA inicie sesión, cuando abra Teams, la aplicación se iniciará automáticamente.

- Si los usuarios han iniciado sesión en un equipo unido a un dominio y no desea que su nombre de usuario se haya rellenado previamente en la pantalla de inicio de sesión de Teams, los administradores pueden configurar el siguiente registro de Windows para desactivar el rellenado anterior del nombre de usuario (UPN):

  Equipo \ HKEY_CURRENT_USER \Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill (REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > La omisión del nombre de usuario prerelleno de los nombres de usuario que terminan en ". local" o ". Corp" está activado de forma predeterminada, por lo que no es necesario configurar una clave del registro para desactivarlo. 


### <a name="mac-users"></a>Usuarios de Mac 

Cuando los usuarios inician Teams, su equipo no podrá recuperar sus credenciales de su cuenta de Office 365 Enterprise ni de ninguna de las otras aplicaciones de Office. En su lugar, verán un mensaje pidiéndole a la persona con la configuración de, según la configuración de su organización. Una vez que los usuarios escriben sus credenciales, no se les pedirá que vuelvan a proporcionarlas. A partir de ese momento, los equipos se inician automáticamente cada vez que trabajan en el mismo equipo.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Cambiar de cuenta tras completar la autenticación moderna

Si los usuarios trabajan en un equipo unido a un dominio (por ejemplo, si su inquilino ha habilitado Kerberos), no puede cambiar las cuentas de usuario una vez que haya completado la autenticación moderna. Si los usuarios no trabajan en un equipo unido a un dominio, pueden cambiar de cuenta.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Cerrar la sesión de Microsoft Teams tras completar la autenticación moderna
Para cerrar la sesión de Teams, los usuarios pueden hacer clic en su imagen de perfil en la parte superior de la aplicación y, a continuación, seleccionar **Cerrar sesión**. También puede hacer clic con el botón derecho en el icono de la aplicación en la barra de tareas y, a continuación, seleccionar **Cerrar sesión**. Una vez que se cierra la sesión de Teams, es necesario volver a escribir sus credenciales para iniciar la aplicación.

## <a name="urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP
Teams requiere conectividad a Internet. Para comprender los puntos de conexión que deben ser accesibles para los clientes que usan equipos en planes de Office 365, administración pública y otras nubes, lea las [instrucciones disponibles aquí](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Además, también necesitará permitir el acceso a https://ssl.gstatic.com.

## <a name="troubleshooting-modern-authentication"></a>Solución de problemas de autenticación moderna

La autenticación moderna está disponible para todas las organizaciones que usan Teams, por lo que si los usuarios no pueden completar el proceso, es posible que haya algún problema con su dominio o con la cuenta de Office 365 Enterprise de su organización. 

Para obtener más información, consulte [¿por qué tengo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

