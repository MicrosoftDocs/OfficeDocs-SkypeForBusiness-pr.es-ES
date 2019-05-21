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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla de subred es una tabla de soporte técnico. Cada registro representa una subred definida en la opción de configuración de red.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294638"
---
# <a name="subnet-table"></a>Tabla Subnet
 
La tabla de subred es una tabla de soporte técnico. Cada registro representa una subred definida en la opción de configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Principal, extranjero  <br/> |Representación de enteros de la IP de subred.  <br/> |
|**Máscaradesubred** <br/> |int  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Extranjero  <br/> |Se hace referencia a ella desde la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||La descripción de la subred.  <br/> |
   

