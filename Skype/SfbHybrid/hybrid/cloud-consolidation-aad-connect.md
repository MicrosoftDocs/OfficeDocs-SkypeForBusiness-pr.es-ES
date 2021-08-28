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
ms.localizationpriority: medium
description: En este apéndice se incluyen pasos detallados para actualizar los Conectar AAD para incluir más de un bosque como parte de la consolidación de la nube para Teams y Skype Empresarial.
ms.openlocfilehash: e803ae1e41fd0e68a56e059bbaf398ee30f807f6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625802"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Actualizar AAD Connect para incluir más de un bosque

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD Conectar [la sincronización desde varios bosques.](/azure/active-directory/connect/active-directory-aadconnect-topologies) Sin embargo, solo admite una instancia de Azure AD Conectar sincronización con AAD. Por lo tanto, en los casos en los que Azure AD ya está instalado en un bosque, la instancia existente de AAD Conectar debe actualizarse para sincronizarse desde el bosque adicional.

 - Si todas las identidades se representan solo una vez en ambos bosques (es decir, no ha realizado contactos habilitados para correo), puede volver a ejecutar el asistente de AAD Conectar, elegir "Personalizar opciones de sincronización" y, a continuación, en la página **Conectar** Sus directorios, escriba el nombre del bosque y las creds adicionales.<br><br>
 ![La Conectar de directorios](../media/cloud-consolidation-connect-your-directories.png)
 - Sin embargo, si los usuarios pueden existir en más de un directorio y combinará los datos (por ejemplo, si existen objetos de contacto en un bosque correspondiente a los usuarios de otro bosque), deberá desinstalar Azure AD Conectar y volver a instalarlo.  Esto se debe a que la condición de reglas de combinación entre bosques solo se puede configurar durante la primera instalación. Esto se realiza en la página siguiente:<br><br>
 ![La página Identificación única de los usuarios](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Consulte también

[Consolidación de nube para Teams y Skype Empresarial](cloud-consolidation.md)