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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: En la siguiente tabla se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. A menos que se indique lo contrario, se heredan todas las ACE.
ms.openlocfilehash: 8a087dfbbd8b670467727803f996694a816cc065
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815548"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del dominio en Skype empresarial Server
 
En la siguiente tabla se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. A menos que se indique lo contrario, se heredan todas las ACE.
  
**Entradas ACE agregadas a la raíz del dominio**

|**ENTRADA**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-servicios**|**Autenticados: usuarios**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Leer contenedor (no heredado)  <br/> |**Afirmativa** <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |
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
|Leer contenedor (no heredado)  <br/> |**Afirmativa** <br/> |**Sí** <br/> |
   

