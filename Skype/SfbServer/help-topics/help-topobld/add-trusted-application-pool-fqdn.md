---
title: Agregar FQDN de grupo de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Para definir un nombre de dominio completo (FQDN) de un grupo de aplicaciones de confianza, especifique lo siguiente:'
ms.openlocfilehash: fc4817bad1c82d0ae0e50be6a5c08d03bb73687e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122484"
---
# <a name="add-trusted-application-pool-fqdn"></a>Agregar FQDN de grupo de servidores de aplicaciones de confianza
 
Para definir un nombre de dominio completo (FQDN) de un grupo de aplicaciones de confianza, especifique lo siguiente:
  
El nombre de dominio completo del servidor o el grupo de servidores que hospedarán las aplicaciones de confianza.
  
Seleccione **Grupo de servidores de varios equipos** si va a implementar un grupo de servidores para las aplicaciones de confianza desde equilibrio de carga y alta disponibilidad; si no necesita equilibrio de carga ni alta disponibilidad, seleccione **Grupo de servidores de un solo equipo**.
  
> [!IMPORTANT]
> Un solo servidor de aplicaciones de confianza no se puede convertir en un grupo de servidores posteriormente. Si cree que puede necesitar un grupo de servidores en el futuro, puede implementar un grupo de servidores múltiple que contenga ahora un único equipo y agregar servidores cuando sea necesario. 
  
Para obtener más información sobre las aplicaciones de confianza, consulte [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
