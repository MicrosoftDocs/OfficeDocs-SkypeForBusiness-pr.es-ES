---
title: Planear la autenticación moderna en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Temas de planeación de autenticación y autorización para Skype Empresarial Server, incluida la integración con otros productos
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816250"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discusión de autenticación y autorización en Skype Empresarial

La autenticación y la autorización son conceptos relacionados, pero hacen diferentes tareas (aunque ambas son necesarias). En términos sencillos, la autenticación (AuthN) depende de secretos que solo un usuario válido conoce o tiene, y que pueden ser una contraseña, código, huella digital, certificado, una combinación de notificaciones sobre el usuario que son verdaderas o una combinación de estas cosas que se usan juntas. AuthN es un proceso para demostrar que eres quien dice ser.

La autorización (AuthZ) se preocupa por lo que tiene acceso después de haber probado quién es. Determina lo que se le ha permitido ver, editar y obtener acceso de otro modo. Por ejemplo, puede que tenga acceso de administrador de colección de sitios eficaz a SharePoint Online, pero si cambia a otra carga de trabajo en línea, como Skype Empresarial Online, puede que tenga privilegios para solucionar problemas de usuario, no para cambiar la configuración del servidor o los servidores. En una tercera carga de trabajo, como Exchange Online, es posible que solo tenga el acceso promedio del usuario. AuthZ comprueba qué y cuánto acceso tiene a servicios/cargas de carga, aplicaciones, archivos y otros datos.

Nuestros ejemplos implican propiedades en línea como SharePoint y Exchange Online, pero los procesos de AuthN y AuthZ funcionan localmente y en un entorno híbrido de la misma manera. En última instancia, las herramientas como AAD Connect y ADFS se involucran en la historia de AuthN y AuthZ mediante la sincronización de cuentas y contraseñas locales en ad de la nube (que es Azure AD) o la intrusión en el flujo de AuthZ para que a un usuario no se le pidan con frecuencia sus credenciales, por ejemplo, al cambiar entre cargas de trabajo en la nube, crear escenarios de Sign-On único. Pero no son, por sí mismos, AuthN o AuthZ responsables, solo forman parte de la mecánica.

Hoy en día, muchas tecnologías consideran que estos procesos (AuthN y AuthZ) son un mecanismo y oirá muchas referencias al proceso de autenticación que también incluyen autorización en ellos. Es importante recordar que el primer paso en el acceso de usuario es AuthN, lo que demuestra que es quien dice ser y que AuthZ usa el conocimiento de quién es el usuario para determinar a qué tiene acceso (como verá con Open Authorization u OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Temas de planeación de autenticación y autorización

[Cómo usar la autenticación moderna (ADAL) con Skype Empresarial](plan-adal.md)

[Topologías de Skype Empresarial compatibles con la autenticación moderna](topologies-supported.md)

[Planee desactivar los métodos de autenticación heredados interna y externamente en la red.](turn-on-modern-auth.md)

