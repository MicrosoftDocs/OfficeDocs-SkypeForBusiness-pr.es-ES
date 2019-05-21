---
title: Planificar la autenticación moderna en Skype Empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Temas de planeación de la autenticación y autorización de Skype empresarial Server, incluida la integración con otros productos
ms.openlocfilehash: 922b53b26bd77be4f7d49e7c594d337f7961703d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297305"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discutir la autenticación y la autorización en Skype empresarial

La autenticación y la autorización son conceptos relacionados, pero hacen que el trabajo sea diferente (aunque ambos son necesarios). En términos simples, Authenciation (authn) depende de los secretos solo que un usuario válido sabe o tiene, y que puede ser una contraseña, código, huella dactilar, certificado, una combinación de reclamaciones sobre el usuario que son verdaderas o una combinación de estas cosas que se usan conjuntamente. Authn es un proceso que puede demostrar que eres quien dice que eres.

La autorización (AuthZ) se refiere a lo que tienes accesible después de haber demostrado quién eres. Determina qué se le permitió ver, editar y, de otro modo, acceder a. Por ejemplo, es posible que tenga acceso eficaz de administrador de la colección de sitios a SharePoint Online, pero si cambia a otra carga de trabajo en línea, como Skype empresarial online, es posible que tenga los privilegios para solucionar los problemas de los usuarios, no cambiar la configuración de la servidor o servidores. En una tercera carga de trabajo, como Exchange Online, es posible que solo tenga acceso al usuario promedio. AuthZ comprueba qué es el acceso y el nivel de acceso que tiene a servicios/worloads, aplicaciones, archivos y otros datos.

Nuestros ejemplos implican propiedades en línea como SharePoint y Exchange Online, pero los procesos de authn y AuthZ funcionan de manera local y en un entorno híbrido de la misma manera. En última instancia, las herramientas como AAD Connect y ADFS participan en la historia de authn y AuthZ, ya que sincronizan las cuentas locales y las contraseñas en el AD de la nube (que es Azure AD, en el caso de Office 365 o Azure), o intrusos en el flujo de AuthZ para que los usuarios no suelen solicitar sus credenciales, como cuando cambian entre cargas de trabajo en la nube, lo que crea escenarios de inicio de sesión único. Pero no son, en sí mismos, autenticaciones responsables o AuthZ, solo forman parte de la mecánica.

Hoy en día, muchas tecnologías consideran que estos procesos (authn y AuthZ) sean un mecanismo y escuchará muchas referencias a procesos de autenticación que también incluyen autorización. Es importante recordar que el primer paso en el acceso de los usuarios es authn, demostrar que eres quien dice que eres y que AuthZ usa el conocimiento de quién es el usuario para determinar a qué tiene acceso (como verás con la autorización abierta o OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Temas de planeación de autenticación y autorización

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[Planear la desactivación de los métodos de autenticación heredados de forma interna y externa a la red.](turn-on-modern-auth.md)

