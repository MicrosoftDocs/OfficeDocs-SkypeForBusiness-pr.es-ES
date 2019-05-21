---
title: Vista VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información sobre sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295667"
---
# <a name="voipdetails-view"></a>Vista VoIPDetails
 
La vista VoIPDetails almacena información sobre sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP. Esta vista se presentó en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista VoIPDetails contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) además de las columnas que se muestran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)  <br/> |URI de teléfono del usuario que inició la sesión.  <br/> |
|**Teléfono** <br/> |nvarchar (450)  <br/> |URI de teléfono del usuario que se unió a la sesión.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |URI del usuario que desconectó la sesión.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha desconectado la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario que desconectó la sesión.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |URI de teléfono del usuario que desconectó la sesión.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que inició la sesión.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que se unió a la sesión.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que inició la sesión.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que se unió a la sesión.  <br/> |
   

