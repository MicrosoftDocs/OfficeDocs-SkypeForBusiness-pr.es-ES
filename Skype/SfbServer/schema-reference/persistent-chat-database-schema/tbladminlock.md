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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809890"
---
# <a name="tbladminlock"></a>tblAdminLock
 
La tabla tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, no NULL  <br/> |Fecha y hora de expiración del bloqueo. El propietario puede ampliar este valor de manera regular.  <br/> |
|lockServerID  <br/> |int, no NULL  <br/> |Identificador del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad que posee el bloqueo.  <br/> |
   

