---
title: Administrar el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Resumen: Conozca cómo administrar el servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 294c6bcecbbfb57bb8d2a6a785cdf20775119510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar el servidor de charla persistente en Skype para Business Server 2015.
  
Al configurar el servidor de charla persistente para su organización, especifique la configuración durante la implementación inicial. Sin embargo, puede haber ocasiones cuando desea cambiar cómo implementar la compatibilidad con el servidor de charla persistente. Por ejemplo necesitará configurar la compatibilidad con el servidor de charla persistente y controles de forma diferente para un equipo específico o un grupo dentro de la organización. En esta sección se proporciona información y procedimientos para ayudarle a personalizar su implementación de servidor de charla persistente. Para obtener más información acerca de las características y funciones que se pueden configurar para el servidor de charla persistente, vea [Planear persistente Server Chat de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Para obtener más información acerca de cómo implementar el servidor de charla persistente, vea [Implementar servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
  
Puede administrar el servidor de charla persistente mediante el Panel de Control o mediante cmdlets de Windows PowerShell. 
  
Para usar el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.
    
3. En la barra de navegación de la izquierda, haga clic en **Charla persistente**.
    
La siguiente tabla resume los cmdlets de Windows PowerShell disponibles para ayudarle a administrar el servidor de charla persistente. Para obtener más información acerca de la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|Nueva CsPersistentChatCategory  <br/> |Crea una categoría  <br/> |
|Conjunto de CsPersistentChatCategory  <br/> |Configura las opciones de una categoría existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera información sobre las categorías  <br/> |
|Quitar CsPersistentChatCategory  <br/> |Quita una categoría  <br/> |
|Nueva CsPersistentChatRoom  <br/> |Crea un salón de chat  <br/> |
|Conjunto de CsPersistentChatRoom  <br/> |Configura las opciones de un salón existente; asigna usuarios y grupos de usuarios al salón  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera información sobre las salas  <br/> |
|Borrar CsPersistentChatRoom  <br/> |Borra un salón o los mensajes de un salón  <br/> |
|Quitar CsPersistentChatRoom  <br/> |Quita un salón  <br/> |
|Quitar CsPersistentChatMessage  <br/> |Quita mensajes de un salón  <br/> |
|Nueva CsPersistentChatAddin  <br/> |Crea un complemento  <br/> |
|Conjunto de CsPersistentChatAddin  <br/> |Configura las opciones de un complemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera información sobre los complementos  <br/> |
|Quitar CsPersistentChatAddin  <br/> |Quita un complemento  <br/> |
|Conjunto de CsPersistentChatComplianceConfiguration  <br/> |Modifica una colección existente de opciones de configuración del cumplimiento  <br/> |
|CsPersistentChatData de exportación  <br/> |Exporta los datos de una base de datos de chat persistente  <br/> |
|CsPersistentChatData de importación  <br/> |Importa los datos exportados de una versión anterior de Skype Empresarial  <br/> |
   

