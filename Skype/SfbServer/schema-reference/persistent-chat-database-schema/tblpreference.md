---
title: tblPreference
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 24de89ff74da66023aeac696c7f3ae91fb9b98b1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768458"
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


