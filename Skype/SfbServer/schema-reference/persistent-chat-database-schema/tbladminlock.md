---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814698"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, not null  <br/> |Bloquear la fecha y la hora de expiración. El propietario puede extender este valor de forma periódica.  <br/> |
|lockServerID  <br/> |int, not null  <br/> |IDENTIFICADOR del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad que posee el bloqueo.  <br/> |
   

