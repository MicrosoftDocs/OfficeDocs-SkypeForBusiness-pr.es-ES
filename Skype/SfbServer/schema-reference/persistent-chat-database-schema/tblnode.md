---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contiene el árbol de objetos (con nodos de categoría o de salón de chat) como administrados en el panel de control y los cmdlets administrativos.
ms.openlocfilehash: 99300b6e26a0c173a13e6187680fd150ffa90e0a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814568"
---
# <a name="tblnode"></a>tblNode
 
tblNode contiene el árbol de objetos (con nodos de categoría o de salón de chat) como administrados en el panel de control y los cmdlets administrativos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |IDENTIFICADOR de nodo (número único).  <br/> |
|nodeGuid  <br/> |GUID, not null  <br/> |GUID de nodo.  <br/> |
|parentID  <br/> |int  <br/> |IDENTIFICADOR de nodo del elemento primario. El nodo raíz (con identificador 1) también se incluye como principal.  <br/> |
|Nodo  <br/> |bit, not null  <br/> |True si el nodo es una categoría.  <br/> Falso si el nodo es un salón de chat.  <br/> |
|nombreDeNodo  <br/> |nvarchar (256), not null  <br/> |Nombre del nodo.  <br/> |
|nodeDesc  <br/> |nvarchar (256), not null  <br/> |Descripción del nodo.  <br/> |
|recibir  <br/> |bit  <br/> | Para las categorías: <br/>  True si los invitados están activados. <br/>  False si los invitados están deshabilitados. <br/>  Para salas: <br/>  False si los invitados están deshabilitados (reemplaza la categoría principal). <br/>  NULL si la configuración de invitados se hereda de la categoría principal. <br/> |
|conectarse  <br/> |bit  <br/> | Para las categorías: <br/>  True si el historial de chat está activado. <br/>  Falso si el historial de conversaciones está deshabilitado. <br/>  Para salas: <br/>  Valor. <br/> |
|filePost  <br/> |bit  <br/> | Para las categorías: <br/>  True si se permiten las cargas de archivos. <br/>  False si no se permiten las cargas de archivos. <br/>  Para salas: <br/>  Valor. <br/> |
|habilitar  <br/> |bit, not null  <br/> |True si el salón de chat está deshabilitado. Solo se aplica a salones de chat. (Falso para categorías).  <br/> |
|problema  <br/> |smallint, not null  <br/> | Comportamiento (que se busca en la tabla EnumValue): <br/>  4: normal (salones de chat normales). <br/>  5: auditorio (salones de chat de Auditorio; solo los moderadores pueden contribuir). <br/>  Solo se aplica a salones de chat. <br/> |
|visión  <br/> |smallint, not null  <br/> | Visibilidad (en la tabla EnumValue): <br/>  2: privado <br/>  3: ámbito <br/>  6: abrir <br/>  Solo se aplica a salones de chat. <br/> |
|siopID  <br/> |Identificador único global  <br/> |GUID de complemento si un complemento está asociado con este salón de chat. (Las categorías no tienen complementos).  <br/> La información del complemento se busca en la tabla SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad que creó este nodo.  <br/> |
|nodeAddedOn  <br/> |BIGINT, not null  <br/> |Marca de tiempo de la creación del nodo.  <br/> |
|nodeUpdatedBy  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad que realizó la última actualización de este nodo.  <br/> |
|nodeUpdatedOn  <br/> |BIGINT, not null  <br/> |Marca de tiempo de la última actualización de este nodo.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Hora de la última operación de purga (eliminación de ámbitos de la tabla tblScopedPrincipal y roles de la tabla tblPrincipalRole) que afectó a este nodo. Lo usa el mecanismo de actualización de la caché interna del servicio de chat.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|nodeID  <br/> |Clave principal.  <br/> |
|problema  <br/> |Clave externa con la búsqueda en la tabla tblEnumValue. valueID.  <br/> |
|visión  <br/> |Clave externa con la búsqueda en la tabla tblEnumValue. valueID.  <br/> |
|parentID  <br/> |Clave externa con la búsqueda en la tabla tblNode. nodeID.  <br/> |
|siopID  <br/> |Clave externa con la búsqueda en la tabla tblSiopWhiteList. siopId.  <br/> |
   

