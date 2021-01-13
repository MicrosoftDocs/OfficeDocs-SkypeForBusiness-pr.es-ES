---
title: Cambios realizados por la preparación del dominio en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: En la tabla siguiente se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. Todas las ACE se heredan, salvo que se indique lo contrario.
ms.openlocfilehash: 46eaedb25ca245a5426314a8118be7443fb612e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831910"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del dominio en Skype Empresarial Server
 
En la tabla siguiente se enumeran las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. Todas las ACE se heredan, salvo que se indique lo contrario.
  
**Entradas ACE agregadas a la raíz del dominio**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Authenticated-Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Read Container (no se hereda)  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet User-Account-Restrictions  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet Personal-Information  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet General-Information  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet Public-Information  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet RTCUserSearchProperty-Set  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |
|Read User PropertySet RTCPropertySet  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Write User Property Proxy-Addresses  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Write User PropertySet RTCUserSearchProperty-Set  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Write User PropertySet RTCPropertySet  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Read PropertySet DS-Replication-Get-Changes de todos los objetos de Active Directory  <br/> |No  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |
   
En la tabla siguiente se enumeran las ACE que crea la preparación del dominio en los tres contenedores integrados: usuarios, equipos y controladores de dominio. Todas las ACE se heredan, salvo que se indique lo contrario.
**Entradas ACE agregadas a los contenedores integrados**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Read Container (no se hereda)  <br/> |**Sí** <br/> |**Sí** <br/> |
   

