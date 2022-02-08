---
title: Tabla subred
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 92e582332e0e7c20c443a57c4ba0cc6abbb66cad
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394602"
---
# <a name="subnet-table"></a>Tabla subred
 
La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Representación en número entero de la IP de la subred.  <br/> |
|**SubnetMask** <br/> |Entero  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |Entero  <br/> |Externo  <br/> |Se hace referencia desde la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Descripción de la subred.  <br/> |
   

