---
title: Agregue el FQDN del grupo de aplicaciones de confianza
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Para definir un nombre de dominio completo del grupo de aplicaciones de confianza (FQDN), especifique lo siguiente:'
ms.openlocfilehash: af21ab09797a5b81f2071a37a2668d556f0a4012
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-trusted-application-pool-fqdn"></a>Agregue el FQDN del grupo de aplicaciones de confianza
 
Para definir un nombre de dominio completo del grupo de aplicaciones de confianza (FQDN), especifique lo siguiente:
  
Un nombre de dominio completo del servidor o grupo de servidores que alojarán las aplicaciones de confianza.
  
Seleccione **grupo de equipo múltiple** si va a implementar una agrupación de servidores de alta disponibilidad y equilibrio de carga de las aplicaciones de confianza, o seleccione el **grupo de equipo solo** si no es necesario cargar equilibrio o alta disponibilidad.
  
> [!IMPORTANT]
> Un único servidor de aplicaciones de confianza no se puede convertir a un grupo de servidores más adelante. Si cree que puede que necesite un grupo en el futuro, puede implementar un grupo de servidores múltiples con un único equipo ahora y agregar servidores cuando sea necesario. 
  
Para obtener más información acerca de los grupos de aplicaciones de confianza, vea [CsTrustedApplicationPool de nuevo](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

