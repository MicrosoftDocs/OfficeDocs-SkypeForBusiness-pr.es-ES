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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
ms.openlocfilehash: 10df067fe95f244aea2fa9987b4962efaef9fbe32fbbfbe5b0e9f6ed9f6392e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279966"
---
# <a name="subnet-table"></a>Tabla subred
 
La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Representación en número entero de la IP de la subred.  <br/> |
|**SubnetMask** <br/> |Entero  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |Entero  <br/> |Externo  <br/> |Se hace referencia desde la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Descripción de la subred.  <br/> |
   

