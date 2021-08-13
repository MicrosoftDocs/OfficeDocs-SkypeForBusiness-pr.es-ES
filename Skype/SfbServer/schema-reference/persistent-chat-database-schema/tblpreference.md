---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Esto suele ser usado por clientes anteriores a Lync 2013.
ms.openlocfilehash: 698976f3f98b939578787a0f8a2c0aeb8167888ad09ea20a09d0d7e4d83e900c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315436"
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


