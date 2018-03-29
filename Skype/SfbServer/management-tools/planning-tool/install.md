---
title: Instalar la Herramienta de planeación en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de empezar a diseñar y planear su Skype para la infraestructura de servidor de negocios 2015 utilizando el Skype para la herramienta de planeación de 2015 Business Server, primero debe instalar la herramienta de planeación. La herramienta de planeación no deben implementarse una estación de trabajo o servidor que forma parte del dominio o infraestructura donde planea instalar Skype para Business Server 2015. El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta. Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.
ms.openlocfilehash: 1c5c56031890aaff035e237e2ff7ab6d89d6ba2b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="afb0b-106">Instalar la Herramienta de planeación en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="afb0b-106">Install the Planning Tool in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="afb0b-107">Antes de empezar a diseñar y planear su Skype para la infraestructura de servidor de negocios 2015 utilizando el Skype para la herramienta de planeación de 2015 Business Server, primero debe instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="afb0b-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="afb0b-108">La herramienta de planeación no deben implementarse una estación de trabajo o servidor que forma parte del dominio o infraestructura donde planea instalar Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="afb0b-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="afb0b-109">El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="afb0b-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="afb0b-110">Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="afb0b-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="afb0b-111">La herramienta de planeación requiere instalación por un usuario con derechos de administrador y permisos en el equipo en el que se va a instalar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="afb0b-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span> 
  
<span data-ttu-id="afb0b-112">Los sistemas operativos compatibles para la instalación y el funcionamiento de la herramienta de planeación son:</span><span class="sxs-lookup"><span data-stu-id="afb0b-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>
  
- <span data-ttu-id="afb0b-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="afb0b-113">Windows 10</span></span> 
    
- <span data-ttu-id="afb0b-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="afb0b-114">Windows 8</span></span>
    
- <span data-ttu-id="afb0b-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="afb0b-115">Windows 8.1</span></span>
    
- <span data-ttu-id="afb0b-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="afb0b-116">Windows Server 2012</span></span>
    
- <span data-ttu-id="afb0b-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="afb0b-117">Windows Server 2012 R2</span></span>
    
- <span data-ttu-id="afb0b-118">Edición de 32 bits de Windows 7</span><span class="sxs-lookup"><span data-stu-id="afb0b-118">Windows 7, 32-bit edition</span></span>
    
- <span data-ttu-id="afb0b-119">Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="afb0b-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>
    
- <span data-ttu-id="afb0b-120">Windows Server 2008 R2 usando WOW</span><span class="sxs-lookup"><span data-stu-id="afb0b-120">Windows Server 2008 R2, using WOW</span></span>
    
<span data-ttu-id="afb0b-121">Además, la herramienta de planeación requiere Microsoft.NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="afb0b-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>
  
<span data-ttu-id="afb0b-122">Una vez cumplidos los requisitos de preinstalación, a continuación, puede instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="afb0b-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>
  
## 

### <a name="to-install-the-planning-tool"></a><span data-ttu-id="afb0b-123">Para instalar la Herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="afb0b-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="afb0b-124">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="afb0b-124">Log on to the local computer as a member of the Administrators group.</span></span>
    
2. <span data-ttu-id="afb0b-125">Mediante el Explorador de Windows o una ventana de comandos, busque el directorio donde descargó los archivos de instalación de la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="afb0b-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>
    
3. <span data-ttu-id="afb0b-p103">Busque el archivo SkypeForBusinessPlanningTool.msi. En el Explorador de Windows, haga doble clic en el archivo. En la ventana de línea de comandos, escriba el nombre del archivo y presione **Entrar** para ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="afb0b-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>
    
4. <span data-ttu-id="afb0b-129">En la página principal del **Asistente para la instalación de la herramienta de planeación de Skype Empresarial Server 2015**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afb0b-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>
    
5. <span data-ttu-id="afb0b-130">Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afb0b-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>
    
6. <span data-ttu-id="afb0b-p104">Elija dónde quiere instalar los archivos de la Herramienta de planeación. La ubicación predeterminada es C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**. En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos. Después, haga clic en **Aceptar** y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afb0b-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="afb0b-135">El programa de instalación está preparado para instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="afb0b-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="afb0b-136">Haga clic en **Instalar** para comenzar el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="afb0b-136">Click **Install** to begin the installation process.</span></span>
    
8. <span data-ttu-id="afb0b-p106">La instalación se iniciará y se mostrará el progreso de la misma. Una vez completado el proceso de instalación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="afb0b-p106">The installation will start, and the progress will be displayed. After the installation is successfully completed, click **Finish**.</span></span>
    
9. <span data-ttu-id="afb0b-139">La herramienta de planeación está lista para su uso.</span><span class="sxs-lookup"><span data-stu-id="afb0b-139">The Planning Tool is ready for use.</span></span>
    
## <a name="optional-software"></a><span data-ttu-id="afb0b-140">Optional Software</span><span class="sxs-lookup"><span data-stu-id="afb0b-140">Optional Software</span></span>
<span data-ttu-id="afb0b-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="afb0b-141"></span></span>

<span data-ttu-id="afb0b-142">El Skype para la herramienta de planeación de 2015 Business Server está diseñado para exportar a Microsoft Excel y Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="afb0b-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="afb0b-143">Mientras que estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, agreguen un valor significativo para la instalación y la documentación del diseño.</span><span class="sxs-lookup"><span data-stu-id="afb0b-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>
  
