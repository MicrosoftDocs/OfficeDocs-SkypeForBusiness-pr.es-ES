---
title: Tabla McuJoinsAndLeaves en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Cada registro de esta tabla contiene detalles de llamadas sobre una combinación de un servidor de conferencias o deje y join de usuario. Por ejemplo, si un usuario se une a una conferencia que incluye elementos de audio y vídeo y de conferencia web, se creará un registro para unirse a conferencia de web del usuario y se crearán otro registro para unirse a conferencias de audio y vídeo del usuario.
ms.openlocfilehash: d6bcd51e9c0e5832939004647348abe7368a2e43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930300"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabla McuJoinsAndLeaves en Skype para Business Server 2015
 
Cada registro de esta tabla contiene detalles de llamadas sobre una combinación de un servidor de conferencias o deje y join de usuario. Por ejemplo, si un usuario se une a una conferencia que incluye elementos de audio y vídeo y de conferencia web, se creará un registro para unirse a conferencia de web del usuario y se crearán otro registro para unirse a conferencias de audio y vídeo del usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la instancia de conferencia. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la instancia de conferencia. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**UserId** <br/> |int  <br/> |Principal, externa  <br/> |Número único que identifica a este usuario. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |Si un usuario inicia sesión en varios equipos o dispositivos a la vez, McuUserInstance identifica de forma única la combinación usuario/dispositivo.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si el usuario se está uniendo desde una RTC o no.  <br/> |
|**McuId** <br/> |int  <br/> |Principal, externa  <br/> |Número único que identifica este servidor de conferencia. Consulte la [tabla de MCU en Skype para Business Server 2015](mcus.md) para obtener más información. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Externa  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |El tiempo de este usuario se une a este servidor de conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Hora a la que este usuario sale de este servidor de conferencia.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externa  <br/> |Identificador que especifica el número de versión del software de cliente que se use en la conferencia. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

