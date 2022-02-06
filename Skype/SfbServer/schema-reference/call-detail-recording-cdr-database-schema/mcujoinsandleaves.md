---
title: Tabla McuJoinsAndLeaves en Skype Empresarial Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 'Cada registro de esta tabla contiene detalles de llamadas sobre una combinación de un servidor de conferencia o unión de usuario o de licencia. Por ejemplo, si un usuario se une a una conferencia que incluye conferencias web y elementos de audio y vídeo, se crearía un registro para la unión a conferencias web de ese usuario y se crearía otro registro para la unión a conferencias de audio y vídeo del usuario.'
---

# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabla McuJoinsAndLeaves en Skype Empresarial Server 2015
 
Cada registro de esta tabla contiene detalles de llamadas sobre una combinación de un servidor de conferencia o unión de usuario o de licencia. Por ejemplo, si un usuario se une a una conferencia que incluye conferencias web y elementos de audio y vídeo, se crearía un registro para la unión a conferencias web de ese usuario y se crearía otro registro para la unión a conferencias de audio y vídeo del usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Externa  <br/> |Hora de la instancia de conferencia. Se usa junto con **SessionIdSeq para** identificar de forma única una instancia de conferencia. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal, Externa  <br/> |Número de identificación de la instancia de conferencia. Se usa junto con **SessionIdTime para** identificar de forma única una instancia de conferencia. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**UserId** <br/> |Entero  <br/> |Principal, Externa  <br/> |Número único que identifica a este usuario. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**McuUserInstance** <br/> |Entero  <br/> |Principal  <br/> |Si un usuario ha iniciado sesión en varios equipos o dispositivos a la vez, McuUserInstance identifica de forma única la combinación de usuario y dispositivo.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si el usuario se une desde una RTC o no.  <br/> |
|**McuId** <br/> |Entero  <br/> |Principal, Externa  <br/> |Número único que identifica este servidor de conferencias. Vea la [tabla Mcus en Skype Empresarial Server 2015](mcus.md) para obtener más información. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Externo  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |Entero  <br/> |Externo  <br/> |Número con el que se identifica la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |La hora en que este usuario se une a este servidor de conferencias.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |La hora en que este usuario deja este servidor de conferencias.  <br/> |
|**ClientVerId** <br/> |Entero  <br/> |Externo  <br/> |Identificador que especifica el número de versión del uso del software cliente en la conferencia. Vea la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md) para obtener más información. <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

