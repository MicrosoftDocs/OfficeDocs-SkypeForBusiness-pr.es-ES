---
title: Vista Conferencias
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
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: La vista Conferencias almacena información sobre las conferencias. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 500a03e85a3339d28227a5b65d5a3c206fc34723
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828633"
---
# <a name="conferences-view"></a>Vista Conferencias
 
La vista Conferencias almacena información sobre las conferencias. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Número de identificador para identificar la sesión. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo del URI de la conferencia. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Se usa en conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo ConferenceUri, pero un ConfInstance distinto.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Hora de inicio de la conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Hora de finalización de la conferencia.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI del usuario que organizó la conferencia.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que organizó la conferencia. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que organizó la conferencia. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |Nombre de dominio completo del grupo que hospedó la conferencia.  <br/> |
|**Flag** <br/> |smallint  <br/> |Máscara de bits que contiene atributos de la conferencia. Los valores posibles son:  <br/> 0X01: transacción sintética  <br/> |
   

