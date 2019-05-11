---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: la tabla tblAdminLock contiene el bloqueo de administrador que se necesita para ejecutar algunos comandos de administrador.
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929815"
---
# <a name="tbladminlock"></a>tblAdminLock
 
la tabla tblAdminLock contiene el bloqueo de administrador que se necesita para ejecutar algunos comandos de administrador.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, no es nulo  <br/> |Bloqueo de la fecha de caducidad y la hora. El propietario puede ampliar este valor periódicamente.  <br/> |
|lockServerID  <br/> |int, no es nulo  <br/> |Identificador del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que posee el bloqueo.  <br/> |
   

