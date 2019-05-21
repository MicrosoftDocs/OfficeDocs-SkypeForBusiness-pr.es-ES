---
title: Vista conferencias
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: La vista conferencias almacena información sobre las conferencias. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 2e49a60be1651c34fb874c62bbee8c993eb00983
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296465"
---
# <a name="conferences-view"></a>Vista conferencias
 
La vista conferencias almacena información sobre las conferencias. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI de la Conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de la Conferencia. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**ConfInstance** <br/> |identificador  <br/> |Se usa para conferencias periódicas. Cada instancia de una conferencia periódica tiene el mismo ConferenceUri pero un ConfInstance diferente.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Hora de inicio de la Conferencia.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Hora de finalización de la Conferencia.  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que organizó la Conferencia.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que organizó la Conferencia. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario que organizó la Conferencia. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |Nombre de dominio completo del grupo que ha hospedado la Conferencia.  <br/> |
|**Fdisableautoindexingonschemaupdate** <br/> |smallint  <br/> |Máscara de bits que contiene atributos de conferencia. Los valores posibles son:  <br/> 0X01: transacción sintética  <br/> |
   

