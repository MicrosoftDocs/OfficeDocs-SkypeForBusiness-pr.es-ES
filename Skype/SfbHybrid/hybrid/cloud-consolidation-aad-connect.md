---
title: Actualizar AAD Connect para incluir más de un bosque
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apéndice incluye pasos detallados para actualizar AAD Connect para incluir más de un bosque como parte de la consolidación de la nube para Teams y Skype Empresarial.
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049102"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Actualizar AAD Connect para incluir más de un bosque

Azure AD Connect admite [la sincronización de varios bosques.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies) Sin embargo, solo admite una instancia de sincronización de Azure AD Connect con AAD. Por lo tanto, en los casos en los que Azure AD ya está instalado en un bosque, la instancia existente de AAD Connect debe actualizarse para sincronizarse desde el bosque adicional.

 - Si todas las identidades se representan una sola vez en ambos bosques (es decir, no ha realizado contactos habilitados para correo), puede  volver a ejecutar el asistente para AAD Connect, elegir "Personalizar opciones de sincronización" y, a continuación, en la página Conectar directorios, escriba el nombre del bosque adicional y las creds.<br><br>
 ![La página Conectar los directorios](../media/cloud-consolidation-connect-your-directories.png)
 - Sin embargo, si los usuarios pueden existir en más de un directorio y va a combinar los datos (por ejemplo, si existen objetos de contacto en un bosque correspondiente a los usuarios de otro bosque), tendrá que desinstalar Azure AD Connect y volver a instalarlo.  Esto se debe a que la condición de reglas de combinación entre bosques solo se puede configurar durante la primera instalación. Esto se realiza en la página siguiente:<br><br>
 ![La página De identificación única de los usuarios](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Vea también

[Consolidación de la nube para Teams y Skype Empresarial](cloud-consolidation.md)