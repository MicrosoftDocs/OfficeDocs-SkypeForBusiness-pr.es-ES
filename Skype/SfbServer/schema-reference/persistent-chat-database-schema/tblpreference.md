---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Por lo general, esto se usa en los clientes anteriores a Lync 2013.
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929924"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contiene las preferencias de cliente de los usuarios. Por lo general, esto se usa en los clientes anteriores a Lync 2013.

**Columnas**


| **Columna**            | **Tipo**                        | **Descripción**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), no es nulo  <br/> | Etiqueta con un formato como: \<uri de sip del usuario\>                   |
| prefSeqID  <br/>      | int, no es nulo  <br/>            | Número secuencial (por etiqueta) para el control de versiones.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Contenido codificado.  <br/>                                         |
| lastModifiedBy  <br/> | int, no es nulo  <br/>            | Identificador de la entidad de seguridad que se ha actualizado la preferencia.  <br/>         |

**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Clave principal.  <br/> |


