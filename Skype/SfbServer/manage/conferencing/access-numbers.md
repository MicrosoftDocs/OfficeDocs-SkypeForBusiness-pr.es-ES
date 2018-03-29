---
title: Administrar números de conferencia de acceso telefónico local en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Resumen: Conozca cómo administrar los números de acceso de acceso telefónico de la conferencia de Skype para Business Server 2015.'
ms.openlocfilehash: ebe3388578b74041802afc12f47e0b484cb88bd7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server-2015"></a><span data-ttu-id="4f30b-103">Administrar números de conferencia de acceso telefónico local en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4f30b-103">Manage dial-in conferencing access numbers in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4f30b-104">**Resumen:** Aprenda a administrar los números de acceso de acceso telefónico de la conferencia de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4f30b-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4f30b-105">Cuando se implementa la característica de conferencia de acceso telefónico local, es necesario establecer números de teléfono que los usuarios puedan marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias.</span><span class="sxs-lookup"><span data-stu-id="4f30b-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="4f30b-106">Estos números de acceso telefónico se muestran en invitaciones a reuniones y en la página web de configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4f30b-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="4f30b-107">En este tema se describe cómo ver, modificar o eliminar números de acceso a conferencias de acceso telefónico local existentes.</span><span class="sxs-lookup"><span data-stu-id="4f30b-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="4f30b-108">Para obtener más información acerca de cómo crear números iniciales de acceso telefónico, vea [Configurar acceso telefónico conferencia en Skype para Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="4f30b-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="4f30b-109">Ver los números de acceso a conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="4f30b-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="4f30b-110">Puede ver los números de acceso a conferencias de acceso telefónico utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor de Business.</span><span class="sxs-lookup"><span data-stu-id="4f30b-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4f30b-111">Ver los números de acceso telefónico utilizando Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4f30b-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4f30b-112">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4f30b-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="4f30b-113">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="4f30b-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4f30b-114">En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="4f30b-115">En la página **Número de acceso telefónico local**, haga clic en el número de acceso que desea ver.</span><span class="sxs-lookup"><span data-stu-id="4f30b-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="4f30b-116">En **Editar**, active la casilla **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4f30b-117">Ver los números de acceso telefónico utilizando Skype para el Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4f30b-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="4f30b-118">Para ver información sobre los números de acceso telefónico local, use el cmdlet **Get-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="4f30b-119">El siguiente comando devuelve una colección de todos los números de acceso a conferencias de acceso telefónico configurado para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="4f30b-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```
Get-CsDialInConferencingAccessNumber

```

<span data-ttu-id="4f30b-120">A continuación se muestra un ejemplo del tipo de información devuelta:</span><span class="sxs-lookup"><span data-stu-id="4f30b-120">The following is an example of the type of information returned:</span></span>
  
```
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

```

<span data-ttu-id="4f30b-121">Para obtener más información, consulte [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4f30b-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="4f30b-122">Modificar los números de acceso a conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="4f30b-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="4f30b-123">Puede modificar los números de acceso telefónico utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4f30b-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4f30b-124">Modificar números de acceso telefónico mediante Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4f30b-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4f30b-125">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4f30b-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="4f30b-126">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="4f30b-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4f30b-127">En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="4f30b-128">En la página **Número de acceso telefónico local**, haga clic en uno de los números de acceso telefónico local de la lista, haga clic en **Editar** y después haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f30b-p103">Usar el campo de búsqueda para buscar el contenido de una columna de la lista de números de acceso telefónico no siempre permite obtener los resultados esperados. En lugar de eso, ordene la lista por la columna que le interese para identificar el número de acceso telefónico que desea ver o modificar.</span><span class="sxs-lookup"><span data-stu-id="4f30b-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="4f30b-131">En **Número para mostrar**, escriba el número de teléfono que los usuarios de RTC (Red telefónica conmutada) marcan para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="4f30b-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="4f30b-132">Este número se muestra en las invitaciones a reuniones y en la página web Configuración de la conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4f30b-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="4f30b-133">En **Nombre para mostrar**, escriba una descripción del número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4f30b-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="4f30b-134">Este es el nombre que está asociado con el número de acceso telefónico de Skype para los resultados de la búsqueda empresarial.</span><span class="sxs-lookup"><span data-stu-id="4f30b-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="4f30b-135">Este número se muestra en el cliente cuando un usuario llama al número de acceso.</span><span class="sxs-lookup"><span data-stu-id="4f30b-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="4f30b-p105">En **URI de línea**, escriba el número E.164 del número de acceso telefónico local en el formato de URI TEL, con el símbolo + delante del número y sin espacios. Por ejemplo, tel.: +14255550200.</span><span class="sxs-lookup"><span data-stu-id="4f30b-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f30b-138">El mismo URI de línea no puede volver a usarse por otro número de acceso telefónico a conferencias.</span><span class="sxs-lookup"><span data-stu-id="4f30b-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="4f30b-139">En **URI del SIP**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="4f30b-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="4f30b-140">En el cuadro de texto, escriba un URI del SIP único para este número de acceso a conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4f30b-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="4f30b-141">Este URI del SIP se muestra en diversas ubicaciones, incluidas, pero no limitado para llamar a los mensajes de notificación y las versiones anteriores de clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="4f30b-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f30b-p107">El mismo URI del SIP no puede volver a usarse por otro número de acceso telefónico a conferencias. El URI del SIP no puede modificarse una vez creado el número de acceso. El único modo de cambiar el URI del SIP es eliminar y volver a crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="4f30b-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="4f30b-145">En el cuadro de lista desplegable, haga clic en el dominio de la aplicación del operador de conferencia que admita este número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="4f30b-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="4f30b-146">En **Grupo de servidores**, haga clic en el grupo que ejecuta la instancia del operador de conferencia que admite el número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4f30b-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f30b-147">Si necesita cambiar el grupo después de crear el número de acceso, debe usar el cmdlet **Move-CsApplicationEndpoint** o eliminar y volver a crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="4f30b-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="4f30b-148">En **Idioma principal**, haga clic en el idioma en el que se mostrarán las indicaciones para este número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4f30b-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="4f30b-p108">El idioma principal es el idioma que usa el operador de conferencia para responder la llamada. Los idiomas admitidos se muestran junto a cada número de teléfono de acceso en la página web de configuración de conferencias de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="4f30b-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="4f30b-151">(Opcional) En **Idiomas secundarios (cuatro máximo)**, haga clic en **Agregar**, seleccione uno o más idiomas adicionales que desee poner a disposición de los que llaman a este número de acceso telefónico local y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="4f30b-p109">Puede seleccionar hasta cuatro idiomas secundarios para cada número acceso telefónico. Los usuarios pueden seleccionar un idioma secundario antes de especificar el ID de conferencia cuando marcan para acceder a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="4f30b-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="4f30b-154">Para agregar una región para el número de acceso telefónico, en **las regiones de asociados**, haga clic en ** Agregar **, haga clic en una o más áreas que están asociadas con los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-154">To add a region for the dial-in access number, under **Associated regions**, click ** Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="4f30b-155">Para eliminar una región del número de acceso telefónico local, en **Regiones asociadas**, seleccione la región que desea eliminar y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="4f30b-156">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4f30b-157">Modificar números de acceso telefónico mediante Skype de Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4f30b-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="4f30b-158">Para modificar los números de acceso telefónico local, use el cmdlet **Set-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="4f30b-159">El siguiente comando modifica la propiedad DisplayName para el número de acceso a conferencia de acceso telefónico local con el valor Identity sip:RedmondDialIn@litwareinc.com. En este ejemplo, el nombre para mostrar se establece como "Redmond Dial-In Access Number":</span><span class="sxs-lookup"><span data-stu-id="4f30b-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com. In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"

```

<span data-ttu-id="4f30b-p110">En el siguiente ejemplo, el número de acceso a conferencia de acceso telefónico local con el valor Identity sip:RedmondDialIn@litwareinc.com se modifica para incluir dos regiones: Redmond y Seattle. Para ello, se llama al parámetro Regions, seguido de las dos regiones (dos valores de cadena separados por comas). Tenga en cuenta que este comando producirá un error a menos que las regiones de Redmond y Seattle ya se hayan definido en planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="4f30b-p110">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle. To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas). Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"

```

<span data-ttu-id="4f30b-163">Para obtener más información, consulte [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4f30b-163">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="4f30b-164">Eliminar un número de acceso a conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="4f30b-164">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="4f30b-165">Puede eliminar un número de acceso a conferencias de acceso telefónico utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4f30b-165">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4f30b-166">Eliminar un número de acceso de marcado en la conferencia mediante Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4f30b-166">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4f30b-167">Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4f30b-167">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2.  <span data-ttu-id="4f30b-168">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="4f30b-168">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4f30b-169">En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-169">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="4f30b-170">En la página, haga clic en el número de acceso telefónico local que desea eliminar de la lista, haga clic en **Editar** y luego en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-170">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="4f30b-171">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-171">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4f30b-172">Eliminar un número de acceso de marcado en la conferencia mediante Skype para el Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4f30b-172">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="4f30b-173">Para eliminar un número de acceso a conferencias de acceso telefónico local, use el comando **Remove-Cs DialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="4f30b-173">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="4f30b-174">El siguiente comando elimina el número de acceso a conferencias de acceso telefónico local con el valor Identity sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="4f30b-174">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="4f30b-175">El siguiente comando elimina todos los números de acceso a conferencias de acceso telefónico local asociados a la región noroeste:</span><span class="sxs-lookup"><span data-stu-id="4f30b-175">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="4f30b-176">El siguiente comando elimina todos los números de acceso a conferencias de acceso telefónico local en los que el italiano es el idioma principal:</span><span class="sxs-lookup"><span data-stu-id="4f30b-176">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="4f30b-177">Para obtener más información, vea [Quitar CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4f30b-177">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

