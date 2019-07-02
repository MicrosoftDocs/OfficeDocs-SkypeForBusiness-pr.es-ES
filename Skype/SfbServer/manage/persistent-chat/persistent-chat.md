---
title: Administrar el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Resumen: Aprenda a administrar el servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: 1702cc9891c34085f8de269d5e91723378c54ada
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418672"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar el servidor de chat persistente en Skype empresarial Server 2015.
  
Al configurar un servidor de chat persistente para su organización, debe especificar la configuración inicial durante la implementación. Sin embargo, puede haber ocasiones en las que desee cambiar el modo en que se implementa la compatibilidad con el servidor de chat. Por ejemplo, es posible que tenga que configurar la compatibilidad del servidor de chat persistente y los controles de forma diferente para un equipo o grupo específico de su organización. Esta sección proporciona información y procedimientos para ayudarle a personalizar la implementación del servidor de chat persistente. Para obtener más información sobre las características y funcionalidades que puede configurar para el servidor de chat persistente, consulte [planear el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Para obtener más información sobre cómo implementar el servidor de chat persistente, consulte [implementar un servidor de chat persistente en Skype empresarial server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 
  
Puede administrar el servidor de chat persistente mediante el panel de control o mediante cmdlets de Windows PowerShell. 
  
Para usar el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.
    
3. En la barra de navegación izquierda, haga clic en **chat persistente**.
    
En la siguiente tabla se resumen los cmdlets de Windows PowerShell disponibles para ayudarle a administrar el servidor de chat persistente. Para detalles sobre la sintaxis, incluso todos los parámetros disponibles, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crea una categoría  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configura las opciones de una categoría existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera información sobre las categorías  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Quita una categoría  <br/> |
|New-CsPersistentChatRoom  <br/> |Crea un salón de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura las opciones de un salón existente; asigna usuarios y grupos de usuarios al salón  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera información sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Borra un salón o los mensajes de un salón  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Quita un salón  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Quita mensajes de un salón  <br/> |
|New-CsPersistentChatAddin  <br/> |Crea un complemento  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configura las opciones de un complemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera información sobre los complementos  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Quita un complemento  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifica una colección existente de opciones de configuración del cumplimiento  <br/> |
|Export-CsPersistentChatData  <br/> |Exporta los datos de una base de datos de chat persistente  <br/> |
|Import-CsPersistentChatData  <br/> |Importa los datos exportados de una versión anterior de Skype Empresarial  <br/> |
   

