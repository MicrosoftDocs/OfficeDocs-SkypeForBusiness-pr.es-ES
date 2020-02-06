---
title: Tabla Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla de subred es una tabla de soporte técnico. Cada registro representa una subred definida en la opción de configuración de red.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805208"
---
# <a name="subnet-table"></a>Tabla Subnet
 
La tabla de subred es una tabla de soporte técnico. Cada registro representa una subred definida en la opción de configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Principal, extranjero  <br/> |Representación de enteros de la IP de subred.  <br/> |
|**Máscaradesubred** <br/> |int  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Extranjero  <br/> |Se hace referencia a ella desde la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||La descripción de la subred.  <br/> |
   

