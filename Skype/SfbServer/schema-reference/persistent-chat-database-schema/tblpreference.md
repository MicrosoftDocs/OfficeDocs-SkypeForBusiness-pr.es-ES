---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Lo usan generalmente los clientes anteriores a Lync 2013.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814558"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contiene las preferencias de cliente de los usuarios. Lo usan generalmente los clientes anteriores a Lync 2013.

**Columnas**


| **Columna**            | **Tipo**                        | **Descripción**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), not null  <br/> | Etiqueta con un formato como: \<URI del SIP del usuario\>                   |
| prefSeqID  <br/>      | int, not null  <br/>            | Un número secuencial (por etiqueta) para fines de control de versiones.  <br/> |
| prefContent  <br/>    | nvarchar (Max)  <br/>           | Contenido codificado.  <br/>                                         |
| lastModifiedBy  <br/> | int, not null  <br/>            | IDENTIFICADOR de la identidad que actualizó la preferencia.  <br/>         |

**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clave principal.  <br/> |


