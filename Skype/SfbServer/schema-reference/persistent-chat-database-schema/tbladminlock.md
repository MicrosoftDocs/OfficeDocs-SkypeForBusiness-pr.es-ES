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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295527"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, not null  <br/> |Bloquear la fecha y la hora de expiración. El propietario puede extender este valor de forma periódica.  <br/> |
|lockServerID  <br/> |int, not null  <br/> |IDENTIFICADOR del servidor que posee el bloqueo.  <br/> |
|lockActorID  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad que posee el bloqueo.  <br/> |
   

