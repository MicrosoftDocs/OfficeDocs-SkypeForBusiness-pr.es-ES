---
title: Cambios realizados por la preparación del dominio en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: En la siguiente tabla se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. A menos que se indique lo contrario, se heredan todas las ACE.
ms.openlocfilehash: afd6747590e09b0b86b42119ad34eb26eaf9d8db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296717"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del dominio en Skype empresarial Server
 
En la siguiente tabla se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. A menos que se indique lo contrario, se heredan todas las ACE.
  
**Entradas ACE agregadas a la raíz del dominio**

|**ENTRADA**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-servicios**|**Autenticados: usuarios**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Leer contenedor (no heredado)  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer usuario de la PropertySet de la cuenta de usuario-restricciones  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer usuario PropertySet información personal  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer usuario de la petición general-información  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer usuario PropertySet Public-Information  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer usuario PropertySet RTCUserSearchProperty-set  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |
|Leer el usuario PropertySet RTCPropertySet  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Escribir propiedad de usuario proxy: direcciones  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Escribir el usuario de la RTCUserSearchProperty  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Escribir el usuario PropertySet RTCPropertySet  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Lea el complemento de DS-replicación-obtener-cambios de todos los objetos de Active Directory  <br/> |No  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |
   
En la tabla siguiente se enumeran las ACE que crea el dominio de preparación en los tres contenedores integrados: usuarios, equipos y controladores de dominio. A menos que se indique lo contrario, se heredan todas las ACE.
**Entradas ACE agregadas a contenedores integrados**

|**ENTRADA**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Leer contenedor (no heredado)  <br/> |**Sí** <br/> |**Sí** <br/> |
   

