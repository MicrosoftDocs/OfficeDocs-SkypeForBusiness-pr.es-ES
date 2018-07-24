---
title: Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumen: Obtenga información sobre cómo iniciar, detener y supervisar los servicios de Chat persistente de Skype para Business Server 2015.'
ms.openlocfilehash: 272ea0f4270b1109ff77b5d809472051705b6f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991592"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo iniciar, detener y supervisar los servicios de Chat persistente de Skype para Business Server 2015.
  
Los servicios de Chat persistente y cumplimiento de Chat persistente forman parte de la Skype para la topología de servidor empresarial y puede, por tanto, se supervisan, detenido e iniciarse mediante los cmdlets siguientes:
  
|||
|:-----|:-----|
|Get-CsWindowsService  <br/> |Devuelve información detallada acerca de Skype para Business Server 2015 componentes que se ejecutan como servicios de Windows.  <br/> |
|Start-CsWindowsService  <br/> |Inicia el servicio.  <br/> |
|Stop-CsWindowsService  <br/> |Detiene el servicio.  <br/> |
   
> [!NOTE]
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 

Para obtener información detallada sobre cómo usar los cmdlets, vea [Skype para Shell de administración de Business Server 2015](../management-shell.md).
  

