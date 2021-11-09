---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: 1527cee53bc93c9b26a1cb961bba0a7fa53ae2e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852844"
---
# <a name="tbladminlock"></a>tblAdminLock
 
La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, no NULL  <br/> |Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.  <br/> |
|lockServerID  <br/> |int, no NULL  <br/> |Identificador del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad que posee el bloqueo.  <br/> |
   

