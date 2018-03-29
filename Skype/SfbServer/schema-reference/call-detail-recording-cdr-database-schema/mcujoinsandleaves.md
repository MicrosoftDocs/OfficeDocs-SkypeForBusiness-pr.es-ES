---
title: Tabla McuJoinsAndLeaves en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Cada registro de esta tabla contiene detalles de la llamada acerca de una combinación de un servidor de conferencias o vacaciones y combinación de usuario. Por ejemplo, si un usuario une a una conferencia que incluya elementos de audio y vídeo y conferencias por Internet, se crearía un registro de combinación de conferencia web del usuario y se creará otro registro de combinación de conferencia de audio y vídeo del usuario.
ms.openlocfilehash: 153da84534dae4a9ad2287c355b93a4477003e6f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabla McuJoinsAndLeaves en Skype para Business Server 2015
 
Cada registro de esta tabla contiene detalles de la llamada acerca de una combinación de un servidor de conferencias o vacaciones y combinación de usuario. Por ejemplo, si un usuario une a una conferencia que incluya elementos de audio y vídeo y conferencias por Internet, se crearía un registro de combinación de conferencia web del usuario y se creará otro registro de combinación de conferencia de audio y vídeo del usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la instancia de la conferencia. Se utiliza junto con **SessionIdSeq** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la instancia de la conferencia. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**ID de usuario** <br/> |int  <br/> |Principal, externa  <br/> |Número único que identifica este usuario. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |Si un usuario inicia sesión en varios equipos o dispositivos a la vez, McuUserInstance identifica la combinación usuario/dispositivo.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si el usuario se une desde un PSTN o no.  <br/> |
|**McuId** <br/> |int  <br/> |Principal, externa  <br/> |Número único que identifica este servidor de conferencia. Consulte la [tabla de MCU en Skype para Business Server 2015](mcus.md) para obtener más información. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Externa  <br/> |Hora de la solicitud de sesión. Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |El tiempo que este usuario une a este servidor de conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |El tiempo que este usuario deja este servidor de conferencia.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externa  <br/> |Identificador que especifica el número de versión del software de cliente que se utilice en la conferencia. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

