---
title: 'Administrar números de acceso a conferencias de acceso telefónico local en Skype Empresarial Server '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Resumen: obtenga información sobre cómo administrar los números de acceso a conferencias de acceso telefónico local en Skype Empresarial Server.'
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806490"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="b358f-103">Administrar números de acceso a conferencias de acceso telefónico local en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b358f-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="b358f-104">**Resumen:** Obtenga información sobre cómo administrar los números de acceso a conferencias de acceso telefónico local en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b358f-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="b358f-105">Al implementar las conferencias de acceso telefónico local, debe configurar números de teléfono que los usuarios pueden marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias.</span><span class="sxs-lookup"><span data-stu-id="b358f-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="b358f-106">Estos números de acceso telefónico local aparecen en las invitaciones a reuniones y en la página web configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b358f-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="b358f-107">En este tema se describe cómo ver, modificar o eliminar números de acceso a conferencias de acceso telefónico local existentes.</span><span class="sxs-lookup"><span data-stu-id="b358f-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="b358f-108">Para obtener más información acerca de cómo crear números de acceso telefónico local iniciales, consulte Configurar las conferencias de acceso telefónico [local en Skype Empresarial Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="b358f-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="b358f-109">Ver números de acceso a conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="b358f-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="b358f-110">Puede ver los números de acceso a conferencias de acceso telefónico local con el Panel de control de Skype Empresarial Server o con el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b358f-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b358f-111">Ver números de acceso telefónico local mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b358f-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b358f-112">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b358f-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b358f-113">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b358f-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b358f-114">En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="b358f-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b358f-115">En la página **Número de acceso telefónico**, haga clic en el número de acceso que desea ver.</span><span class="sxs-lookup"><span data-stu-id="b358f-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="b358f-116">En **Editar,** active la casilla **Mostrar** detalles.</span><span class="sxs-lookup"><span data-stu-id="b358f-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b358f-117">Ver números de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b358f-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b358f-118">Para ver información sobre los números de acceso telefónico local, use el cmdlet **Get-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="b358f-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="b358f-119">El siguiente comando devuelve una colección de todos los números de acceso a conferencias de acceso telefónico local configurados para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="b358f-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b358f-120">A continuación se muestra un ejemplo del tipo de información devuelta:</span><span class="sxs-lookup"><span data-stu-id="b358f-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="b358f-121">Para obtener más información, [vea Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b358f-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="b358f-122">Modificar números de acceso a conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="b358f-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="b358f-123">Puede modificar los números de acceso telefónico local con el Panel de control de Skype Empresarial Server o con el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b358f-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b358f-124">Modificar números de acceso telefónico local mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b358f-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b358f-125">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b358f-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b358f-126">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b358f-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b358f-127">En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="b358f-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b358f-128">En la **página Número** de acceso telefónico, haga clic en uno de los números de acceso telefónico de la lista, haga clic en Editar y, a continuación, haga clic **en Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="b358f-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b358f-129">El uso del campo de búsqueda para buscar el contenido de una columna en la lista de números de acceso telefónico no puede producir los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="b358f-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="b358f-130">En su lugar, ordene la lista por la columna de interés para identificar el número de acceso telefónico que desea ver o cambiar.</span><span class="sxs-lookup"><span data-stu-id="b358f-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="b358f-131">En **Número de pantalla,** escriba el número de teléfono que marcan los usuarios de la red telefónica conmutada (RTC) para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="b358f-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="b358f-132">Este número se muestra en las invitaciones a reuniones y en la página web configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b358f-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="b358f-133">En **Nombre para mostrar,** escriba una descripción para el número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="b358f-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="b358f-134">Este es el nombre asociado al número de acceso telefónico en los resultados de búsqueda de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b358f-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="b358f-135">Este nombre se muestra en el cliente cuando un usuario llama al número de acceso.</span><span class="sxs-lookup"><span data-stu-id="b358f-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="b358f-136">En **uri** de línea, escriba el número E.164 del número de acceso telefónico en formato URI tel., incluido el símbolo + delante del número y excluyendo espacios.</span><span class="sxs-lookup"><span data-stu-id="b358f-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="b358f-137">Por ejemplo, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="b358f-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b358f-138">Otro número de acceso a conferencias de acceso telefónico local no puede volver a usar el mismo URI de línea.</span><span class="sxs-lookup"><span data-stu-id="b358f-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="b358f-139">En **el URI de SIP,** haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b358f-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="b358f-140">En el cuadro de texto, escriba un URI de SIP único para este número de acceso a conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b358f-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="b358f-141">Este URI de SIP se muestra en varias ubicaciones, incluidos, entre otros, los mensajes de notificación de llamadas y las versiones anteriores de los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="b358f-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b358f-142">Otro número de acceso a conferencias de acceso telefónico local no puede volver a usar el mismo URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="b358f-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="b358f-143">El URI de SIP no se puede modificar después de crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="b358f-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="b358f-144">La única forma de cambiar el URI de SIP es eliminar y volver a crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="b358f-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="b358f-145">En el cuadro de lista desplegable, haga clic en el dominio de la aplicación Operador de conferencia que admite este número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b358f-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="b358f-146">En **Grupo** de servidores, haga clic en el grupo que ejecuta la instancia de Operador de conferencia que admite este número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b358f-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b358f-147">Si necesita cambiar el grupo después de crear el número de acceso, debe usar el cmdlet **Move-CsApplicationEndpoint** o eliminar y volver a crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="b358f-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="b358f-148">En **el idioma principal,** haga clic en el idioma en el que se reproducen los mensajes para este número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="b358f-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="b358f-149">El idioma principal es el idioma que el operador de conferencia usa para responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="b358f-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="b358f-150">Los idiomas admitidos se muestran junto con cada número de teléfono de acceso en la página web configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b358f-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="b358f-151">(Opcional) En **idiomas** secundarios (máximo de cuatro), haga clic en Agregar **,** seleccione uno o más idiomas adicionales que desee admitir para los autores de llamadas a este número de acceso telefónico local y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="b358f-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="b358f-152">Puede elegir hasta cuatro idiomas secundarios para cada número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b358f-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="b358f-153">Los usuarios pueden seleccionar un idioma secundario antes de escribir el identificador de conferencia cuando llamen a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="b358f-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="b358f-154">Para agregar una región para el número de acceso telefónico, en Regiones **asociadas,** haga clic en Agregar **,** haga clic en una o más regiones asociadas a los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="b358f-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="b358f-155">Para eliminar una región del número de acceso telefónico, en Regiones **asociadas,** haga clic en la región que desea eliminar y, a continuación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="b358f-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="b358f-156">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b358f-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b358f-157">Modificar números de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b358f-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b358f-158">Para modificar los números de acceso telefónico local, use el cmdlet **Set-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="b358f-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="b358f-159">El siguiente comando modifica la propiedad DisplayName para el número de acceso a conferencias de acceso telefónico local con el parámetro Identity sip:RedmondDialIn@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b358f-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="b358f-160">En este ejemplo, el nombre para mostrar se establece en "Redmond Dial-In Access Number":</span><span class="sxs-lookup"><span data-stu-id="b358f-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="b358f-161">En el siguiente ejemplo, se modifica el número de acceso para conferencias de acceso telefónico local con el parámetro Identity sip:RedmondDialIn@litwareinc.com para incluir dos regiones: Redmond y Seattle.</span><span class="sxs-lookup"><span data-stu-id="b358f-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="b358f-162">Para ello, se llama al parámetro Regions, seguido de las dos regiones (dos valores de cadena separados por comas).</span><span class="sxs-lookup"><span data-stu-id="b358f-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="b358f-163">Tenga en cuenta que este comando producirá un error a menos que las regiones de Redmond y Seattle ya se hayan definido en planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="b358f-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="b358f-164">Para obtener más información, [vea Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b358f-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="b358f-165">Eliminar un número de acceso a conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="b358f-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="b358f-166">Puede eliminar un número de acceso para conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b358f-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b358f-167">Eliminar un número de acceso a conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b358f-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b358f-168">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b358f-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="b358f-169">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b358f-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b358f-170">En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="b358f-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="b358f-171">En la página, haga clic en el número de acceso telefónico local que desea eliminar de la lista, haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b358f-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="b358f-172">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b358f-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b358f-173">Eliminar un número de acceso a conferencias de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b358f-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b358f-174">Para eliminar un número de acceso a conferencias de acceso telefónico local, use **remove-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="b358f-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="b358f-175">El siguiente comando elimina el número de acceso a conferencias de acceso telefónico local con el parámetro Identity sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b358f-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="b358f-176">El siguiente comando elimina todos los números de acceso a conferencias de acceso telefónico local asociados con la región Northwest:</span><span class="sxs-lookup"><span data-stu-id="b358f-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b358f-177">El siguiente comando elimina todos los números de acceso a conferencias de acceso telefónico local en los que el italiano es el idioma principal:</span><span class="sxs-lookup"><span data-stu-id="b358f-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="b358f-178">Para obtener más información, [vea Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b358f-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

