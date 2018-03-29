---
title: Tabla de ubicaciones en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa una referencia de ubicación de una llamada de emergencia, al igual que una llamada E9-1-1.
ms.openlocfilehash: b15e7f0b7930871b97dc3341a47153965529810e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Tabla de ubicaciones en Skype para Business Server 2015
 
Cada registro representa una referencia de ubicación de una llamada de emergencia, al igual que una llamada E9-1-1.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**Ubicación** <br/> |nvarchar (max)  <br/> ||Ubicación de llamada de emergencia.  <br/> |
   

