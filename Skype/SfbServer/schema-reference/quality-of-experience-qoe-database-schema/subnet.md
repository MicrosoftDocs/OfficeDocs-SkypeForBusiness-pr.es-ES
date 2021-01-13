---
title: Tabla Subnet
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831340"
---
# <a name="subnet-table"></a>Tabla Subnet
 
La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |entero  <br/> |Principal, Exterior  <br/> |Representación en número entero de la IP de la subred.  <br/> |
|**SubnetMask** <br/> |entero  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |entero  <br/> |Externo  <br/> |Se hace referencia a la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Descripción de la subred.  <br/> |
   

