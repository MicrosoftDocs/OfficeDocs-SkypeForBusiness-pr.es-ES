---
title: Cambios realizados por la preparación del dominio en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: En la siguiente tabla se enumera las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. Todas las ACE se heredan, a menos que se indique lo contrario.
ms.openlocfilehash: ccb05f122e60c66bccefa3e8504e60639612cba0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907146"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del dominio en Skype para Business Server
 
En la siguiente tabla se enumera las entradas de control de acceso (ACE) que crea la preparación del dominio en la raíz del dominio. Todas las ACE se heredan, a menos que se indique lo contrario.
  
**Entradas ACE agregadas a la raíz del dominio**

|**as**|**Grupo de UserReadOnly RTCUniversal**|**Grupo de ServerReadOnly RTCUniversal**|**RTCUniversal UserAdmins**|**Servicios de RTCHSUniversal**|**Usuarios autenticados**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Contenedor de lectura (no heredado)  <br/> |**Sí** <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer el usuario restricciones de cuentas de usuario de PropertySet  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Usuario PropertySet Personal-Information de lectura  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Usuario PropertySet General-Information de lectura  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Usuario PropertySet Public-Information de lectura  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leer PropertySet RTCUserSearchProperty-conjunto de usuarios  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |
|Usuario PropertySet RTCPropertySet de lectura  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Escribir direcciones de Proxy de usuario (propiedad)  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Escribir PropertySet RTCUserSearchProperty-conjunto de usuarios  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Usuario PropertySet RTCPropertySet de escritura  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |No  <br/> |
|Lectura PropertySet DS-Replication-Get-Changes de todos los objetos de Active Directory  <br/> |No  <br/> |No  <br/> |No  <br/> |**Sí** <br/> |No  <br/> |
   
En la siguiente tabla se enumera las ACE que crea la preparación del dominio en los tres contenedores integrados: los usuarios, equipos y controladores de dominio. Todas las ACE se heredan, a menos que se indique lo contrario.
**Entradas ACE agregadas a los contenedores integrados**

|**as**|**Grupo de UserReadOnly RTCUniversal**|**Grupo de ServerReadOnly RTCUniversal**|
|:-----|:-----|:-----|
|Contenedor de lectura (no heredado)  <br/> |**Sí** <br/> |**Sí** <br/> |
   

