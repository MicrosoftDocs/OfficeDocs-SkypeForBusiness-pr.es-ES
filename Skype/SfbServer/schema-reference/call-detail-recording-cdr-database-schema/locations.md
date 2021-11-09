---
title: Tabla Ubicaciones en Skype Empresarial Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa una referencia de ubicación en una llamada de emergencia, como una llamada E9-1-1.
ms.openlocfilehash: 4a008ae472dd9726af7c85f89d069bc49bd2ce4d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847053"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Tabla Ubicaciones en Skype Empresarial Server 2015
 
Cada registro representa una referencia de ubicación en una llamada de emergencia, como una llamada E9-1-1.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Número del identificador para identificar la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**Location** <br/> |nvarchar(max)  <br/> ||Ubicación de una llamada de emergencia.  <br/> |
   

