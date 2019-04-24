---
title: Lista de tablas de cumplimiento del servidor de Chat persistente en Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: El esquema de base de datos de cumplimiento de normas de Chat persistente consta de las siguientes tablas.
ms.openlocfilehash: 18c35cc71da43dcf25bb477e81a2471b483ee86d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212701"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Lista de tablas de cumplimiento del servidor de Chat persistente en Skype para Business Server
 
El esquema de base de datos de cumplimiento de normas de Chat persistente consta de las siguientes tablas.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista de tablas de cumplimiento del servidor de Chat en grupo

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contiene los eventos de cumplimiento que aún no se han procesado por el adaptador configurado.  <br/> Esta tabla incluye los eventos relacionados con el Chat persistente, como mensajes de chat y descargas de archivos. (Eventos de participante se realiza un seguimiento de la tabla tblComplianceParticipant.)  <br/> (Los servidores que procesaron los eventos de esta tabla se enumeran en la tabla tblComplianceFanout).  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contiene los servidores que procesaron un evento de cumplimiento. En esta tabla se complementa con la tabla tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contiene a los participantes actuales por el servicio de chat y por servidor. Se mantiene en función de eventos de cumplimiento de combinación y elemento recibidos desde el servicio de Chat persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contiene información de estado de cumplimiento de todo el grupo de servidores.  <br/> |
   

