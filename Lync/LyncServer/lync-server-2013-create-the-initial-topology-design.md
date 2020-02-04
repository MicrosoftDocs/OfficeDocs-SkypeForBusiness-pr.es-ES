---
title: 'Lync Server 2013: crear el diseño de topología inicial'
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
ms.openlocfilehash: 7fc8d3e731c2772b275dd861c41b8c10f2127a2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="93de6-102">Crear el diseño de topología inicial para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93de6-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93de6-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="93de6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="93de6-104">Una vez que haya terminado de instalar Lync Server 2013, la herramienta de planeación, estará listo para iniciar la herramienta de planeación y empezar a diseñar la infraestructura de Lync Server 2013 propuesta.</span><span class="sxs-lookup"><span data-stu-id="93de6-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93de6-105">La herramienta de planeación es una herramienta guiada por un asistente con guías detalladas para informar sobre el proceso de toma de decisiones en el diseño de sitios y topología.</span><span class="sxs-lookup"><span data-stu-id="93de6-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="93de6-106">Este tema está pensado no es una guía exhaustiva, pero simplemente para ayudarle a empezar a usar la herramienta de planificación en sus sesiones de diseño.</span><span class="sxs-lookup"><span data-stu-id="93de6-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="93de6-107">Para empezar a usar la herramienta de planificación y crear el diseño inicial</span><span class="sxs-lookup"><span data-stu-id="93de6-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="93de6-108">Inicie Lync Server 2013, herramienta de planeación: haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **herramienta de planeación**.</span><span class="sxs-lookup"><span data-stu-id="93de6-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="93de6-109">Después de iniciar la herramienta de planeación, aparece la página **de bienvenida a la herramienta de planeación de Microsoft Lync Server 2013** .</span><span class="sxs-lookup"><span data-stu-id="93de6-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="93de6-110">Para empezar el diseño, elija una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="93de6-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="93de6-111">**Opción 1:**   Introducción al hacer clic en **comenzar** proporciona una serie de preguntas de entrevista con las selecciones pertinentes para definir los criterios.</span><span class="sxs-lookup"><span data-stu-id="93de6-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="93de6-112">Una vez completada la sección de entrevistas de **Introducción**, se pasa a la fase **Diseñar sitios** para definir la arquitectura del sitio.</span><span class="sxs-lookup"><span data-stu-id="93de6-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="93de6-113">Para completar esta opción, vaya al paso 3.</span><span class="sxs-lookup"><span data-stu-id="93de6-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="93de6-114">**Opción 2: diseñar sitios**   al hacer clic en **sitios de diseño** , en la página de bienvenida se omiten las preguntas de entrevista que se presentan en **la sección introducción** .</span><span class="sxs-lookup"><span data-stu-id="93de6-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="93de6-115">Los datos que el usuario facilita al responder a las preguntas de la entrevista de **Introducción** se definen como sus valores predeterminados con esta opción.</span><span class="sxs-lookup"><span data-stu-id="93de6-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="93de6-116">Al hacer clic en **Diseñar sitios**, los diseñadores avanzados pueden prescindir de la entrevista inicial y modificar los valores predeterminados a su conveniencia en la página de inicio de **Sitios centrales**.</span><span class="sxs-lookup"><span data-stu-id="93de6-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="93de6-117">Para completar esta opción, omita los pasos del 3 al 5 y comience en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="93de6-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="93de6-118">**Opción 3: Mostrar la topología**   guardada si ya ha completado y guardado una topología a través del uso anterior de la herramienta de planeación, puede omitir la mayoría de estos pasos y empezar abriendo y mostrando la topología.</span><span class="sxs-lookup"><span data-stu-id="93de6-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="93de6-119">Además, puede cambiar y actualizar la topología, volverla a guardar y exportarla a Microsoft Excel o Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="93de6-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="93de6-120">Para completar esta opción, omita los pasos del 3 al 12 y comience en el paso 13.</span><span class="sxs-lookup"><span data-stu-id="93de6-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="93de6-121">Haga **clic en introducción para** empezar a diseñar su topología de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93de6-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="93de6-p106">Responda a cada pregunta seleccionando el criterio correcto para el diseño; después, haga clic en **Siguiente** para pasar a la página siguiente del Asistente. Haga clic en **Atrás** para hacer cambios en páginas anteriores.</span><span class="sxs-lookup"><span data-stu-id="93de6-p106">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page. Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="93de6-124">Cada página presenta una descripción de los criterios de selección, así como recomendaciones basadas en los procedimientos preferidos y el planeamiento de capacidad.</span><span class="sxs-lookup"><span data-stu-id="93de6-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="93de6-125">Si necesita más información, haga clic en <STRONG>más</STRONG> información para obtener información detallada de la documentación de planeación de Lync Server 2013 en el sitio web de Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="93de6-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="93de6-126">Para tener acceso al sitio web de Microsoft TechNet, debe disponerse de conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="93de6-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="93de6-127">Seleccione las opciones pertinentes para el diseño.</span><span class="sxs-lookup"><span data-stu-id="93de6-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="93de6-128">Tras haber definido los criterios iniciales, se mostrará una página para confirmar que se ha completado la información general sobre las características.</span><span class="sxs-lookup"><span data-stu-id="93de6-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="93de6-129">Haga clic en **diseñar sitios** para definir el sitio central.</span><span class="sxs-lookup"><span data-stu-id="93de6-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93de6-130">Cada topología de Lync Server 2013 tendrá al menos un sitio central.</span><span class="sxs-lookup"><span data-stu-id="93de6-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="93de6-131">Su diseño puede tener un único sitio central, un sitio central con un número de sitios de sucursales, una serie de sitios centrales o varios sitios centrales con sitios de sucursales asociados con cada sitio central.</span><span class="sxs-lookup"><span data-stu-id="93de6-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="93de6-132">En **nombre del sitio**, escriba el nombre que identificará a este sitio central.</span><span class="sxs-lookup"><span data-stu-id="93de6-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="93de6-133">En **usuarios alojados del sitio**, escriba el número esperado de usuarios simultáneos locales que estarán alojados en este sitio central.</span><span class="sxs-lookup"><span data-stu-id="93de6-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="93de6-134">En **usuarios domésticos en la nube**, escriba el número esperado de usuarios simultáneos en línea que estarán alojados en este sitio central.</span><span class="sxs-lookup"><span data-stu-id="93de6-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="93de6-135">Modifique las opciones de Colaboración en línea, Usuarios, Voz, Opciones de implementación adicionales o Aplicaciones de servidor según se necesite.</span><span class="sxs-lookup"><span data-stu-id="93de6-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="93de6-136">En esta fase del diseño, solamente puede activar o desactivar opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="93de6-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="93de6-137">Sin embargo, puede configurar más opciones en una fase posterior de la herramienta de planificación.</span><span class="sxs-lookup"><span data-stu-id="93de6-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="93de6-138">También hay opciones no disponibles y que no se pueden desactivar.</span><span class="sxs-lookup"><span data-stu-id="93de6-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="93de6-139">Además, es posible que deba desactivar una opción para poder desactivar otra.</span><span class="sxs-lookup"><span data-stu-id="93de6-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="93de6-140">Por ejemplo, si desactiva la opción <STRONG>Telefonía IP empresarial</STRONG> debajo de Voz, las opciones <STRONG>Grupo de respuesta</STRONG>, <STRONG>Anuncio</STRONG> y <STRONG>Estacionamiento de llamadas</STRONG> debajo de Aplicaciones de servidor (todas ellas características de Telefonía IP empresarial) también se desactivan.</span><span class="sxs-lookup"><span data-stu-id="93de6-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="93de6-141">Después de haber definido un nombre de sitio y la cantidad de usuarios, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93de6-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="93de6-142">Las siguientes páginas solicitan información sobre los dominios SIP, la configuración de la Conferencia, la configuración de voz y la infraestructura, la mensajería unificada de Exchange, el acceso de usuarios externos, la configuración de chat persistente, la configuración de cliente, las opciones de collocation y los sitios de sucursales</span><span class="sxs-lookup"><span data-stu-id="93de6-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="93de6-143">Responda a estas preguntas según considere adecuado.</span><span class="sxs-lookup"><span data-stu-id="93de6-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="93de6-144">La pregunta final pregunta si desea crear otro sitio central.</span><span class="sxs-lookup"><span data-stu-id="93de6-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="93de6-145">Si selecciona **sí**, la herramienta de planeación vuelve a la página sitios centrales.</span><span class="sxs-lookup"><span data-stu-id="93de6-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="93de6-146">Si selecciona **No**, haga clic en **Siguiente** y después en **Dibujar** para mostrar la vista Topología global de nivel alto.</span><span class="sxs-lookup"><span data-stu-id="93de6-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="93de6-147">Para ver una topología que ya existe, haga clic en **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="93de6-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="93de6-148">Haga clic en el archivo .xml que representa la topología guardada anteriormente; a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="93de6-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="93de6-149">La herramienta de planeación muestra la página de topología global.</span><span class="sxs-lookup"><span data-stu-id="93de6-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="93de6-150">Ahora puede empezar a editar, actualizar o cambiar la topología mediante las herramientas disponibles en la herramienta de planificación.</span><span class="sxs-lookup"><span data-stu-id="93de6-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93de6-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="93de6-151">See Also</span></span>


[<span data-ttu-id="93de6-152">Edición del diseño en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93de6-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

