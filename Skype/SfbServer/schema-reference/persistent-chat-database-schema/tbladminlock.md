---
title: tblAdminLock
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: la tabla tblAdminLock contiene el bloqueo de administrador que se necesita para ejecutar algunos comandos de administrador.
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212666"
---
# <a name="tbladminlock"></a>tblAdminLock
 
la tabla tblAdminLock contiene el bloqueo de administrador que se necesita para ejecutar algunos comandos de administrador.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, no es nulo  <br/> |Bloqueo de la fecha de caducidad y la hora. El propietario puede ampliar este valor periódicamente.  <br/> |
|lockServerID  <br/> |int, no es nulo  <br/> |Identificador del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que posee el bloqueo.  <br/> |
   

