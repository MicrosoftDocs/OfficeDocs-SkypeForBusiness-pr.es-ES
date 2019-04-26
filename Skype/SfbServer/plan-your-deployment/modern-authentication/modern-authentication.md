---
title: Planificar la autenticación moderna en Skype Empresarial
ms.reviewer: ''
ms.author: tracyp
author: MSFTTracyP
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Temas de planeamiento para la autenticación y autorización de Skype para Business Server, incluida la integración con otros productos
ms.openlocfilehash: 662eb90758bb22a9ef65492d9c9c1a99af778f23
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214120"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Trate de autenticación y autorización en Skype para la empresa

Autenticación y autorización son conceptos relacionados, pero hacer trabajo diferente por usted (aunque ambos son necesarias). Poner en términos sencillos, authenciation (niveles de autenticación) depende de secretos sólo sabe o que tenga un usuario válido, y que puede ser una contraseña, código, huella, certificado, una combinación de notificaciones sobre el usuario que son true o una combinación de estas cosas utilizado conjuntamente. Niveles de autenticación es un proceso de salida para demostrar que usted es quien dice que ser.

Autorización (AuthZ) está relacionada con lo que podrá acceder a después de haber probado quién es usted. Determina qué ha se ha permitido para ver, editar y, en caso contrario, tener acceso. Por ejemplo, puede tener acceso eficaz de administrador de colección de sitios a SharePoint Online, pero si se cambia a otra carga de trabajo en línea, al igual que Skype para en línea de negocio, puede que tenga los privilegios para solucionar problemas de usuario, no cambie la configuración de la servidor o servidores. En una carga de trabajo de terceros, como Exchange Online, solo puede que tenga acceso de un usuario promedio. AuthZ comprueba qué y cuánto acceso a servicios/worloads, aplicaciones, archivos y otros datos.

Los ejemplos implican propiedades en línea como SharePoint y Exchange online, pero los procesos de niveles de autenticación y AuthZ funcionen local y en un local híbrida del mismo modo. En última instancia, herramientas como AAD conectar y ADFS intervenir en la historia de niveles de autenticación y AuthZ por sincronizar cuentas locales y las contraseñas en la nube de AD (que es Azure AD en el caso de Office 365 o Azure), o que unos se entrometan en el flujo de AuthZ por lo que un usuario no se pide con frecuencia para sus credenciales, diga al cambiar entre las cargas de trabajo en la nube, creación de escenarios de inicio de sesión único. Pero no son, en sí mismos, niveles de autenticación responsable o AuthZ, parte de la mecánica.

En la actualidad, muchas tecnologías, tenga en cuenta estos procesos (niveles de autenticación y AuthZ), como un mecanismo y oirá muchas referencias al proceso de autenticación que también incluyen autorización en ellos. Es importante recordar que el primer paso para el acceso de usuarios es niveles de autenticación, que demuestren que usted es quien dice que ser, y que AuthZ usa el conocimiento de quién es el usuario determinar qué navegará tiene acceso a (como verá con autorización Open o OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Temas de planeación de autorización y autenticación

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[Planeación desactivar los métodos de autenticación Legacy interna y externamente a su red.](turn-on-modern-auth.md)

