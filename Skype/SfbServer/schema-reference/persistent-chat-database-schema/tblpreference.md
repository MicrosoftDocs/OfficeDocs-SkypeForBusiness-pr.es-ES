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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Lo usan generalmente los clientes anteriores a Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295345"
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


