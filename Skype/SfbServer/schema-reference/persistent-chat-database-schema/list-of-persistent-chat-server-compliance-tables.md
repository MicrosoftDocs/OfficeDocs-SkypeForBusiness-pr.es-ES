---
title: Lista de tablas de cumplimiento del servidor de chat persistente en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: El esquema de base de datos de cumplimiento de chat persistente consta de las tablas siguientes.
ms.openlocfilehash: cc4a40d5c2fa80559ddb2ba2cb713c078b4af357
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833254"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Lista de tablas de cumplimiento del servidor de chat persistente en Skype Empresarial Server
 
El esquema de base de datos de cumplimiento de chat persistente consta de las tablas siguientes.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista de tablas de cumplimiento del servidor de chat persistente

|**Table**|**Descripción**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contiene los eventos de cumplimiento que aún no fueron procesados por el adaptador configurado.  <br/> Esta tabla incluye eventos relacionados con chat persistente, como mensajes de chat y descargas de archivos. (Los eventos participantes son seguidos por la tabla tblComplianceParticipant).  <br/> (Los servidores que procesaron los eventos en esta tabla se enumeran en la tabla tblComplianceFanout).  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contiene los servidores que procesaron un evento de cumplimiento. Esta tabla está fuertemente vinculada con la tabla tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contiene los participantes actuales por servicio de chat y por servidor. Se mantiene en función de los eventos de unión y cumplimiento de partes recibidos del servicio de chat persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contiene información de estado de cumplimiento de todo el grupo.  <br/> |
   

