---
title: Configurar complementos para los salones de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Resumen: Obtenga información sobre cómo configurar extensiones de servidor de Chat persistente para salones de chat de Skype para Business Server 2015.'
ms.openlocfilehash: 64017115370c24c8c4a117f595230a6f5f741afd
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569968"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="d67da-103">Configurar complementos para los salones de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d67da-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d67da-104">**Resumen:** Obtenga información sobre cómo configurar extensiones de servidor de Chat persistente para salones de chat de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d67da-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d67da-105">Los complementos sirven para ampliar la experiencia en el salón al asociar las direcciones URL con los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="d67da-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="d67da-106">Dichas direcciones URL aparecen en el panel de extensibilidad de las conversaciones del cliente.</span><span class="sxs-lookup"><span data-stu-id="d67da-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="d67da-107">Un complemento típico puede incluir una dirección URL que apunte a una aplicación de Silverlight que intercepta cuando un tablero de cotizaciones se registra en un salón de chat y muestra el historial de cotizaciones en el panel de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="d67da-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="d67da-108">Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".</span><span class="sxs-lookup"><span data-stu-id="d67da-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="d67da-109">Antes de que los usuarios puedan ver un complemento en el cliente, es preciso que agregue el complemento a la lista de complementos registrados; los administradores o los creadores del salón de chat necesitan asociar los salones con el complemento.</span><span class="sxs-lookup"><span data-stu-id="d67da-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="d67da-110">Configurar complementos para los salones de chat con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="d67da-110">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="d67da-111">Para configurar complementos para los salones de chat con el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="d67da-111">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="d67da-112">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d67da-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d67da-113">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="d67da-113">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d67da-114">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.</span><span class="sxs-lookup"><span data-stu-id="d67da-114">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="d67da-115">Para implementaciones de varios grupos de servidores de Chat persistente, seleccione el grupo adecuado de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d67da-115">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="d67da-116">En la página **Complemento**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d67da-116">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="d67da-117">En **Seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de Chat persistente que necesita para crear el complemento.</span><span class="sxs-lookup"><span data-stu-id="d67da-117">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="d67da-118">Los complementos no se pueden mover de un grupo a otro ni compartir entre diferentes grupos.</span><span class="sxs-lookup"><span data-stu-id="d67da-118">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="d67da-119">Haga lo siguiente en **Complemento nuevo**:</span><span class="sxs-lookup"><span data-stu-id="d67da-119">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="d67da-120">En **Nombre**, especifique un nombre para el nuevo complemento.</span><span class="sxs-lookup"><span data-stu-id="d67da-120">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="d67da-p103">En **URL**, especifique la dirección URL que se asociará al complemento. Las direcciones URL se limitan a protocolos http y https.</span><span class="sxs-lookup"><span data-stu-id="d67da-p103">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="d67da-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d67da-123">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="d67da-124">Configurar los complementos con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d67da-124">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="d67da-125">Puede configurar complementos para los salones de chat con los siguientes cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d67da-125">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d67da-126">Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de Business Server 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="d67da-126">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="d67da-127">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="d67da-127">**Cmdlet**</span></span>|<span data-ttu-id="d67da-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d67da-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d67da-129">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="d67da-129">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="d67da-130">Crea un complemento.</span><span class="sxs-lookup"><span data-stu-id="d67da-130">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="d67da-131">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="d67da-131">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="d67da-132">Configura las opciones de un complemento existente.</span><span class="sxs-lookup"><span data-stu-id="d67da-132">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="d67da-133">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="d67da-133">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="d67da-134">Recupera información sobre los complementos.</span><span class="sxs-lookup"><span data-stu-id="d67da-134">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="d67da-135">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="d67da-135">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="d67da-136">Quita un complemento.</span><span class="sxs-lookup"><span data-stu-id="d67da-136">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="d67da-137">Crear un complemento</span><span class="sxs-lookup"><span data-stu-id="d67da-137">Create a new add-in</span></span>

<span data-ttu-id="d67da-138">Puede crear un nuevo complemento mediante el cmdlet **New-CsPersistentChatAddin** .</span><span class="sxs-lookup"><span data-stu-id="d67da-138">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="d67da-139">Por ejemplo, el comando siguiente crea un nuevo complemento (con el nombre ITPersistentChatAddin) para el grupo de servidores atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d67da-139">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="d67da-140">El parámetro de dirección URL y el valor del parámetro http://atl-cs-001.contoso.com/itchat especificar la ubicación de la página Web del complemento:</span><span class="sxs-lookup"><span data-stu-id="d67da-140">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="d67da-141">Configurar las opciones de un complemento existente</span><span class="sxs-lookup"><span data-stu-id="d67da-141">Configure settings for an existing add-in</span></span>

<span data-ttu-id="d67da-142">Puede configurar las opciones para un complemento existente al usar el cmdlet **Set-CsPersistentChatAddIn**.</span><span class="sxs-lookup"><span data-stu-id="d67da-142">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="d67da-143">Por ejemplo, el siguiente comando modifica la dirección URL asignada al complemento del chat persistente ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="d67da-143">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="d67da-144">En este caso, se cambia la dirección URL ahttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="d67da-144">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="d67da-145">Recuperar información sobre los complementos</span><span class="sxs-lookup"><span data-stu-id="d67da-145">Retrieve information about add-ins</span></span>

<span data-ttu-id="d67da-p107">Puede obtener información sobre los complementos al usar el cmdlet **Get-CsPersistentChatAddin**. Por ejemplo, el siguiente comando devuelve información sobre todos los complementos del chat persistente configurados para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="d67da-p107">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="d67da-148">Quitar un complemento</span><span class="sxs-lookup"><span data-stu-id="d67da-148">Remove an add-in</span></span>

<span data-ttu-id="d67da-149">Puede quitar un complemento mediante el cmdlet **Remove-CsPersistentChatAddIn** .</span><span class="sxs-lookup"><span data-stu-id="d67da-149">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="d67da-150">Por ejemplo, el siguiente comando quita el complemento del chat persistente ITChatAddin que se encuentra en el grupo atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="d67da-150">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