### <a name="microsoft-excel"></a><span data-ttu-id="afb0b-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="afb0b-144">Microsoft Excel</span></span>

<span data-ttu-id="afb0b-145">La exportación de su diseño a Microsoft Excel genera un informe con cuatro pestañas en la hoja de cálculo:</span><span class="sxs-lookup"><span data-stu-id="afb0b-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>
  
- <span data-ttu-id="afb0b-146">Resumen: muestra información sobre la configuración del sitio, incluyendo información de perfil de servidor, configuración de capacidad y recuento de usuarios.</span><span class="sxs-lookup"><span data-stu-id="afb0b-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>
    
- <span data-ttu-id="afb0b-147">Perfil de hardware - muestra un informe con las configuraciones de hardware recomendadas para servidores que se especifican en la topología, incluidos CPU, memoria, disco e interfaz de red.</span><span class="sxs-lookup"><span data-stu-id="afb0b-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="afb0b-148">También contempla la cantidad y las especificaciones recomendadas para los componentes de servidor.</span><span class="sxs-lookup"><span data-stu-id="afb0b-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="afb0b-149">De igual modo, cada servidor está definido por el sitio para proporcionar una representación completa de los requisitos del servidor por sitio.</span><span class="sxs-lookup"><span data-stu-id="afb0b-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>
    
- <span data-ttu-id="afb0b-150">Requisitos de puertos: muestra un informe de todos los puertos están habilitados y la asociación (DNS LB) de equilibrio de carga de sistema de nombres de dominio y equilibradores de carga de hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="afb0b-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="afb0b-151">Este informe es útil para planear las configuraciones de DNS LB y HLB y del firewall.</span><span class="sxs-lookup"><span data-stu-id="afb0b-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>
    
- <span data-ttu-id="afb0b-152">Resumen: muestra el resumen general de los ajustes que sean necesarios para configurar la red del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="afb0b-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>
    
- <span data-ttu-id="afb0b-153">Informe de certificados - muestra el nombre del sujeto y los nombres alternativos de asunto que se requieren para los certificados necesarios para obtener los servidores Edge.</span><span class="sxs-lookup"><span data-stu-id="afb0b-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>
    
- <span data-ttu-id="afb0b-154">Informe - muestra los puertos de origen y de destino y direcciones IP para las interfaces externas e internas del firewall.</span><span class="sxs-lookup"><span data-stu-id="afb0b-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>
    
- <span data-ttu-id="afb0b-155">Informe DNS - muestra el nombre de dominio completo (FQDN) y direcciones IP/VIP requerido por cada entrada DNS que cree.</span><span class="sxs-lookup"><span data-stu-id="afb0b-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>
    
### <a name="microsoft-visio"></a><span data-ttu-id="afb0b-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="afb0b-156">Microsoft Visio</span></span>

<span data-ttu-id="afb0b-p110">La exportación del diseño a Microsoft Visio genera un diagrama para su uso en fines de documentación de la topología y la infraestructura configuradas. El diagrama importado se puede modificar y reorganizar para adaptarlo a sus necesidades de documentación. El típico diagrama de Visio incluirá:</span><span class="sxs-lookup"><span data-stu-id="afb0b-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>
  
> [!NOTE]
> <span data-ttu-id="afb0b-160">Si el diseño es lo suficientemente grande como para requerir más de tres servidores frontales, se creará una página adicional para el grupo de Front-End, servidores frontales, el equipo que ejecuta SQL Server, direcciones IP y nombres de dominio completos.</span><span class="sxs-lookup"><span data-stu-id="afb0b-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span> 
  
- <span data-ttu-id="afb0b-161">Topología global - diagrama de Skype configurado para sitios de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="afb0b-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>
    
- <span data-ttu-id="afb0b-162">Ficha nombre de sitio: muestra la topología de configuración del sitio con el servidor perimetral, firewall, public switched teléfono red (PSTN) con puertas de enlace y la implementación de servidor interno.</span><span class="sxs-lookup"><span data-stu-id="afb0b-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="afb0b-163">Implementación interna consta de servidores configurados y agrupaciones de grupos, incluyendo el Front-End, servidores basados en SQL Server, servicios de dominio de Active Directory, directores, servidores de Exchange Unified Messaging (UM) servidores, servidores de buzones de Exchange, Office Web Apps, Servidores de mediación y los servidores de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="afb0b-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>
    
- <span data-ttu-id="afb0b-164">Diagrama de red: diagrama que detalla la configuración de servidor perimetral con las direcciones IP y los FQDN asociado del borde.</span><span class="sxs-lookup"><span data-stu-id="afb0b-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="afb0b-165">El equilibrio de carga de DNS y los equilibradores de carga de hardware también están incluidos.</span><span class="sxs-lookup"><span data-stu-id="afb0b-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="afb0b-166">Además, el grupo de servidor Front-End o Front-End y directores se muestran, con LB de DNS asociado o HLB y la dirección IP asignada (la herramienta de planeación es compatible con direcciones IPv4 e IPv6) y FQDN.</span><span class="sxs-lookup"><span data-stu-id="afb0b-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="afb0b-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="afb0b-167">See also</span></span>
<span data-ttu-id="afb0b-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="afb0b-168"></span></span>

#### 

[<span data-ttu-id="afb0b-169">Instalación de la herramienta de planificación</span><span class="sxs-lookup"><span data-stu-id="afb0b-169">Installing the Planning Tool</span></span>](http://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)

