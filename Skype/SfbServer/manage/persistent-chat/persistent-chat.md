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
description: 'Resumen: Obtenga información sobre cómo administrar el servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 2511de09c321c70d73d824f5fc94bf21fa674131
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967901"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar el servidor de Chat persistente en Skype para Business Server 2015.
  
Al configurar servidor de Chat persistente para su organización, especifique la configuración durante la implementación inicial. Sin embargo, puede haber ocasiones cuando desea cambiar cómo implementar compatibilidad con servidor de Chat persistente. Por ejemplo es posible que necesite configurar la compatibilidad con servidor de Chat persistente y controles de forma diferente para un equipo específico o un grupo dentro de la organización. En esta sección se proporciona información y procedimientos que le ayudarán a personalizar la implementación del servidor de Chat persistente. Para obtener información detallada sobre las características y funciones que se pueden configurar para el servidor de Chat persistente, consulte [Plan for Persistent Chat Server en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Para obtener información detallada sobre la implementación de servidor de Chat persistente, vea [Implementar servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 
  
Puede administrar servidores de Chat persistente mediante el Panel de Control o mediante el uso de cmdlets de Windows PowerShell. 
  
Para usar el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.
    
3. En la barra de navegación izquierda, haga clic en **Chat persistente**.
    
En la siguiente tabla se resume los cmdlets de Windows PowerShell disponibles que le ayudarán a administrar el servidor de Chat persistente. Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de Business Server 2015](../management-shell.md).
  

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crea una categoría  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configura las opciones de una categoría existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera información sobre las categorías  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Quita una categoría  <br/> |
|New-CsPersistentChatRoom  <br/> |Crea un salón de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura las opciones de un salón existente; asigna usuarios y grupos de usuarios al salón  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera información acerca de los salones  <br/> |
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
   

