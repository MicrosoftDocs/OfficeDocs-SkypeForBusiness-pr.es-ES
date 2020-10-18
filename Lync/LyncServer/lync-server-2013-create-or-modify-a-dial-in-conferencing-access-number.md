---
title: 'Lync Server 2013: crear o modificar un número de acceso de conferencia de acceso telefónico local'
description: 'Lync Server 2013: crear o modificar un número de acceso de conferencia de acceso telefónico local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187361ab839fe2f80fda7cb68285c8f36398f5a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577966"
---
# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="a7f75-103">Crear o modificar un número de acceso de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7f75-103">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7f75-104">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a7f75-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a7f75-105">Siga estos pasos si desea crear o modificar un número de acceso de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a7f75-105">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a7f75-106">Antes de crear un nuevo número de acceso telefónico local, debe establecer una región de conferencia de acceso telefónico local en el plan de marcado asociado con el nuevo número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a7f75-106">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="a7f75-107">Varios planes de marcado pueden usar la misma región.</span><span class="sxs-lookup"><span data-stu-id="a7f75-107">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="a7f75-108">Para crear o modificar un número de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="a7f75-108">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="a7f75-109">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a7f75-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a7f75-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7f75-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a7f75-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a7f75-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a7f75-112">En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="a7f75-112">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="a7f75-113">En la página **número de acceso telefónico local** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="a7f75-113">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a7f75-114">Haga clic en **nuevo** para abrir **un nuevo número de acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="a7f75-114">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="a7f75-115">Haga clic en uno de los números de acceso telefónico local de la lista, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="a7f75-115">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a7f75-116">Si se usa el campo de búsqueda para buscar el contenido de una columna en la lista de números de acceso telefónico a redes, es posible que no ofrezca los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="a7f75-116">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="a7f75-117">En su lugar, ordene la lista por la columna de interés para identificar el número de acceso telefónico que desea ver o cambiar.</span><span class="sxs-lookup"><span data-stu-id="a7f75-117">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="a7f75-118">En **número para mostrar**, escriba el número de teléfono que los usuarios de teléfono de la red telefónica conmutada (RTC) llaman para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a7f75-118">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7f75-119">Este número se muestra en las invitaciones a la reunión y en la Página Web de configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a7f75-119">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="a7f75-120">En **nombre para mostrar**, escriba una descripción para el número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a7f75-120">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="a7f75-121">Este es el nombre que se asocia con el número de acceso telefónico local en los resultados de la búsqueda de Lync.</span><span class="sxs-lookup"><span data-stu-id="a7f75-121">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7f75-122">Este nombre se muestra en el cliente cuando un usuario llama al número de acceso.</span><span class="sxs-lookup"><span data-stu-id="a7f75-122">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="a7f75-123">En **URI de línea**, escriba el número E. 164 del número de acceso telefónico en formato URI de Tel, incluido el símbolo + delante del número y excluidos los espacios.</span><span class="sxs-lookup"><span data-stu-id="a7f75-123">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="a7f75-124">Por ejemplo, Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="a7f75-124">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7f75-125">El mismo URI de línea no puede volver a usarse por otro número de acceso de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a7f75-125">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="a7f75-126">En **URI del SIP**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7f75-126">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="a7f75-127">En el cuadro de texto, escriba un URI de SIP único para este número de acceso de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a7f75-127">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="a7f75-128">Este URI de SIP se muestra en varias ubicaciones, incluidos, entre otros, los mensajes de notificación de llamadas y las versiones anteriores de clientes de Communicator.</span><span class="sxs-lookup"><span data-stu-id="a7f75-128">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a7f75-129">El mismo URI de SIP no puede volver a usarse por otro número de acceso de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a7f75-129">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="a7f75-130">El URI del SIP no se puede modificar una vez que se ha creado el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="a7f75-130">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="a7f75-131">La única forma de cambiar el URI del SIP es eliminar y volver a crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="a7f75-131">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="a7f75-132">En el cuadro de lista desplegable, haga clic en el dominio de la aplicación operador de conferencia que admite este número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a7f75-132">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="a7f75-133">En **Grupo**, haga clic en el grupo de servidores que ejecuta la instancia del operador de conferencia que admite este número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a7f75-133">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7f75-134">Si necesita cambiar el grupo después de crear el número de acceso, debe usar el cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> o eliminar y volver a crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="a7f75-134">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="a7f75-135">En **idioma principal**, haga clic en el idioma en el que se reproducen los mensajes para este número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a7f75-135">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7f75-136">El idioma principal es el idioma que el operador de conferencia usa para responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7f75-136">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="a7f75-137">Los idiomas admitidos se muestran junto a cada número de teléfono de acceso en la Página Web de configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="a7f75-137">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="a7f75-138">Opcional En **idiomas secundarios (un máximo de cuatro)**, haga clic en **Agregar**, seleccione uno o más idiomas adicionales para los que las personas que llaman deben ser compatibles con este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7f75-138">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7f75-139">Puede elegir un máximo de cuatro idiomas secundarios para cada número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="a7f75-139">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="a7f75-140">Los usuarios pueden seleccionar un idioma secundario antes de escribir el identificador de conferencia al llamar a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a7f75-140">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="a7f75-141">Para agregar una región para el número de acceso telefónico local, en **regiones asociadas**, haga clic en **Agregar**, haga clic en una o más regiones que estén asociadas a los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7f75-141">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="a7f75-142">Para eliminar una región del número de acceso telefónico local, en **regiones asociadas**, haga clic en la región que desea eliminar y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="a7f75-142">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="a7f75-143">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a7f75-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

