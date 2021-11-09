---
title: tblPreference
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Esto suele ser usado por clientes anteriores a Lync 2013.
ms.openlocfilehash: 8c719ba33196e32d48f045c07ea89ded317ab5ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846193"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contiene las preferencias de cliente de los usuarios. Esto suele ser usado por clientes anteriores a Lync 2013.

**Columns**


| **Columna**            | **Tipo**                        | **Descripción**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), no NULL  <br/> | Etiqueta con un formato como: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, no NULL  <br/>            | Número secuencial (por etiqueta) para el control de versiones.  <br/> |
| prefContent  <br/>    | nvarchar (máx.)  <br/>           | Contenido codificado.  <br/>                                         |
| lastModifiedBy  <br/> | int, no NULL  <br/>            | Identificador de la entidad de seguridad que ha actualizado la preferencia.  <br/>         |

**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clave principal.  <br/> |


