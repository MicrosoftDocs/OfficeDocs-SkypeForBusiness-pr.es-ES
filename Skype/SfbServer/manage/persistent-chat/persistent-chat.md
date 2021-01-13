---
title: Administrar el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Resumen: obtenga información sobre cómo administrar el servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832890"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar el servidor de chat persistente en Skype Empresarial Server 2015.
  
Al configurar el servidor de chat persistente para la organización, se especifica la configuración inicial durante la implementación. Sin embargo, puede haber ocasiones en las que desee cambiar la forma en que implementa la compatibilidad con el servidor de chat persistente. Por ejemplo, puede que necesite configurar la compatibilidad y los controles del servidor de chat persistente de forma diferente para un equipo o grupo específico de la organización. En esta sección se proporciona información y procedimientos que le ayudarán a personalizar la implementación del servidor de chat persistente. Para obtener más información sobre las características y funcionalidades que puede configurar para el servidor de chat persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Para obtener más información acerca de la implementación del servidor de chat persistente, consulte Implementar el servidor de chat persistente [en Skype Empresarial Server 2015.](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md) 

> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
  
Puede administrar el servidor de chat persistente mediante el Panel de control o Windows PowerShell cmdlets. 
  
Para usar el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic **en Chat persistente.**
    
En la tabla siguiente se resumen los Windows PowerShell disponibles para ayudarle a administrar el servidor de chat persistente. Para obtener más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte Shell de administración de [Skype Empresarial Server 2015.](../management-shell.md)
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crea una categoría nueva  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configura las opciones de una categoría existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera información sobre categorías  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Quita una categoría  <br/> |
|New-CsPersistentChatRoom  <br/> |Crea un nuevo salón de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura las opciones de una sala existente; asignar usuarios y grupos de usuarios a la sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera información sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Borra una sala o mensajes de una sala  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Quita un salón  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Quita los mensajes de un salón  <br/> |
|New-CsPersistentChatAddin  <br/> |Crea un nuevo complemento  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configura las opciones de un complemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera información sobre complementos  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Quita un complemento  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifica una colección existente de opciones de configuración de cumplimiento  <br/> |
|Export-CsPersistentChatData  <br/> |Exporta datos de una base de datos de chat persistente  <br/> |
|Import-CsPersistentChatData  <br/> |Importa los datos exportados desde una versión anterior de Lync Server  <br/> |
   

