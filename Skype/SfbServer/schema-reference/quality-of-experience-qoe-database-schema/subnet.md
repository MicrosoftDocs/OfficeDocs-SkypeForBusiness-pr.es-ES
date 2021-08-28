---
title: Tabla subred
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
ms.localizationpriority: medium
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
ms.openlocfilehash: e7fd43963414b24ed684d8f1efa59c7e634839bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613800"
---
# <a name="subnet-table"></a>Tabla subred
 
La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Representación en número entero de la IP de la subred.  <br/> |
|**SubnetMask** <br/> |Entero  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |Entero  <br/> |Externo  <br/> |Se hace referencia desde la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Descripción de la subred.  <br/> |
   

