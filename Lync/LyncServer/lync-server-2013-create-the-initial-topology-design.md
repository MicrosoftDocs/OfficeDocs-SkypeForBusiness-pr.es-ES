---
title: 'Lync Server 2013: crear el diseño de la topología inicial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed95696dc0acad9030615f8a031672f8abf3a136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="eb284-102">Crear el diseño de topología inicial para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb284-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb284-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="eb284-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="eb284-104">Una vez que haya finalizado la instalación de la herramienta de planeación de Lync Server 2013, estará listo para iniciar la herramienta de planeación y comenzar a diseñar la infraestructura de Lync Server 2013 propuesta.</span><span class="sxs-lookup"><span data-stu-id="eb284-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb284-105">La herramienta de planeación es una herramienta guiada por asistente con guías detalladas para informar sobre el proceso de toma de decisiones en el diseño de los sitios y la topología.</span><span class="sxs-lookup"><span data-stu-id="eb284-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="eb284-106">Este tema no está pensado como guía exhaustiva, pero simplemente para ayudarle a empezar a usar la herramienta de planeación en sus sesiones de diseño.</span><span class="sxs-lookup"><span data-stu-id="eb284-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="eb284-107">Para empezar a usar la Herramienta de planeación y crear el diseño inicial</span><span class="sxs-lookup"><span data-stu-id="eb284-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="eb284-108">Inicie la herramienta de planeación de Lync Server 2013: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **herramienta de planeación**.</span><span class="sxs-lookup"><span data-stu-id="eb284-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="eb284-109">Una vez iniciada la herramienta de planeación, aparece la página **de bienvenida de la herramienta de planeación de Microsoft Lync Server 2013** .</span><span class="sxs-lookup"><span data-stu-id="eb284-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="eb284-110">Elija una de las siguientes opciones para comenzar el diseño:</span><span class="sxs-lookup"><span data-stu-id="eb284-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="eb284-111">**Opción 1:**   Introducción **al hacer clic en Introducción proporciona** una serie específica de preguntas de la entrevista con las selecciones pertinentes para definir los criterios.</span><span class="sxs-lookup"><span data-stu-id="eb284-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="eb284-112">Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio.</span><span class="sxs-lookup"><span data-stu-id="eb284-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="eb284-113">Para completar esta opción, vaya al paso 3.</span><span class="sxs-lookup"><span data-stu-id="eb284-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="eb284-114">**Opción 2: diseñar sitios**   al hacer clic en **diseñar sitios** en la página de bienvenida se omiten las preguntas **de la entrevista** que se presentan en la sección introducción.</span><span class="sxs-lookup"><span data-stu-id="eb284-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="eb284-115">La información que se habría recopilado al responder a las preguntas de la entrevista en **la sección introducción se establece en valores** predeterminados con esta opción.</span><span class="sxs-lookup"><span data-stu-id="eb284-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="eb284-116">Al hacer clic en **diseñar sitios**, el diseñador experimentado puede omitir la entrevista inicial y cambiar los valores predeterminados, según sea necesario, en la página de inicio de los **sitios centrales** .</span><span class="sxs-lookup"><span data-stu-id="eb284-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="eb284-117">Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="eb284-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="eb284-118">**Opción 3: Mostrar la topología**   guardada si ya ha completado y guardado una topología a través del uso anterior de la herramienta de planeación, puede omitir la mayoría de estos pasos y empezar por abrir y mostrar la topología.</span><span class="sxs-lookup"><span data-stu-id="eb284-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="eb284-119">También puede realizar cambios y actualizaciones en la topología, reguardarla y, a continuación, exportarla a Microsoft Excel o Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="eb284-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="eb284-120">Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.</span><span class="sxs-lookup"><span data-stu-id="eb284-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="eb284-121">Haga **clic en introducción para** empezar a diseñar su topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb284-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="eb284-122">Responda a cada pregunta seleccionado el criterio correcto para el diseño; a continuación, haga clic en **Siguiente** para pasar a la página siguiente del Asistente.</span><span class="sxs-lookup"><span data-stu-id="eb284-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="eb284-123">Haga clic en **atrás** para realizar cambios en las páginas anteriores.</span><span class="sxs-lookup"><span data-stu-id="eb284-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="eb284-124">Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en prácticas preferidas y la planeación de la capacidad.</span><span class="sxs-lookup"><span data-stu-id="eb284-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="eb284-125">Si necesita más información, haga clic en <STRONG>más</STRONG> información para leer información detallada de la documentación de planeación de Lync Server 2013 en el sitio web de Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="eb284-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="eb284-126">Para tener acceso al sitio web de Microsoft TechNet, debe disponerse de conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="eb284-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="eb284-127">Seleccione las opciones pertinentes para el diseño.</span><span class="sxs-lookup"><span data-stu-id="eb284-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="eb284-128">Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características.</span><span class="sxs-lookup"><span data-stu-id="eb284-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="eb284-129">Haga clic en **diseñar sitios** para definir el sitio central.</span><span class="sxs-lookup"><span data-stu-id="eb284-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb284-130">Cada topología de Lync Server 2013 tendrá al menos un sitio central.</span><span class="sxs-lookup"><span data-stu-id="eb284-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="eb284-131">El diseño puede tener un único sitio central, un sitio central con varios sitios de sucursal, una serie de sitios centrales o una serie de sitios centrales con sitios de sucursal asociados con cada sitio central.</span><span class="sxs-lookup"><span data-stu-id="eb284-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="eb284-132">En **nombre del sitio**, escriba el nombre que va a identificar este sitio central.</span><span class="sxs-lookup"><span data-stu-id="eb284-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="eb284-133">En **usuarios alojados**en el sitio, escriba el número previsto de usuarios simultáneos locales que se hospedarán en este sitio central.</span><span class="sxs-lookup"><span data-stu-id="eb284-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="eb284-134">En **usuarios alojados en la nube**, escriba el número previsto de usuarios simultáneos en línea que se hospedarán en este sitio central.</span><span class="sxs-lookup"><span data-stu-id="eb284-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="eb284-135">Modifique las selecciones para colaboración en línea, usuarios, voz, opciones de implementación adicionales o aplicaciones de servidor, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="eb284-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb284-136">En este punto del diseño, solo puede activar o desactivar las opciones de la implementación.</span><span class="sxs-lookup"><span data-stu-id="eb284-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="eb284-137">Sin embargo, puede configurar más opciones en una fase posterior de la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="eb284-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="eb284-138">También hay opciones no disponibles y que no se pueden desactivar.</span><span class="sxs-lookup"><span data-stu-id="eb284-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="eb284-139">Asimismo, es posible que deba desactivar una opción para poder desactivar otra.</span><span class="sxs-lookup"><span data-stu-id="eb284-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="eb284-140">Por ejemplo, si desactiva la opción <STRONG>telefonía IP empresarial</STRONG> en voz, las opciones <STRONG>grupo de respuesta</STRONG>, <STRONG>anuncio</STRONG>y <STRONG>estacionamiento de llamadas</STRONG> en aplicaciones de servidor (todas ellas son características de Enterprise Voice) también se desactivan.</span><span class="sxs-lookup"><span data-stu-id="eb284-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="eb284-141">Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eb284-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="eb284-142">Las páginas siguientes solicitan información sobre los dominios SIP, la configuración de conferencia, la configuración de voz y la infraestructura, la mensajería unificada de Exchange, el acceso de usuarios externos, la configuración de chat persistente, la configuración de cliente, las opciones de combinación y los sitios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="eb284-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="eb284-143">Responda a estas preguntas.</span><span class="sxs-lookup"><span data-stu-id="eb284-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="eb284-144">La pregunta final pregunta si desea crear otro sitio central.</span><span class="sxs-lookup"><span data-stu-id="eb284-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="eb284-145">Si selecciona **sí**, la herramienta de planeación vuelve a la página sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="eb284-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="eb284-146">Si selecciona **no**, haga clic en **siguiente**y, a continuación, haga clic en **dibujo** para mostrar la vista de topología global de alto nivel.</span><span class="sxs-lookup"><span data-stu-id="eb284-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="eb284-147">Para ver una topología existente, haga clic en **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="eb284-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="eb284-148">Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="eb284-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="eb284-149">La herramienta de planeación muestra la página topología global.</span><span class="sxs-lookup"><span data-stu-id="eb284-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="eb284-150">Ahora puede empezar a editar, actualizar o cambiar la topología con las herramientas disponibles en la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="eb284-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb284-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb284-151">See Also</span></span>


[<span data-ttu-id="eb284-152">Edición del diseño en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb284-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

