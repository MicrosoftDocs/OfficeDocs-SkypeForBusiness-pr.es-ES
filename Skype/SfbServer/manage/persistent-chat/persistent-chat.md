---
title: Administrar el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Resumen: obtenga información sobre cómo administrar el servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 3fc0027d8984a3c4ea4249f0d44a2d21a4913a3a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860007"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar el servidor de chat persistente en Skype Empresarial Server 2015.
  
Al configurar el servidor de chat persistente para la organización, se especifica la configuración inicial durante la implementación. Sin embargo, puede haber ocasiones en las que desee cambiar la forma en que implementa la compatibilidad con el servidor de chat persistente. Por ejemplo, es posible que deba configurar la compatibilidad y los controles del servidor de chat persistente de forma diferente para un grupo o grupo específico de la organización. En esta sección se proporciona información y procedimientos que le ayudarán a personalizar la implementación del servidor de chat persistente. Para obtener más información sobre las características y funcionalidades que puede configurar para el servidor de chat persistente, vea [Plan for Persistent Chat Server in Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Para obtener más información acerca de la implementación del servidor de chat persistente, [vea Deploy Persistent Chat Server in Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015. 
  
Puede administrar el servidor de chat persistente mediante el Panel de control o mediante Windows PowerShell cmdlets. 
  
Para usar el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.
    
2. En el **menú** Inicio, seleccione Skype Empresarial Server Panel de control o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic **en Chat persistente.**
    
En la tabla siguiente se resumen los cmdlets Windows PowerShell disponibles para ayudarle a administrar el servidor de chat persistente. Para obtener más información sobre la sintaxis, incluidos todos los parámetros disponibles, vea Skype Empresarial Server Shell de administración [de 2015](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crea una nueva categoría  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configura la configuración de una categoría existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera información sobre categorías  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Quita una categoría  <br/> |
|New-CsPersistentChatRoom  <br/> |Crea un nuevo salón de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura la configuración de una sala existente; asignar usuarios y grupos de usuarios a la sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera información sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Borra una sala o mensajes de una sala  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Quita una sala  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Quita mensajes de una sala  <br/> |
|New-CsPersistentChatAddin  <br/> |Crea un nuevo complemento  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configura la configuración de un complemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera información sobre complementos  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Quita un complemento  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifica una colección existente de opciones de configuración de cumplimiento  <br/> |
|Export-CsPersistentChatData  <br/> |Exporta datos de una base de datos de chat persistente  <br/> |
|Import-CsPersistentChatData  <br/> |Importa datos exportados desde una versión anterior de Lync Server  <br/> |
   

