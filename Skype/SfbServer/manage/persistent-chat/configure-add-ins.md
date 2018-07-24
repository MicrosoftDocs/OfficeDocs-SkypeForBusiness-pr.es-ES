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
ms.openlocfilehash: f96f000c4ac3a78f6ca3ba4972f295e45128ce50
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967736"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="4e3fc-103">Configurar complementos para los salones de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4e3fc-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4e3fc-104">**Resumen:** Obtenga información sobre cómo configurar extensiones de servidor de Chat persistente para salones de chat de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4e3fc-105">Los complementos sirven para ampliar la experiencia en el salón al asociar las direcciones URL con los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="4e3fc-106">Dichas direcciones URL aparecen en el panel de extensibilidad de las conversaciones del cliente.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="4e3fc-107">Un complemento típico puede incluir una dirección URL que apunte a una aplicación de Silverlight que intercepta cuando un tablero de cotizaciones se registra en un salón de chat y muestra el historial de cotizaciones en el panel de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="4e3fc-108">Otros ejemplos serían incrustar una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir contexto compartido, como "Lista de prioridades" o "Tema del día".</span><span class="sxs-lookup"><span data-stu-id="4e3fc-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="4e3fc-109">Antes de que los usuarios puedan ver un complemento en el cliente, es preciso que agregue el complemento a la lista de complementos registrados; los administradores o los creadores del salón de chat necesitan asociar los salones con el complemento.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e3fc-110">Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4e3fc-111">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="4e3fc-112">Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="4e3fc-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="4e3fc-113">Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="4e3fc-114">Configurar complementos para los salones de chat con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="4e3fc-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="4e3fc-115">Para configurar complementos para los salones de chat con el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="4e3fc-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="4e3fc-116">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4e3fc-117">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4e3fc-118">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Complemento**.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="4e3fc-119">Para implementaciones de varios grupos de servidores de Chat persistente, seleccione el grupo adecuado de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="4e3fc-120">En la página **Complemento**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="4e3fc-121">En **Seleccionar un servicio**, seleccione el servicio correspondiente al grupo de servidores de Chat persistente que necesita para crear el complemento.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="4e3fc-122">Los complementos no se pueden mover de un grupo a otro ni compartir entre diferentes grupos.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="4e3fc-123">Haga lo siguiente en **Complemento nuevo**:</span><span class="sxs-lookup"><span data-stu-id="4e3fc-123">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="4e3fc-124">En **Nombre**, especifique un nombre para el nuevo complemento.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-124">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="4e3fc-p104">En **URL**, especifique la dirección URL que se asociará al complemento. Las direcciones URL se limitan a protocolos http y https.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="4e3fc-127">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="4e3fc-128">Configurar los complementos con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e3fc-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="4e3fc-129">Puede configurar complementos para los salones de chat con los siguientes cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4e3fc-130">Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de Business Server 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="4e3fc-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="4e3fc-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="4e3fc-131">**Cmdlet**</span></span>|<span data-ttu-id="4e3fc-132">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4e3fc-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4e3fc-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="4e3fc-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="4e3fc-134">Crea un complemento.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="4e3fc-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="4e3fc-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="4e3fc-136">Configura las opciones de un complemento existente.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="4e3fc-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="4e3fc-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="4e3fc-138">Recupera información sobre los complementos.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="4e3fc-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="4e3fc-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="4e3fc-140">Quita un complemento.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="4e3fc-141">Crear un complemento</span><span class="sxs-lookup"><span data-stu-id="4e3fc-141">Create a new add-in</span></span>

<span data-ttu-id="4e3fc-142">Puede crear un nuevo complemento mediante el cmdlet **New-CsPersistentChatAddin** .</span><span class="sxs-lookup"><span data-stu-id="4e3fc-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="4e3fc-143">Por ejemplo, el comando siguiente crea un nuevo complemento (con el nombre ITPersistentChatAddin) para el grupo de servidores atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="4e3fc-144">El parámetro de dirección URL y el valor del parámetro http://atl-cs-001.contoso.com/itchat especificar la ubicación de la página Web del complemento:</span><span class="sxs-lookup"><span data-stu-id="4e3fc-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="4e3fc-145">Configurar las opciones de un complemento existente</span><span class="sxs-lookup"><span data-stu-id="4e3fc-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="4e3fc-146">Puede configurar las opciones para un complemento existente al usar el cmdlet **Set-CsPersistentChatAddIn**.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="4e3fc-147">Por ejemplo, el siguiente comando modifica la dirección URL asignada al complemento del chat persistente ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="4e3fc-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="4e3fc-148">En este caso, se cambia la dirección URL ahttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="4e3fc-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="4e3fc-149">Recuperar información sobre los complementos</span><span class="sxs-lookup"><span data-stu-id="4e3fc-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="4e3fc-p108">Puede obtener información sobre los complementos al usar el cmdlet **Get-CsPersistentChatAddin**. Por ejemplo, el siguiente comando devuelve información sobre todos los complementos del chat persistente configurados para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="4e3fc-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="4e3fc-152">Quitar un complemento</span><span class="sxs-lookup"><span data-stu-id="4e3fc-152">Remove an add-in</span></span>

<span data-ttu-id="4e3fc-153">Puede quitar un complemento mediante el cmdlet **Remove-CsPersistentChatAddIn** .</span><span class="sxs-lookup"><span data-stu-id="4e3fc-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="4e3fc-154">Por ejemplo, el siguiente comando quita el complemento del chat persistente ITChatAddin que se encuentra en el grupo atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="4e3fc-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


