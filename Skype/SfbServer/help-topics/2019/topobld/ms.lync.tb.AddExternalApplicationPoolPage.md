---
title: Agregar FQDN de grupo de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir un nombre de dominio completo (FQDN) de un grupo de aplicaciones de confianza, especifique lo siguiente:'
ms.openlocfilehash: f23a09f3c7d73cf81912026a584942a917106f5e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837122"
---
# <a name="add-trusted-application-pool-fqdn"></a>Agregar FQDN de grupo de servidores de aplicaciones de confianza
 
Para definir un nombre de dominio completo (FQDN) de un grupo de aplicaciones de confianza, especifique lo siguiente:
  
El nombre de dominio completo del servidor o el grupo de servidores que hospedarán las aplicaciones de confianza.
  
Seleccione **Grupo de servidores de varios equipos** si va a implementar un grupo de servidores para las aplicaciones de confianza desde equilibrio de carga y alta disponibilidad; si no necesita equilibrio de carga ni alta disponibilidad, seleccione **Grupo de servidores de un solo equipo**.
  
> [!IMPORTANT]
> Un solo servidor de aplicaciones de confianza no se puede convertir en un grupo de servidores posteriormente. Si cree que puede necesitar un grupo de servidores en el futuro, puede implementar un grupo de servidores múltiple que contenga ahora un único equipo y agregar servidores cuando sea necesario. 
  
Para obtener más información sobre las aplicaciones de confianza, consulte [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
