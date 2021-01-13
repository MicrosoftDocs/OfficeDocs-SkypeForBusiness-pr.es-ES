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
description: 'Para definir un nombre de dominio completo (FQDN) de grupo de aplicaciones de confianza, especifique lo siguiente:'
ms.openlocfilehash: acbae42e5bd37e8fcdb009a033bdf583eab00a5f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803560"
---
# <a name="add-trusted-application-pool-fqdn"></a>Agregar FQDN de grupo de servidores de aplicaciones de confianza
 
Para definir un nombre de dominio completo (FQDN) de grupo de aplicaciones de confianza, especifique lo siguiente:
  
El nombre de dominio completo del servidor o el grupo de servidores que hospedarán las aplicaciones de confianza.
  
Seleccione **Grupo de servidores de varios equipos** si va a implementar un grupo de servidores para las aplicaciones de confianza desde equilibrio de carga y alta disponibilidad; si no necesita equilibrio de carga ni alta disponibilidad, seleccione **Grupo de servidores de un solo equipo**.
  
> [!IMPORTANT]
> Un solo servidor de aplicaciones de confianza no se puede convertir en un grupo de servidores posteriormente. Si cree que puede necesitar un grupo en el futuro, puede implementar un grupo de varios servidores que contenga ahora un único equipo y agregar servidores cuando sea necesario. 
  
Para obtener más información sobre las aplicaciones de confianza, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

