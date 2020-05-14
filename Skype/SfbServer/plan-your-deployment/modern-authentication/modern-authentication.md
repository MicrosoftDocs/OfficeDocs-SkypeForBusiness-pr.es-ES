---
title: Planeación de la autenticación moderna en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Temas de planeación de la autenticación y autorización de Skype empresarial Server, incluida la integración con otros productos
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221584"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discutir la autenticación y la autorización en Skype empresarial

La autenticación y la autorización son conceptos relacionados, pero realizan distintas tareas por usted (aunque ambas son necesarias). En términos sencillos, Authenciation (authn) solo depende de los secretos que un usuario válido sabe o tiene, y que puede ser una contraseña, código, huella digital, certificado, una combinación de notificaciones sobre el usuario que son verdaderas o una combinación de estas cosas que se usan conjuntamente. Authn es un proceso que puede demostrar que es quien dice ser.

La autorización (AuthZ) está relacionada con aquello a la que tiene acceso después de haber demostrado quién es. Determina lo que se le permite ver, editar o tener acceso de cualquier otro modo. Por ejemplo, es posible que tenga acceso de administrador de la colección de sitios eficaz a SharePoint Online, pero si cambia a otra carga de trabajo en línea, como Skype empresarial online, es posible que tenga los privilegios necesarios para solucionar problemas de usuario, no cambiar la configuración del servidor o los servidores. En una tercera carga de trabajo, como Exchange Online, es posible que solo tenga acceso al usuario medio. AuthZ comprueba qué y con qué grado de acceso tiene a los servicios/worloads, las aplicaciones, los archivos y otros datos.

Nuestros ejemplos incluyen propiedades en línea como SharePoint y Exchange Online, pero los procesos de authn and AuthZ funcionan de forma local y en un entorno híbrido de la misma manera. En última instancia, herramientas como AAD Connect y ADFS participan en la historia de authn y AuthZ, ya sea mediante la sincronización de las cuentas locales y las contraseñas en el AD de la nube (que es Azure AD), o la intrusión en el flujo de AuthZ para que no se le pidan a los usuarios sus credenciales, por ejemplo, al cambiar entre cargas de trabajo Pero no son, por sí solas, authn o AuthZ responsables, sólo parte de la mecánica.

Hoy en día, muchas tecnologías consideran que estos procesos (authn y AuthZ) son un mecanismo y que escuchará muchas referencias al proceso de autenticación que también incluyen autorización en ellos. Es importante recordar que el primer paso en el acceso de los usuarios es authn, lo que demuestra que usted es quien dice ser y que AuthZ usa el conocimiento de quién es el usuario para determinar a qué tiene acceso (como verá con Open Authorization o OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Temas de planeación de autenticación y autorización

[Cómo usar la autenticación moderna (ADAL) con Skype empresarial](plan-adal.md)

[Topologías de Skype empresarial compatibles con la autenticación moderna](topologies-supported.md)

[Planear la desactivación interna y externa de los métodos de autenticación heredados en la red.](turn-on-modern-auth.md)

