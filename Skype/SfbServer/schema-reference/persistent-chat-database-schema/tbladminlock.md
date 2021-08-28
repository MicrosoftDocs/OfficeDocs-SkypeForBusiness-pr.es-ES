---
title: tblAdminLock
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
ms.localizationpriority: medium
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: 478ca06da81ddc8144dbd712885ecdbde5c8bc8d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633514"
---
# <a name="tbladminlock"></a>tblAdminLock
 
La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, no NULL  <br/> |Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.  <br/> |
|lockServerID  <br/> |int, no NULL  <br/> |Identificador del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad que posee el bloqueo.  <br/> |
   

