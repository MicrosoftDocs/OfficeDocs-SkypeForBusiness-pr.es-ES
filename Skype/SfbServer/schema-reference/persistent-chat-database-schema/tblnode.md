---
title: tblNode
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contiene el árbol de objetos (con nodos de categoría o salón de chat) administrado en el panel de control y cmdlets administrativos.
ms.openlocfilehash: 2d26e61fc9404e2649ca71d4e48d4bb3f147c88ec787dfd798753eaa5f83a5b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306721"
---
# <a name="tblnode"></a>tblNode
 
tblNode contiene el árbol de objetos (con nodos de categoría o salón de chat) administrado en el panel de control y cmdlets administrativos.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, no NULL  <br/> |Id. de nodo (número único).  <br/> |
|nodeGuid  <br/> |GUID, not null  <br/> |GUID de nodo.  <br/> |
|parentID  <br/> |Entero  <br/> |Id. de nodo del elemento primario. El nodo raíz (con id. 1) también se incluye como primario.  <br/> |
|nodeType  <br/> |bit, not null  <br/> |True si el nodo es una categoría.  <br/> False si el nodo es un salón de chat.  <br/> |
|nodeName  <br/> |nvarchar (256), no NULL  <br/> |Nombre del nodo.  <br/> |
|nodeDesc  <br/> |nvarchar (256), no NULL  <br/> |Descripción del nodo.  <br/> |
|invitar  <br/> |bit  <br/> | Para categorías: <br/>  True si las invitaciones están en. <br/>  False si las invitaciones están desactivadas. <br/>  Para salas: <br/>  False si las invitaciones están desactivadas (invalida la categoría principal). <br/>  Null si la configuración de invitaciones se hereda de la categoría primaria. <br/> |
|registrado  <br/> |bit  <br/> | Para categorías: <br/>  True si el historial de chat está en. <br/>  False si el historial de chat está desactivado. <br/>  Para salas: <br/>  Null. <br/> |
|filePost  <br/> |bit  <br/> | Para categorías: <br/>  True si se permiten las cargas de archivos. <br/>  False si no se pueden cargar archivos. <br/>  Para salas: <br/>  Null. <br/> |
|deshabilitado  <br/> |bit, not null  <br/> |True si el salón de chat está deshabilitado. Solo se aplica a los salas de chat. (False para categorías).  <br/> |
|comportamiento  <br/> |smallint, no NULL  <br/> | Comportamiento (buscado en la tabla EnumValue): <br/>  4: Normal (salas de chat normales). <br/>  5: Auditorium (salas de chat de auditorio, solo los presentadores pueden contribuir). <br/>  Solo se aplica a los salas de chat. <br/> |
|visibility  <br/> |smallint, no NULL  <br/> | Visibilidad (buscada en la tabla EnumValue): <br/>  2: Privado <br/>  3: Ámbito <br/>  6: Abrir <br/>  Solo se aplica a los salas de chat. <br/> |
|siopID  <br/> |GUID  <br/> |Add-In GUID si un complemento está asociado a este salón de chat. (Las categorías no tienen complementos).  <br/> La información del complemento se busca en la tabla SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad que creó este nodo.  <br/> |
|nodeAddedOn  <br/> |bigint, no NULL  <br/> |Marca de tiempo de la creación del nodo.  <br/> |
|nodeUpdatedBy  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad que hizo la actualización más reciente de este nodo.  <br/> |
|nodeUpdatedOn  <br/> |bigint, no NULL  <br/> |Marca de tiempo de la última actualización de este nodo.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Hora de la última operación de purga (eliminación de ámbitos de la tabla tblScopedPrincipal y roles de la tabla tblPrincipalRole) que afectó a este nodo. Esto lo usa el mecanismo de actualización de caché interna del servicio de chat.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|nodeID  <br/> |Clave principal.  <br/> |
|comportamiento  <br/> |Clave externa con búsqueda en la tabla tblEnumValue.valueID.  <br/> |
|visibility  <br/> |Clave externa con búsqueda en la tabla tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
|siopID  <br/> |Clave externa con búsqueda en la tabla tblSiopWhiteList.siopId.  <br/> |
   

