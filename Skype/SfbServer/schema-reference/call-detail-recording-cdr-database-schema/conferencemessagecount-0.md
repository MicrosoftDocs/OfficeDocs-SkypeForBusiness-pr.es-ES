---
title: Vista ConferenceMessageCount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount almacena información acerca de la cantidad de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: ce94cd13637b70b87a92fd688ca8ce8aefd2c69e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901418"
---
# <a name="conferencemessagecount-view"></a>Vista ConferenceMessageCount
 
La vista ConferenceMessageCount almacena información acerca de la cantidad de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista ConferenceMessageCount todas las columnas en la [vista ConferenceSessionDetails](conferencesessiondetails.md) contiene además en las columnas enumeradas a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario que envió el mensaje.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que envía los mensajes. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Inquilino del usuario que envió los mensajes. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Número de mensajes enviados por el usuario durante la sesión de conferencia.  <br/> |
   

