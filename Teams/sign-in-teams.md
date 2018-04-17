---
title: Iniciar sesión en equipos de Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Instrucciones para iniciar sesión en el Teams de Microsoft utilizando autenticación moderna.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 443f20b1ecd8295acc4f731211c69d23a79f28dd
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
<a name="sign-in-to-microsoft-teams"></a>Iniciar sesión en equipos de Microsoft
==========================

Teams de Microsoft utiliza autenticación moderna para mantener la experiencia sencilla y segura.

## <a name="how-modern-authentication-works"></a>Moderno cómo funciona la autenticación

Autenticación moderno es un proceso que permite que los equipos saben que los usuarios ya han escrito sus credenciales (como el correo electrónico del trabajo y la contraseña) en otro lugar, y no se le exige que escribirlas de nuevo para iniciar la aplicación. La experiencia variará dependiendo de dos factores, como si los usuarios están trabajando en Windows o en Mac. También variará dependiendo de si su organización ha habilitado la autenticación de factor único o múltiples factores de autenticación (autenticación multifactor normalmente implica la comprobación de credenciales a través de un teléfono, proporcionando un código único, escribir un PIN, o presentar una huella digital). Aquí tiene un resumen de cada escenario de autenticación modernos.

### <a name="windows-users"></a>Usuarios de Windows 

- Si los usuarios han firmado ya otras aplicaciones de Office mediante su cuenta de empresa de Office 365, cuando inician los equipos está tomadas rectas a la aplicación. No es necesario para especificar sus credenciales.

- Si los usuarios no inició sesión su cuenta de Office 365 Enterprise en cualquier otro, cuando inician los equipos, se pide que se proporcione la autenticación de factor único o varios factor (SFA o AMF), dependiendo de lo que la organización ha decidido que desearían los proceso pueden implicar.

- Si los usuarios han iniciado sesión un equipo unido al dominio, cuando inician los equipos, que pueden tener que pasar por uno más paso de autenticación, dependiendo de si la organización optó por requerir AMF o si su equipo ya requiere AMF iniciar sesión en. Si su equipo ya requiere AMF iniciar sesión en, cuando abran los equipos, la aplicación automáticamente se inicia.

### <a name="mac-users"></a>Usuarios de Mac 

Cuando los usuarios inicien los equipos, su equipo no podrá extraer sus credenciales de su cuenta de Office 365 Enterprise o cualquiera de sus otras aplicaciones de Office. En su lugar, verán un mensaje solicitando SFA o AMF (según la configuración de su organización). Una vez que los usuarios escriben sus credenciales, no se necesitará a fin de proporcionarles otra vez. Desde ese momento, los equipos automáticamente se inicia siempre que trabaje en el mismo equipo.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Cuentas de conmutación después de completar la autenticación moderno

Si los usuarios están trabajando en un equipo unido al dominio (por ejemplo, si su arrendatario ha habilitado Kerberos), no pueden cambiar las cuentas de usuario una vez que hayan finalizado la autenticación moderna. Si los usuarios no están trabajando en un equipo unido al dominio, las cuentas pueden cambiar.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>La sesión de Teams de Microsoft después de completar la autenticación moderno

Para cerrar sesión en los equipos, los usuarios pueden haga clic en su imagen de perfil en la parte superior de la aplicación y, a continuación, seleccione **Cerrar sesión**. Puede también haga clic derecho en el icono de la aplicación en la barra de tareas y, a continuación, seleccione **Cerrar sesión**. Una vez que ha de cerrar la sesión de equipos, necesitan escribir sus credenciales para iniciar la aplicación.

## <a name="troubleshooting-modern-authentication"></a>Solución de problemas de autenticación moderno

Autenticación moderna está disponible para todas las organizaciones que utiliza los equipos, por lo que si los usuarios no son capaces de completar el proceso, puede haber algún problema con su cuenta de dominio o de la organización empresarial de Office 365. 

Para obtener más información, consulte [¿por qué tengo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/en-US/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

