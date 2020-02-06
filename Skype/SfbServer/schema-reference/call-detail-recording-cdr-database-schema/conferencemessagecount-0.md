---
title: Vista ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount almacena información acerca de cuántos mensajes envió un usuario a una conferencia. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815388"
---
# <a name="conferencemessagecount-view"></a>Vista ConferenceMessageCount
 
La vista ConferenceMessageCount almacena información acerca de cuántos mensajes envió un usuario a una conferencia. Esta vista se presentó en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista ConferenceMessageCount contiene todas las columnas de la [vista ConferenceSessionDetails](conferencesessiondetails.md) además de las columnas que se muestran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que envió el mensaje.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que envió los mensajes. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |identificador  <br/> |Espacio empresarial del usuario que envió los mensajes. Para obtener más información, consulte la [tabla de inquilinos](tenants.md) . <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Número de mensajes enviados por el usuario durante la sesión de conferencia.  <br/> |
   

