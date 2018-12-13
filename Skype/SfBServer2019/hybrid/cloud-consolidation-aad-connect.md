---
title: Actualizar AAD conectar para incluir más de un bosque
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye los pasos detallados para la actualización de AAD conectar para incluir más de uno de los bosques como parte de la consolidación en la nube para equipos y Skype para la empresa.
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247735"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Actualizar AAD conectar para incluir más de un bosque

Conectar de Azure AD admite la [sincronización de varios bosques](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). Sin embargo, es compatible con una única instancia de sincronización de Azure Connect de AD con AAD. Por lo tanto, en los casos donde Azure AD ya está instalado en un bosque, se debe actualizar la instancia existente de AAD conectar a la sincronización desde el bosque adicional.

 - Si todas las identidades se representan sólo una vez a través de ambos bosques (es decir, que no ha realizado todos los contactos habilitados para correo), a continuación, simplemente vuelva a ejecutar el Asistente para la conexión AAD, elija "Personalizar las opciones de sincronización" y, a continuación, en la **conectar los directorios **página, escriba el nombre del bosque adicional y credenciales.<br><br>
 ![El conectar su página de directorios](../media/cloud-consolidation-connect-your-directories.png)
 - Sin embargo, si los usuarios pueden existir en más de un directorio y aquí se combinar los datos (por ejemplo, si existen objetos de contacto en un bosque correspondiente a los usuarios en otro bosque), deberá desinstalar Azure Connect AD y volver a instalarlo.  Esto es debido a que la condición de las reglas de combinación de entre bosques sólo se puede configurar durante la primera instalación. Esto se realiza en la página siguiente:<br><br>
 ![Los caracteres que identifica la página de usuarios](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Vea también

[Consolidación de la nube para equipos y Skype para la empresa](cloud-consolidation.md)