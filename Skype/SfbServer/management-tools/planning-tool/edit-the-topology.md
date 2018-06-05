---
title: Editar la topología en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Una vez completadas las preguntas iniciales de la entrevista, podrá editar las direcciones IP y el nombre de dominio completo (FQDN) del sitio. Para ello, en la página topología Global, haga doble clic en el sitio que desea editar.
ms.openlocfilehash: b47f8b52360b5b286ea11cbeca0d864292e7beaa
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504974"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="5beb8-104">Editar la topología en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5beb8-104">Edit the topology in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5beb8-p102">Una vez completadas las preguntas iniciales de la entrevista, podrá editar las direcciones IP y el nombre de dominio completo (FQDN) del sitio. Para ello, en la página **Topología global**, haga doble clic en el sitio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="5beb8-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>
  
<span data-ttu-id="5beb8-107">La herramienta de planeación muestra la topología de sitios para el sitio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5beb8-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="5beb8-108">En la parte inferior de la página del sitio hay cuatro pestañas:</span><span class="sxs-lookup"><span data-stu-id="5beb8-108">At the bottom of the site page are four tabs:</span></span>
  
![Herramienta de planeación - Topología del sitio](../../media/Planning_Tool_Site_Topology.png)
  
- <span data-ttu-id="5beb8-110">Topología de sitio: la página mostrada actualmente con una descripción general visual de la topología recomendada.</span><span class="sxs-lookup"><span data-stu-id="5beb8-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>
    
- <span data-ttu-id="5beb8-111">Diagrama de red perimetral - la página de diagrama de red perimetral es donde el diseñador realiza la mayor parte del trabajo de la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="5beb8-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="5beb8-112">El diagrama muestra la configuración de red para una Skype recomendada para la topología empresarial Server 2015, con entradas modificables para IP direcciones y del sistema de nombres de dominio (DNS) y los FQDN de los servidores, grupo de servidores y tanto hardware equilibradores de carga.</span><span class="sxs-lookup"><span data-stu-id="5beb8-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>
    
- <span data-ttu-id="5beb8-113">Informe de administración perimetral - el informe de administración perimetral contiene un total de cuatro informes:</span><span class="sxs-lookup"><span data-stu-id="5beb8-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>
    
     ![Página Informe de administración de servidores perimetrales](../../media/Planning_Tool_Summary_Report.png)
  
  - <span data-ttu-id="5beb8-115">Informe de resumen - un informe general de configuración para la configuración de red perimetral.</span><span class="sxs-lookup"><span data-stu-id="5beb8-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="5beb8-116">Si modifica los valores de la página **Diagrama de red perimetral** por los valores de TCP/IP y FQDN de la topología que se usarán en la implementación real, esas direcciones y nombres se representarán aquí.</span><span class="sxs-lookup"><span data-stu-id="5beb8-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="5beb8-117">De lo contrario, se mostrará el texto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5beb8-117">Otherwise, the default text will appear.</span></span>
    
  - <span data-ttu-id="5beb8-118">Informe de certificado - el informe de certificado se enumerará el nombre de sujeto y nombre alternativo de sujeto para los certificados que son necesarios para la topología.</span><span class="sxs-lookup"><span data-stu-id="5beb8-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
  - <span data-ttu-id="5beb8-119">Informe de firewall - del informe de firewall enumera la información necesaria para configurar servidores de seguridad perimetrales en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="5beb8-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="5beb8-120">Esto incluye las direcciones IP (ya sea los valores predeterminados o los modificados), el rol de servidor, el puerto y la IP de origen, el puerto y la IP de destino, el protocolo de transporte, el protocolo de aplicación y las notas relevantes.</span><span class="sxs-lookup"><span data-stu-id="5beb8-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
  - <span data-ttu-id="5beb8-121">Informe de DNS - del informe de DNS enumera información relevante para las entradas DNS que debe crear.</span><span class="sxs-lookup"><span data-stu-id="5beb8-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="5beb8-122">También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para obtener un funcionamiento correcto.</span><span class="sxs-lookup"><span data-stu-id="5beb8-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>
    
- <span data-ttu-id="5beb8-123">Resumen del sitio - el resumen del sitio presenta una visión general de las selecciones realizadas por responder a las preguntas de la entrevista inicial o rellenar los valores de **Diseño de sitios**.</span><span class="sxs-lookup"><span data-stu-id="5beb8-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="5beb8-124">También se muestra información sobre la capacidad.</span><span class="sxs-lookup"><span data-stu-id="5beb8-124">Capacity information is also presented.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5beb8-125">La información de la página Resumen del sitio está personalizada para cada diseño y puede que no contenga todas las secciones o toda la información que se indica aquí.</span><span class="sxs-lookup"><span data-stu-id="5beb8-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span> 
  
## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="5beb8-126">Editar el diagrama de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5beb8-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="5beb8-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="5beb8-127"></span></span>

<span data-ttu-id="5beb8-128">La mayoría del trabajo que hace un diseñador en la Skype para la herramienta de planeación de Business Server 2015 consiste en definir las entradas para las direcciones IP y nombres de dominio completo (FQDN) para las entradas en el diagrama de red.</span><span class="sxs-lookup"><span data-stu-id="5beb8-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="5beb8-129">La información que se especifica en esta página se traduce en los informes y otra información contenida en la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="5beb8-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span> 
  
![Diagrama de red de la Herramienta de planeación](../../media/Planning_Tool_Network_Diagram.png)
  
<span data-ttu-id="5beb8-131">La herramienta de planeación, se crea un diagrama de red con texto predeterminado para las direcciones IP y nombres de dominio completos.</span><span class="sxs-lookup"><span data-stu-id="5beb8-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span> 
  
<span data-ttu-id="5beb8-132">Para editar el diagrama de red y los valores de entrada:</span><span class="sxs-lookup"><span data-stu-id="5beb8-132">To edit the network diagram and input values:</span></span>
  
1. <span data-ttu-id="5beb8-p110">Elija una sección de la red en la cual comenzar a trabajar. Por ejemplo, haga doble clic en el texto, **access1.contoso.com**. En el cuadro de diálogo que se abre, escriba el FQDN real del servidor access1.contoso.com y la dirección IP real en lugar de 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="5beb8-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>
    
2. <span data-ttu-id="5beb8-136">Haga clic en **Aceptar** para guardar las entradas.</span><span class="sxs-lookup"><span data-stu-id="5beb8-136">Click **OK** to save the entries.</span></span>
    
3. <span data-ttu-id="5beb8-137">Continúe con la edición de direcciones IP y FQDN y proporcione direcciones IP virtuales para equilibradores de carga de hardware o entradas de servidores para el equilibrio de carga del Sistema de nombres de dominio (DNS) para servidores incluidos en grupos.</span><span class="sxs-lookup"><span data-stu-id="5beb8-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>
    
<span data-ttu-id="5beb8-p111">Una característica útil de la herramienta de planeación es que puede asignar de forma gradual un rango de direcciones IP y nombres de host de servidor, en lugar de requerir que el diseñador edite por separado cada servidor de un grupo. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5beb8-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>
  
1. <span data-ttu-id="5beb8-p112">Haga doble clic en los servidores front-end agrupados. Cuando se abra el cuadro de diálogo, seleccione **¿Desea usar las direcciones IP y el FQDN como puntos de inicio para todos los servidores equivalentes de este clúster?**.</span><span class="sxs-lookup"><span data-stu-id="5beb8-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span> 
    
2. <span data-ttu-id="5beb8-142">Por ejemplo, el valor de inicio para el primer servidor es fe0101.contoso.com y la dirección IP es 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="5beb8-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>
    
3. <span data-ttu-id="5beb8-143">Escriba fe0.contoso.com en **FQDN de servidor Front-End**, escriba 192.168.21.131 en la **dirección IP de servidor de Front-End**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5beb8-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="5beb8-144">La característica de incremento automático actualiza todos los servidores del grupo a fe01 hasta fe06 y todas las direcciones IP desde 192.168.21.131 hasta 136.</span><span class="sxs-lookup"><span data-stu-id="5beb8-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>
    
<span data-ttu-id="5beb8-145">Una vez completadas todas las modificaciones, guarde la topología. Para ello, siga los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5beb8-145">After you have completed all edits, save the topology by completing the following steps:</span></span> 
  
<span data-ttu-id="5beb8-146">Para guardar el diseño de la herramienta de planeación, haga clic en **archivo**y, a continuación, haga clic en **Guardar topología** o **Guardar topología como**.</span><span class="sxs-lookup"><span data-stu-id="5beb8-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="5beb8-147">Si aparece el cuadro de diálogo **Guardar herramienta de planeación como**, escriba el nombre del archivo en **Nombre de archivo** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5beb8-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5beb8-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="5beb8-148">See also</span></span>
<span data-ttu-id="5beb8-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="5beb8-149"></span></span>

[<span data-ttu-id="5beb8-150">Edición del diseño</span><span class="sxs-lookup"><span data-stu-id="5beb8-150">Editing the Design</span></span>](http://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)