---
title: Tabla ConferenceMessageCount en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro de esta tabla representa a un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813280"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabla ConferenceMessageCount en Skype Empresarial Server 2015
 
Cada registro de esta tabla representa a un usuario en una conferencia de mensajería instantánea e incluye el número de mensajes enviados por ese usuario. Cada conferencia está representada por varios registros en esta tabla; un registro para cada usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Externa  <br/> |Hora de la instancia de conferencia. Se usa junto con **SessionIdSeq para** identificar de forma única una instancia de conferencia. Consulte la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Principal, Externa  <br/> |Número de identificación de la instancia de conferencia. Se usa junto con **SessionIdTime para** identificar de forma única una instancia de conferencia. Consulte la [tabla Conferencias de Skype Empresarial Server 2015](conferences.md) para obtener más información. <br/> |
|**UserId** <br/> |entero  <br/> |Externo  <br/> |Número único que identifica a este usuario, al que se hace referencia desde la [tabla Usuarios](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |El número de mensajes enviados por este usuario durante esta conferencia.  <br/> |
   

