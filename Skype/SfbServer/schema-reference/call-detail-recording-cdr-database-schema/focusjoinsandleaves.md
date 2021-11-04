---
title: Tabla FocusJoinsAndLeaves en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Cada registro de esta tabla contiene la información de CDR sobre la unión y la licencia de un usuario para una conferencia. Cada conferencia se representa en esta tabla mediante un registro por cada vez que un usuario se une y sale de la conferencia.
ms.openlocfilehash: ca5ba1776478566c57d8e5992b86db2dd300613b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777790"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabla FocusJoinsAndLeaves en Skype Empresarial Server 2015
 
Cada registro de esta tabla contiene la información de CDR sobre la unión y la licencia de un usuario para una conferencia. Cada conferencia se representa en esta tabla mediante un registro por cada vez que un usuario se une y sale de la conferencia.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Externa  <br/> |Hora de la instancia de conferencia. Se usa junto con **SessionIdSeq para** identificar de forma única una instancia de conferencia. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal, Externa  <br/> |Número de identificación de la instancia de conferencia. Se usa junto con **SessionIdTime para** identificar de forma única una instancia de conferencia. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**DialogSessionIdSeq** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**UserId** <br/> |Entero  <br/> |Externo  <br/> |Número único que identifica a este usuario, al que se hace referencia desde la [tabla Usuarios](users.md).  <br/> |
|**FocusUserInstance** <br/> |Entero  <br/> ||Si un usuario ha iniciado sesión en varios equipos o dispositivos al mismo tiempo, **UserInstance** se usa para identificar de forma única la combinación usuario/dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Si el usuario inició sesión desde interno o no.  <br/> |
|**UserRole** <br/> |Entero  <br/> | <br/> |Rol de este usuario en la conferencia, como moderador o asistente.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |La hora en que este usuario se une a la conferencia.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |La hora en que este usuario abandona la conferencia.  <br/> |
|**ClientVerId** <br/> |Entero  <br/> |Externo  <br/> |Versión del software cliente del usuario, a la que se hace referencia a la [tabla ClientVersions en Skype Empresarial Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificador único global (GUID) del extremo usado en la conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

