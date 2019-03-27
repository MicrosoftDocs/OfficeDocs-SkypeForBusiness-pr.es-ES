---
title: Tabla FocusJoinsAndLeaves en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Cada registro de esta tabla contiene la información de CDR acerca de la combinación de un usuario y deje información para una conferencia. Cada conferencia se representa en esta tabla mediante un registro para cada vez que un usuario se une a y abandona la conferencia.
ms.openlocfilehash: dea6ae9e66416da41c9ca5df0d6a8c3e61550238
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881231"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabla FocusJoinsAndLeaves en Skype para Business Server 2015
 
Cada registro de esta tabla contiene la información de CDR acerca de la combinación de un usuario y deje información para una conferencia. Cada conferencia se representa en esta tabla mediante un registro para cada vez que un usuario se une a y abandona la conferencia.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la instancia de conferencia. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la instancia de conferencia. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de las conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión. vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**UserId** <br/> |int  <br/> |Externa  <br/> |Número único que identifica a este usuario, de la [tabla de usuarios](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Si un usuario inicia sesión en varios equipos o dispositivos a la vez, **UserInstance** se usa para identificar de forma única la combinación usuario/dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Si el usuario iniciado de manera interna o no.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Rol del usuario en la conferencia, por ejemplo moderador o asistente.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |El tiempo de este usuario se une a la conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Hora a la que este usuario sale de la conferencia.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versión de software de cliente del usuario, al que hace referencia a la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificador único global (GUID) del extremo usado en la conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

