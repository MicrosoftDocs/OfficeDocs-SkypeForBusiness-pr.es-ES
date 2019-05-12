---
title: Tabla Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: En la tabla de subred es una tabla de apoyo. Cada registro representa una subred definida en la configuración de configuración de red.
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907069"
---
# <a name="subnet-table"></a>Tabla Subnet
 
En la tabla de subred es una tabla de apoyo. Cada registro representa una subred definida en la configuración de configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Principal, externa  <br/> |Representación de enteros para la dirección IP de la subred.  <br/> |
|**Máscara de subred** <br/> |int  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||La descripción de la subred.  <br/> |
   

