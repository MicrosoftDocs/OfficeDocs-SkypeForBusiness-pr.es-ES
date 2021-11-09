---
title: Tabla ConferenceMessageCount en Skype Empresarial Server 2015
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia se representa mediante varios registros en esta tabla; un registro para cada usuario.
ms.openlocfilehash: 4c2db60023594a86d12be16be84375311ce089e0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863457"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabla ConferenceMessageCount en Skype Empresarial Server 2015
 
Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia se representa mediante varios registros en esta tabla; un registro para cada usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Externa  <br/> |Hora de la instancia de conferencia. Se usa junto con **SessionIdSeq para** identificar de forma única una instancia de conferencia. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal, Externa  <br/> |Número de identificación de la instancia de conferencia. Se usa junto con **SessionIdTime para** identificar de forma única una instancia de conferencia. Vea la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**UserId** <br/> |Entero  <br/> |Externo  <br/> |Número único que identifica a este usuario, al que se hace referencia desde la [tabla Usuarios](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Número de mensajes enviados por este usuario durante esta conferencia.  <br/> |
   

