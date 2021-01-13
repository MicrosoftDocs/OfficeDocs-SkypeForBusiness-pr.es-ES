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
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814140"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Supervisar, iniciar y detener los servicios de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo iniciar, detener y supervisar los servicios de chat persistente en Skype Empresarial Server 2015.
  
Los servicios de chat persistente y los servicios de cumplimiento de chat persistente forman parte de la topología de Skype Empresarial Server y, por lo tanto, se pueden supervisar, detener e iniciar con los cmdlets siguientes:
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Devuelve información detallada sobre los componentes de Skype Empresarial Server 2015 que se ejecutan como servicios de Windows.  <br/> |
|start-CsWindowsService  <br/> |Inicia el servicio.  <br/> |
|stop-CsWindowsService  <br/> |Detiene el servicio.  <br/> |
   
> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 

Para obtener información detallada sobre cómo usar los cmdlets, consulte Shell de administración de [Skype Empresarial Server 2015.](../management-shell.md)
  

