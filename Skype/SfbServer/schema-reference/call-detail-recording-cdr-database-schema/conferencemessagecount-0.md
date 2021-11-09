---
title: Vista ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 1308b0e9aeb8954df8010d0c1d55036eff1a3dac
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856527"
---
# <a name="conferencemessagecount-view"></a>Vista ConferenceMessageCount
 
La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista ConferenceMessageCount contiene todas las columnas de la [vista ConferenceSessionDetails](conferencesessiondetails.md) además de las columnas que se enumeran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario que envió el mensaje.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que envió los mensajes. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Inquilino del usuario que envió los mensajes. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Número de mensajes que envió el usuario durante la sesión de conferencia.  <br/> |
   

