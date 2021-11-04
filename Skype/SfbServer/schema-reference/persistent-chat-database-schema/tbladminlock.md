---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: df040a4a6d503e4ea8f7327e6ac50b5ae411cf60
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746536"
---
# <a name="tbladminlock"></a>tblAdminLock
 
La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, no NULL  <br/> |Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.  <br/> |
|lockServerID  <br/> |int, no NULL  <br/> |Identificador del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad que posee el bloqueo.  <br/> |
   

