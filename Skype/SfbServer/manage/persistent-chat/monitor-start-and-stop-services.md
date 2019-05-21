---
title: Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumen: Aprenda a iniciar, detener y supervisar los servicios de chat persistentes en Skype empresarial Server 2015.'
ms.openlocfilehash: 161bda3cb02bf6208b4db9f1c6825d3fe433eeca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279294"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo iniciar, detener y supervisar los servicios de chat persistentes en Skype empresarial Server 2015.
  
Los servicios de chat persistente y el cumplimiento de chat persistente forman parte de la topología de servidor de Skype empresarial y, por lo tanto, se pueden supervisar, detener e iniciar con los siguientes cmdlets:
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Devuelve información detallada sobre los componentes de Skype empresarial Server 2015 que se ejecutan como servicios de Windows.  <br/> |
|start-CsWindowsService  <br/> |Inicia el servicio.  <br/> |
|stop-CsWindowsService  <br/> |Detiene el servicio.  <br/> |
   
> [!NOTE]
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 

Para más información sobre cómo usar los cmdlets, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

