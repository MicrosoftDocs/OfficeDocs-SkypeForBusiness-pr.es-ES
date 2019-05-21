---
title: Agregar FQDN de grupo de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir un nombre de dominio completo (FQDN) de un grupo de aplicaciones de confianza, especifique lo siguiente:'
ms.openlocfilehash: 026994a57da7838b2799484f000d69d8c9a168d7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278464"
---
# <a name="add-trusted-application-pool-fqdn"></a>Agregar FQDN de grupo de servidores de aplicaciones de confianza
 
Para definir un nombre de dominio completo (FQDN) de un grupo de aplicaciones de confianza, especifique lo siguiente:
  
Un FQDN del servidor o grupo de servidores que hospedarán las aplicaciones de confianza.
  
Seleccione **varios grupos de equipos** si va a implementar un grupo de servidores para las aplicaciones de confianza desde el equilibrio de carga y alta disponibilidad, o bien seleccione un **solo grupo de equipos** si no necesita equilibrio de carga o alta disponibilidad.
  
> [!IMPORTANT]
> Un servidor de aplicaciones de confianza único no se puede convertir en un grupo de servidores más adelante. Si cree que puede necesitar un grupo en el futuro, puede implementar un grupo de varios servidores que contenga un solo equipo y agregar servidores cuando sea necesario. 
  
Para obtener más información sobre los grupos de aplicaciones de confianza, vea [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

