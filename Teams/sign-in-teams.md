---
title: Inicie sesión en los equipos de Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Instrucciones para iniciar sesión en Microsoft Teams mediante el uso de autenticación moderna.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c24625d44bc174a60275b6532001b5f7efc9efc
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "19003369"
---
<a name="sign-in-to-microsoft-teams"></a>Inicie sesión en los equipos de Microsoft
==========================

Microsoft Teams usa autenticación moderna para conservar la experiencia de inicio de sesión sencilla y segura.

## <a name="how-modern-authentication-works"></a>Moderno cómo funciona la autenticación

Autenticación moderna es un proceso que permite a los equipos a saber que los usuarios ya han escrito sus credenciales (al igual que su correo electrónico del trabajo y la contraseña) en otro lugar, y no necesitan que escribirlas de nuevo para iniciar la aplicación. La experiencia de variará en función factores un par, al igual que si los usuarios están trabajando en Windows o en un MAC. También varían dependiendo de si su organización ha habilitado la autenticación de factor único o autenticación multifactor (autenticación multifactor normalmente implica la comprobación de credenciales a través de un teléfono, que proporciona un código único, especificar un PIN, o presentar una huella digital). Este es un resumen de cada escenario de autenticación moderno.

### <a name="windows-users"></a>Usuarios de Windows 

- Si los usuarios han ya ha iniciado sesión otras aplicaciones de Office a través de su cuenta de Office 365 Enterprise, cuando inician los equipos que se tomaron rectas a la aplicación. No es necesario para que puedan escribir sus credenciales.

- Si los usuarios no están ha iniciado sesión su cuenta de Office 365 Enterprise en ningún otro lugar, cuando inician los equipos, pregunte para proporcionar la autenticación de factor único o varios factor (SFA o MFA), dependiendo de lo que la organización ha decidido que desearían el proceso que implican.

- Si los usuarios se conectan a un equipo unido a un dominio, cuando inician los equipos, que es posible que se le pida para ir a través de una paso de autenticación más, dependiendo de si la organización optó por requieren MFA o si su equipo ya requiere MFA iniciar sesión. Si su equipo ya requiere MFA iniciar sesión, cuando se abren los equipos, la aplicación automáticamente se inicia.

### <a name="mac-users"></a>Usuarios de Mac 

Cuando los usuarios inicien los equipos, su equipo no podrá extraer sus credenciales de su cuenta de Office 365 Enterprise o cualquiera de sus otras aplicaciones de Office. En su lugar, verán un mensaje indicándole para SFA o MFA (según la configuración de la organización). Una vez que los usuarios escriben sus credenciales, no se necesitará a fin de proporcionarles nuevo. A partir de ese momento, los equipos automáticamente se inicia cada vez que está trabajando en el mismo equipo.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Cambiar cuentas después de completar la autenticación moderna

Si los usuarios están trabajando en un equipo unido a un dominio (por ejemplo, si su inquilino ha habilitado Kerberos), no pueden cambiar las cuentas de usuario una vez que hayan completado la autenticación moderna. Si los usuarios no están trabajando en un equipo unido a un dominio, puede cambiar de cuentas.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Cerrar una sesión de Microsoft Teams después de completar la autenticación moderna

Para desconectarse de los equipos, los usuarios pueden haga clic en su imagen de perfil en la parte superior de la aplicación y, a continuación, seleccione **Cerrar sesión**. Pueden también (ratón) en el icono de la aplicación en la barra de tareas y, a continuación, seleccione **Cerrar la sesión**. Una vez que ha de cerrar la sesión de equipos, que se necesitan escribir sus credenciales de nuevo para iniciar la aplicación.

## <a name="troubleshooting-modern-authentication"></a>Solución de problemas de autenticación moderna

Autenticación moderna está disponible para todas las organizaciones que usa los equipos, por lo que si los usuarios no pueden completar el proceso, puede haber algún problema con su dominio o cuenta de Office 365 Enterprise de su organización. 

Para obtener más información, vea [¿por qué estoy teniendo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/en-US/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

