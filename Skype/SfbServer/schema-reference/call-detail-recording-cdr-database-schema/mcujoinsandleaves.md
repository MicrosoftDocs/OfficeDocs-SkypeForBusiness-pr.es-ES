---
title: Tabla McuJoinsAndLeaves en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Cada registro de esta tabla contiene detalles de la llamada acerca de una combinación de una Unión de usuario o de un servidor de conferencia y un servidor de conferencia. Por ejemplo, si un usuario se une a una conferencia que incluye conferencias web y elementos de audio/vídeo, se creará un registro para la combinación de conferencias por Internet de ese usuario y otro para la combinación de audio y videoconferencias del usuario.
ms.openlocfilehash: 7eb2e8bccafcbd585c66cb77f2ba18a96c842d60
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815088"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabla McuJoinsAndLeaves en Skype empresarial Server 2015
 
Cada registro de esta tabla contiene detalles de la llamada acerca de una combinación de una Unión de usuario o de un servidor de conferencia y un servidor de conferencia. Por ejemplo, si un usuario se une a una conferencia que incluye conferencias web y elementos de audio/vídeo, se creará un registro para la combinación de conferencias por Internet de ese usuario y otro para la combinación de audio y videoconferencias del usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Hora de la instancia de conferencia. Se usa junto con **SessionIdSeq** para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la instancia de la Conferencia. Se usa junto con **SessionIdTime** para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**Iddeusuario** <br/> |int  <br/> |Principal, extranjero  <br/> |Número único que identifica a este usuario. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |Si un usuario ha iniciado sesión en varios equipos o dispositivos a la vez, McuUserInstancerá de forma exclusiva la combinación de usuario y dispositivo.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si el usuario se une desde una RTC o no.  <br/> |
|**McuId** <br/> |int  <br/> |Principal, extranjero  <br/> |Número único que identifica este servidor de conferencia. Para obtener más información, consulte la [tabla MCU en Skype empresarial Server 2015](mcus.md) . <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Extranjero  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Extranjero  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |El momento en que este usuario se une a este servidor de conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Hora en que este usuario abandona este servidor de conferencia.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Extranjero  <br/> |Identificador que especifica el número de versión del uso de software de cliente en la Conferencia. Para obtener más información, consulte la [tabla ClientVersions en Skype empresarial Server 2015](clientversions.md) . <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   

