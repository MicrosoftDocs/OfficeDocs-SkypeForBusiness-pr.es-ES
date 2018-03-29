---
title: Lista de tablas de cumplimiento de normas de servidor de charla persistente en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: El esquema de base de datos de cumplimiento de normas Chat persistente consta de las siguientes tablas.
ms.openlocfilehash: 801e8d5457a26ef968f700df16a68d36560548c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Lista de tablas de cumplimiento de normas de servidor de charla persistente en Skype para Business Server
 
El esquema de base de datos de cumplimiento de normas Chat persistente consta de las siguientes tablas.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista de tablas de cumplimiento de normas del servidor de Chat persistentes

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contiene los eventos de cumplimiento de normas que aún no se han procesado por el adaptador configurado.  <br/> Esta tabla incluye los eventos relacionados con el Chat persistente, como mensajes de chat y descargas de archivos. (Eventos de participante se hace un seguimiento en la tabla tblComplianceParticipant.)  <br/> (Los servidores que procesan los eventos en esta tabla se enumeran en la tabla de tblComplianceFanout).  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contiene los servidores que se procesan un evento de conformidad. Esta tabla está estrechamente emparejada con la tabla tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contiene a los participantes actuales por servidor y el servicio de charla. Se mantiene según los eventos de conformidad join y parte recibidos del servicio Charla persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contiene información de estado de cumplimiento de normas de todo el grupo.  <br/> |
   

