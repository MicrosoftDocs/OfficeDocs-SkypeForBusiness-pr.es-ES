---
title: Planear la autenticación moderna en Skype Empresarial
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Temas de planeación de autenticación y autorización para Skype Empresarial Server, incluida la integración con otros productos
ms.openlocfilehash: 3bcd9ab78c9703dd938230740fddba4034aff315
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851874"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Hablar de autenticación y autorización en Skype Empresarial

La autenticación y la autorización son conceptos relacionados, pero hacen un trabajo diferente por usted (aunque ambos son necesarios). En términos sencillos, la autenticación (AuthN) depende de secretos que solo un usuario válido conoce o tiene, y puede ser una contraseña, código, huella digital, certificado, una combinación de notificaciones sobre el usuario que son verdaderas o una combinación de estas cosas usadas juntos. AuthN es un proceso para demostrar que eres quien dice ser.

La autorización (AuthZ) se preocupa por lo que tiene acceso después de haber probado quién es. Determina lo que se le ha permitido ver, editar y obtener acceso de otro modo. Por ejemplo, puede que tenga acceso de administrador de colección de sitios eficaz a SharePoint Online, pero si cambia a otra carga de trabajo en línea, como Skype Empresarial Online, puede tener los privilegios para solucionar problemas de usuario y no cambiar la configuración del servidor o los servidores. En una tercera carga de trabajo, como Exchange Online, es posible que solo tenga acceso al usuario promedio. AuthZ comprueba qué y cuánto acceso tiene a los servicios/worloads, aplicaciones, archivos y otros datos.

Nuestros ejemplos incluyen propiedades en línea como SharePoint y Exchange en línea, pero los procesos de AuthN y AuthZ funcionan localmente y en un local híbrido del mismo modo. En última instancia, las herramientas como AAD Conectar y ADFS participan en el artículo de AuthN y AuthZ sincronizando cuentas locales y contraseñas en el AD de la nube (que es Azure AD) o inmiscuyendo en el flujo de AuthZ para que a un usuario no se le pidan con frecuencia sus credenciales, por ejemplo, al cambiar entre cargas de trabajo en la nube, crear escenarios de Sign-On únicos. Pero no son, en sí mismos, AuthN o AuthZ responsables, solo forman parte de la mecánica.

Hoy en día, muchas tecnologías consideran que estos procesos (AuthN y AuthZ) son un mecanismo y oirá muchas referencias al proceso de autenticación que también incluyen autorización en ellos. Es importante recordar que el primer paso en el acceso de usuario es AuthN, lo que demuestra que es quien dice ser y que AuthZ usa el conocimiento de quién es el usuario para determinar a qué tiene acceso (como verá con Open Authorization u OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Temas de planeación de autenticación y autorización

[Cómo usar la autenticación moderna (ADAL) con Skype Empresarial](plan-adal.md)

[Topologías de Skype Empresarial compatibles con la autenticación moderna](topologies-supported.md)

[Planeación de desactivar los métodos de autenticación heredados interna y externamente en la red.](turn-on-modern-auth.md)

