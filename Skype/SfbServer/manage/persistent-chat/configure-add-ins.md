---
title: Configurar complementos para los salas de chat persistente en Skype Empresarial Server 2015
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
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Resumen: obtenga información sobre cómo configurar complementos para los salas de chat del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815086"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="13c90-103">Configurar complementos para los salas de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="13c90-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="13c90-104">**Resumen:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="13c90-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="13c90-105">Los complementos se usan para ampliar la experiencia en el salón mediante la asociación de direcciones URL con los salas de chat.</span><span class="sxs-lookup"><span data-stu-id="13c90-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="13c90-106">Estas direcciones URL aparecen en el panel de extensibilidad de conversación de cliente.</span><span class="sxs-lookup"><span data-stu-id="13c90-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="13c90-107">Un complemento típico puede incluir una dirección URL que apunta a una aplicación de Silverlight que intercepta cuando se publica un ticker de bolsa en un salón de chat y muestra el historial de acciones en el panel de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="13c90-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="13c90-108">Otros ejemplos incluyen la incrustación de una dirección URL de OneNote 2013 en el salón de chat como un complemento para incluir determinado contexto compartido, como "Prioridades" o "Tema del día".</span><span class="sxs-lookup"><span data-stu-id="13c90-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="13c90-109">Para que los usuarios puedan ver un complemento en el cliente, debe agregar el complemento a la lista de complementos registrados, y los administradores o creadores del salón de chat deben asociar salas con el complemento.</span><span class="sxs-lookup"><span data-stu-id="13c90-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13c90-110">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="13c90-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="13c90-111">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="13c90-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="13c90-112">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="13c90-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="13c90-113">Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="13c90-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="13c90-114">Configurar complementos para los salas de chat mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="13c90-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="13c90-115">Para configurar complementos para los salas de chat mediante el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="13c90-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="13c90-116">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator o CsAdministrator, inicie sesión en cualquier PC en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="13c90-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="13c90-117">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="13c90-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="13c90-118">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Complemento**.</span><span class="sxs-lookup"><span data-stu-id="13c90-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="13c90-119">Para varias implementaciones de grupos de servidores de chat persistente, seleccione el grupo adecuado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="13c90-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="13c90-120">En la página **Complemento**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="13c90-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="13c90-121">En **Seleccionar un servicio,** seleccione el servicio correspondiente al grupo de servidores de chat persistente donde necesita crear el complemento.</span><span class="sxs-lookup"><span data-stu-id="13c90-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="13c90-122">Los complementos no se pueden mover de un grupo a otro ni compartir entre grupos distintos.</span><span class="sxs-lookup"><span data-stu-id="13c90-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="13c90-123">En **Nuevo complemento**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="13c90-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="13c90-124">En **Nombre**, especifique un nombre para el nuevo complemento.</span><span class="sxs-lookup"><span data-stu-id="13c90-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="13c90-125">En **Dirección URL**, especifique la dirección URL que se va a asociar con el complemento.</span><span class="sxs-lookup"><span data-stu-id="13c90-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="13c90-126">Las direcciones URL están limitadas a los protocolos http y https.</span><span class="sxs-lookup"><span data-stu-id="13c90-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="13c90-127">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="13c90-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="13c90-128">Configurar complementos con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13c90-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="13c90-129">Puede configurar complementos para los salas de chat mediante los siguientes cmdlets Windows PowerShell web.</span><span class="sxs-lookup"><span data-stu-id="13c90-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="13c90-130">Para obtener más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte Shell de administración de [Skype Empresarial Server 2015.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="13c90-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="13c90-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="13c90-131">**Cmdlet**</span></span>|<span data-ttu-id="13c90-132">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="13c90-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13c90-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="13c90-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="13c90-134">Crear un nuevo complemento</span><span class="sxs-lookup"><span data-stu-id="13c90-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="13c90-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="13c90-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="13c90-136">Configurar las opciones de un complemento existente</span><span class="sxs-lookup"><span data-stu-id="13c90-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="13c90-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="13c90-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="13c90-138">Recuperar información sobre complementos</span><span class="sxs-lookup"><span data-stu-id="13c90-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="13c90-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="13c90-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="13c90-140">Quitar un complemento</span><span class="sxs-lookup"><span data-stu-id="13c90-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="13c90-141">Crear un nuevo complemento</span><span class="sxs-lookup"><span data-stu-id="13c90-141">Create a new add-in</span></span>

<span data-ttu-id="13c90-142">Puede crear un complemento con el cmdlet **New-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="13c90-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="13c90-143">Por ejemplo, el siguiente comando crea un nuevo complemento (con el nombre ITPersistentChatAddin) para el grupo de servidores atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="13c90-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="13c90-144">El parámetro URL y el valor del parámetro especifican la ubicación de la página http://atl-cs-001.contoso.com/itchat web del complemento:</span><span class="sxs-lookup"><span data-stu-id="13c90-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="13c90-145">Configurar las opciones de un complemento existente</span><span class="sxs-lookup"><span data-stu-id="13c90-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="13c90-146">Puede configurar las opciones de un complemento existente mediante el cmdlet **Set-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="13c90-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="13c90-147">Por ejemplo, el siguiente comando modifica la dirección URL asignada al complemento de chat persistente ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="13c90-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="13c90-148">En este caso, la dirección URL se cambia a http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="13c90-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="13c90-149">Recuperar información sobre complementos</span><span class="sxs-lookup"><span data-stu-id="13c90-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="13c90-150">Puede obtener información acerca de los complementos con el cmdlet **Get-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="13c90-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="13c90-151">Por ejemplo, el siguiente comando devuelve información sobre todos los complementos de chat persistente configurados para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="13c90-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="13c90-152">Quitar un complemento</span><span class="sxs-lookup"><span data-stu-id="13c90-152">Remove an add-in</span></span>

<span data-ttu-id="13c90-153">Puede quitar un complemento con el cmdlet **Remove-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="13c90-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="13c90-154">Por ejemplo, el siguiente comando quita el complemento de chat persistente ITChatAddin que se encuentra en el grupo atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="13c90-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


