---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene el bloqueo del administrador que se necesita para ejecutar algunos comandos de administrador.
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contiene el bloqueo del administrador que se necesita para ejecutar algunos comandos de administrador.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |fecha y hora, no nulo  <br/> |Bloqueo de fecha de vencimiento y la hora. El propietario puede extender este valor periódicamente.  <br/> |
|lockServerID  <br/> |int, no nulo  <br/> |Id. del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que posee el bloqueo.  <br/> |
   

