---
title: 'Lync Server 2013: Crear o modificar un número de acceso para conferencias de acceso telefónico local'
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
ms.openlocfilehash: 7ecfebba25d45f53633fdd425e5901929fc32d0c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="fe41a-102">Crear o modificar un número de acceso para conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe41a-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe41a-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="fe41a-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="fe41a-104">Siga estos pasos si desea crear o modificar un número de acceso de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe41a-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe41a-105">Antes de crear un nuevo número de acceso telefónico local, debe establecer una región de conferencia de acceso telefónico local en el plan de marcado asociado al nuevo número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe41a-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="fe41a-106">Varios planes de marcado pueden usar la misma región.</span><span class="sxs-lookup"><span data-stu-id="fe41a-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="fe41a-107">Para crear o modificar un número de acceso de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="fe41a-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="fe41a-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="fe41a-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fe41a-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe41a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe41a-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fe41a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe41a-111">En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="fe41a-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="fe41a-112">En la página **Número de acceso telefónico local**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="fe41a-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="fe41a-113">Haga clic en **Nuevo** para abrir **Nuevo número de acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="fe41a-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="fe41a-114">Haga clic en uno de los números de acceso telefónico local de la lista, haga clic en **Editar** y después haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="fe41a-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fe41a-p103">Usar el campo de búsqueda para buscar el contenido de una columna de la lista de números de acceso telefónico no siempre permite obtener los resultados esperados. En lugar de eso, ordene la lista por la columna que le interese para identificar el número de acceso telefónico que desea ver o modificar.</span><span class="sxs-lookup"><span data-stu-id="fe41a-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="fe41a-117">En **Número para mostrar**, escriba el número de teléfono que los usuarios de RTC (Red telefónica conmutada) marcan para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="fe41a-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe41a-118">Este número se muestra en las invitaciones a reuniones y en la página web Configuración de la conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe41a-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="fe41a-119">En **Nombre para mostrar**, escriba una descripción del número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe41a-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="fe41a-120">Este es el nombre que está asociado al número de acceso telefónico local en los resultados de la búsqueda de Lync.</span><span class="sxs-lookup"><span data-stu-id="fe41a-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe41a-121">Este número se muestra en el cliente cuando un usuario llama al número de acceso.</span><span class="sxs-lookup"><span data-stu-id="fe41a-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="fe41a-p105">En **URI de línea**, escriba el número E.164 del número de acceso telefónico local en el formato de URI TEL, con el símbolo + delante del número y sin espacios. Por ejemplo, tel.: +14255550200.</span><span class="sxs-lookup"><span data-stu-id="fe41a-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe41a-124">El mismo URI de línea no puede volver a usarse por otro número de acceso telefónico a conferencias.</span><span class="sxs-lookup"><span data-stu-id="fe41a-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="fe41a-125">En **URI del SIP**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="fe41a-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="fe41a-126">En el cuadro de texto, escriba un URI del SIP único para este número de acceso a conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe41a-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="fe41a-127">Este URI del SIP se muestra en varias ubicaciones, entre las que se incluyen los mensajes de notificación de llamada y las versiones anteriores de clientes de Communicator.</span><span class="sxs-lookup"><span data-stu-id="fe41a-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fe41a-p107">El mismo URI del SIP no puede volver a usarse por otro número de acceso telefónico a conferencias. El URI del SIP no puede modificarse una vez creado el número de acceso. El único modo de cambiar el URI del SIP es eliminar y volver a crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="fe41a-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="fe41a-131">En el cuadro de lista desplegable, haga clic en el dominio de la aplicación de operador de conferencia que admite este número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe41a-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="fe41a-132">En **Grupo de servidores**, haga clic en el grupo que ejecuta la instancia del operador de conferencia que admite el número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe41a-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe41a-133">Si necesita cambiar el grupo de servidores tras crear el número de acceso, necesitará usar el cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> o eliminar y volver a crear el número de acceso.</span><span class="sxs-lookup"><span data-stu-id="fe41a-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="fe41a-134">En **Idioma principal**, haga clic en el idioma en el que se mostrarán las indicaciones para este número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fe41a-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe41a-p108">El idioma principal es el idioma que usa el operador de conferencia para responder la llamada. Los idiomas admitidos se muestran junto a cada número de teléfono de acceso en la página web de configuración de conferencias de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="fe41a-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="fe41a-137">(Opcional) En **Idiomas secundarios (cuatro máximo)**, haga clic en **Agregar**, seleccione uno o más idiomas adicionales que desee poner a disposición de los que llaman a este número de acceso telefónico local y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fe41a-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe41a-p109">Puede seleccionar hasta cuatro idiomas secundarios para cada número acceso telefónico. Los usuarios pueden seleccionar un idioma secundario antes de especificar el ID de conferencia cuando marcan para acceder a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="fe41a-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="fe41a-140">Para agregar una región para el número de acceso telefónico local, en **regiones asociadas**, haga clic en **Agregar**, haga clic en una o más regiones asociadas con los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fe41a-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="fe41a-141">Para eliminar una región del número de acceso telefónico local, en **Regiones asociadas**, seleccione la región que desea eliminar y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="fe41a-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="fe41a-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fe41a-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

