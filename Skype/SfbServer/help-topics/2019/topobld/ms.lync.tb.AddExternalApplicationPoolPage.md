---
title: Agregar el FQDN del grupo de aplicaciones de confianza
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir un nombre de dominio completo del grupo de servidores de aplicaciones de confianza (FQDN), especifique lo siguiente:'
ms.openlocfilehash: c8241e5e037b4f7993c73e1a10982465ac14dcaf
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21067612"
---
# <a name="add-trusted-application-pool-fqdn"></a>Agregar el FQDN del grupo de aplicaciones de confianza
 
Para definir un nombre de dominio completo del grupo de servidores de aplicaciones de confianza (FQDN), especifique lo siguiente:
  
Un nombre de dominio completo del servidor o grupo de servidores que se va a hospedar las aplicaciones de confianza.
  
Si va a implementar un grupo de servidores para las aplicaciones de confianza de equilibrio de carga y alta disponibilidad, o seleccione el **grupo de servidores de un solo equipo** si no necesita disponibilidad alta o equilibrio de carga, seleccione **el grupo de servidores de varios equipos** .
  
> [!IMPORTANT]
> Un único servidor de aplicaciones de confianza no se puede convertir a un grupo de servidores más adelante. Si piensa que es posible que necesite un grupo de servidores en el futuro, puede implementar un grupo de servidores de varios que ahora contiene un único equipo y adición de servidores cuando es necesario. 
  
Para obtener información detallada acerca de los grupos de servidores de aplicaciones de confianza, vea [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

