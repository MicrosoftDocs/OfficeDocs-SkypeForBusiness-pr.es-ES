---
title: Vista de conferencias
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: La vista de conferencias almacena información acerca de las conferencias. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 98fbf972badeb6cf3b179c8fa408626f2224f5b3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferences-view"></a>Vista de conferencias
 
La vista de conferencias almacena información acerca de las conferencias. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza junto con SessionIdSeq para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con SessionIdTime para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI para la conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de la conferencia URI. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Se utiliza para las conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo ConferenceUri pero un ConfInstance diferentes.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Hora de inicio de la conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Hora de fin de la conferencia.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI del usuario que ha organizado la conferencia.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha organizado la conferencia. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Inquilinos del usuario que ha organizado la conferencia. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**Grupo de servidores** <br/> |nvarchar(256)  <br/> |Nombre de dominio completo del grupo de servidores que alojan la conferencia.  <br/> |
|**Indicador** <br/> |smallint  <br/> |Máscara de bits que contiene los atributos de la conferencia. Los posibles valores son:  <br/> 0 x 01 - transacciones sintéticas  <br/> |
   

