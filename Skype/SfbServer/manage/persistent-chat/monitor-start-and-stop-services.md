---
title: Supervisar, iniciar y detener los servicios de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumen: obtenga información sobre cómo iniciar, detener y supervisar los servicios de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 9d25654a222b956fa5c8a1902e5d3a90674829e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833386"
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
  

