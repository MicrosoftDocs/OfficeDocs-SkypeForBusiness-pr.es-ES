---
title: Tabla FocusJoinsAndLeaves en Skype empresarial Server 2015
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
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Cada registro de esta tabla contiene la información de CDR de la combinación de un usuario y la deja la información para una conferencia. Cada conferencia está representada en esta tabla un registro para cada vez que un usuario se une y sale de la Conferencia.
ms.openlocfilehash: ac5e2b7316dd7d3477d76675d3a3960154b90f35
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815188"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabla FocusJoinsAndLeaves en Skype empresarial Server 2015
 
Cada registro de esta tabla contiene la información de CDR de la combinación de un usuario y la deja la información para una conferencia. Cada conferencia está representada en esta tabla un registro para cada vez que un usuario se une y sale de la Conferencia.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Hora de la instancia de conferencia. Se usa junto con **SessionIdSeq** para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la instancia de la Conferencia. Se usa junto con **SessionIdTime** para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión. para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**Iddeusuario** <br/> |int  <br/> |Extranjero  <br/> |Número único que identifica a este usuario, al que se hace referencia en la [tabla usuarios](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Si un usuario ha iniciado sesión en varios equipos o dispositivos al mismo tiempo, **UserInstance** se usa para identificar de forma inequívoca la combinación de usuario y dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Si el usuario ha iniciado sesión en forma interna o no.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |El rol de este usuario en la Conferencia, como moderador o asistente.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |El momento en que este usuario se une a la Conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Hora en que este usuario abandona la Conferencia.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Extranjero  <br/> |Versión del software de cliente del usuario, al que se hace referencia en la [tabla ClientVersions en Skype empresarial Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |Identificador  <br/> ||Identificador único global (GUID) del extremo que se usa en la Conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   

