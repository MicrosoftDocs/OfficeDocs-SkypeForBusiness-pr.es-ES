---
title: Tabla FocusJoinsAndLeaves en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Cada registro de esta tabla contiene la información de CDR acerca de join de un usuario y la información de licencia para una conferencia. Cada conferencia se representa en esta tabla mediante un registro cada vez que un usuario se une a y sale de la conferencia.
ms.openlocfilehash: f07790af63de562672cefc8d8fbd09d75dff1eec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabla FocusJoinsAndLeaves en Skype para Business Server 2015
 
Cada registro de esta tabla contiene la información de CDR acerca de join de un usuario y la información de licencia para una conferencia. Cada conferencia se representa en esta tabla mediante un registro cada vez que un usuario se une a y sale de la conferencia.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la instancia de la conferencia. Se utiliza junto con **SessionIdSeq** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la instancia de la conferencia. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una instancia de la conferencia. Consulte la [tabla de conferencias en Skype para Business Server 2015](conferences.md) para obtener más información. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ID de usuario** <br/> |int  <br/> |Externa  <br/> |Número único que identifica este usuario, se hace referenciado en la [tabla usuarios](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Si un usuario inicia sesión en varios equipos o dispositivos al mismo tiempo, **UserInstance** se utiliza para identificar de forma exclusiva la combinación usuario/dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Si los usuarios han iniciado sesión interna o no.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Función de este usuario en la conferencia como moderador o asistente.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |El tiempo que este usuario une a la conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |El tiempo que este usuario abandona la conferencia.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versión del software de cliente del usuario, al que hace referencia a la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificador único global (GUID) del extremo que se utiliza en la conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

