---
title: Cambios realizados por la preparación del dominio en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: La tabla siguiente muestra las entradas de control de acceso (ACE) que la preparación del dominio se crea en la raíz del dominio. Todas las ACE se heredan, a menos que se indique lo contrario.
ms.openlocfilehash: 3602e04082dbf4af9a2ab40fc3318761ebc08c21
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del dominio en Skype para Business Server
 
La tabla siguiente muestra las entradas de control de acceso (ACE) que la preparación del dominio se crea en la raíz del dominio. Todas las ACE se heredan, a menos que se indique lo contrario.
  
**ACE que se agrega a la raíz del dominio**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**Servicios de RTCHSUniversal**|**Usuarios autenticados**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Contenedor de lectura (no heredado)  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer el usuario restricciones de cuentas de usuario PropertySet  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer información Personal del usuario PropertySet  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer información General del usuario PropertySet  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer la información del público usuario PropertySet  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer PropertySet RTCUserSearchProperty-conjunto de usuarios  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |
|Usuario lectura PropertySet RTCPropertySet  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Escriba las direcciones de Proxy de usuario propiedad  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Escriba PropertySet RTCUserSearchProperty-conjunto de usuarios  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Escriba usuario PropertySet RTCPropertySet  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Lectura PropertySet DS-replicación-Get-cambios de todos los objetos de Active Directory  <br/> |No  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |
   
La tabla siguiente enumeran las ACE que crea la preparación del dominio en los tres contenedores integrados: usuarios, equipos y controladores de dominio. Todas las ACE se heredan, a menos que se indique lo contrario.
**ACE que se agregan a contenedores integrados**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Contenedor de lectura (no heredado)  <br/> |**Sí** <br/> |**Sí** <br/> |
   

