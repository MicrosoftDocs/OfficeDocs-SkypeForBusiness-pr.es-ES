---
title: Vista ConferenceMessageCount
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813300"
---
# <a name="conferencemessagecount-view"></a>Vista ConferenceMessageCount
 
La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista ConferenceMessageCount contiene todas las columnas de la vista [ConferenceSessionDetails](conferencesessiondetails.md) además de las columnas que se enumeran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario que envió el mensaje.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que envió los mensajes. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Inquilino del usuario que envió los mensajes. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Número de mensajes que envió el usuario durante la sesión de conferencia.  <br/> |
   

