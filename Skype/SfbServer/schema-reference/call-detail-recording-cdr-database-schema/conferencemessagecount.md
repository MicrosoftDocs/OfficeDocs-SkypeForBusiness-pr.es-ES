---
title: Tabla ConferenceMessageCount en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por el usuario. Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815378"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabla ConferenceMessageCount en Skype empresarial Server 2015
 
Cada registro de esta tabla representa un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por el usuario. Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Hora de la instancia de conferencia. Se usa junto con **SessionIdSeq** para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación para identificar la instancia de la Conferencia. Se usa junto con **SessionIdTime** para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, consulte la [tabla conferencias en Skype empresarial Server 2015](conferences.md) . <br/> |
|**Iddeusuario** <br/> |int  <br/> |Extranjero  <br/> |Número único que identifica a este usuario, al que se hace referencia en la [tabla usuarios](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |El número de mensajes enviados por este usuario durante esta conferencia.  <br/> |
   

