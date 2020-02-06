---
title: Lista de tablas de cumplimiento del servidor de chat persistente en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: El esquema de base de datos de cumplimiento de chat persistente consta de las siguientes tablas.
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814768"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Lista de tablas de cumplimiento del servidor de chat persistente en Skype empresarial Server
 
El esquema de base de datos de cumplimiento de chat persistente consta de las siguientes tablas.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista de tablas de cumplimiento del servidor de chat persistente

|**Tabla**|**Descripción**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contiene los eventos de cumplimiento que el adaptador configurado aún no ha procesado.  <br/> Esta tabla incluye eventos persistentes relacionados con el chat, como mensajes instantáneos y descargas de archivos. (Los eventos de participantes se controlan en la tabla tblComplianceParticipant).  <br/> (Los servidores que procesaron los eventos de esta tabla se muestran en la tabla tblComplianceFanout).  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contiene los servidores que procesaron un evento de cumplimiento. Esta tabla está estrechamente acoplada a la tabla tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contiene participantes actuales por servicio de chat y por servidor. Se mantiene según los eventos de conformidad con la Unión y la parte recibidos del servicio de chat persistente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contiene información de estado de cumplimiento para todo el grupo.  <br/> |
   

