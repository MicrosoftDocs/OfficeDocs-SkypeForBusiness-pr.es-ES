---
title: Supervisar, iniciar y detener los servicios de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumen: obtenga información sobre cómo iniciar, detener y supervisar los servicios de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: c541964659ceec36209c4ea262d047cf116c35e444354f6e450b7b684e4992ec
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590724"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Supervisar, iniciar y detener los servicios de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo iniciar, detener y supervisar los servicios de chat persistente en Skype Empresarial Server 2015.
  
Los servicios de chat persistente y los servicios de cumplimiento de chat persistente forman parte de la topología de Skype Empresarial Server y, por lo tanto, se pueden supervisar, detener e iniciar mediante los cmdlets siguientes:
  
|Cmdlet|Función|
|:-----|:-----|
|get-CsWindowsService  <br/> |Devuelve información detallada acerca de Skype Empresarial Server componentes de 2015 que se ejecutan como Windows servicios.  <br/> |
|start-CsWindowsService  <br/> |Inicia el servicio.  <br/> |
|stop-CsWindowsService  <br/> |Detiene el servicio.  <br/> |
   
> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015. 

Para obtener información detallada sobre cómo usar los cmdlets, vea Skype Empresarial Server Shell de administración de [2015](../management-shell.md).
  

