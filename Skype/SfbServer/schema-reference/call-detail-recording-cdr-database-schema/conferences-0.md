---
title: Vista de conferencias
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: La vista de las conferencias almacena información acerca de las conferencias. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 008895e43fb62377f256cb64fdd5f1b24ed0768e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901348"
---
# <a name="conferences-view"></a>Vista de conferencias
 
La vista de las conferencias almacena información acerca de las conferencias. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de la conferencia. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Se usa para conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo ConferenceUri, pero un ConfInstance diferente.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Hora de inicio de la conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Hora de finalización de la conferencia.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI del usuario que organizó la conferencia.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que organizó la conferencia. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que organizó la conferencia. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |Nombre de dominio completo del grupo de servidores que hospedan la conferencia.  <br/> |
|**Marca** <br/> |smallint  <br/> |Máscara de bits que contiene los atributos de conferencia. Los valores posibles son:  <br/> 0 x 01 - transacciones sintéticas  <br/> |
   

