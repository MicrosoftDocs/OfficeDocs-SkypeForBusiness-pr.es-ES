---
title: Tabla subred
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: abbc1317c6a0db1da0b52e5b0eef56abbfad06f5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834848"
---
# <a name="subnet-table"></a>Tabla subred
 
La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Representación en número entero de la IP de la subred.  <br/> |
|**SubnetMask** <br/> |Entero  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |Entero  <br/> |Externo  <br/> |Se hace referencia desde la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Descripción de la subred.  <br/> |
   

