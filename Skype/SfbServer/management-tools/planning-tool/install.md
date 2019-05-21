---
title: Instalar la Herramienta de planeación en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de empezar a diseñar y planear la infraestructura de Skype empresarial Server 2015 con la herramienta de planeación de Skype empresarial Server 2015, primero debe instalar la herramienta de planeación. No es necesario implementar la herramienta de planeación en una estación de trabajo o servidor que forme parte del dominio o de la infraestructura donde se va a instalar Skype empresarial Server 2015. El archivo Léame que acompaña a la herramienta de planificación detalla información importante sobre la instalación y el uso de la herramienta. Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279130"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="7c4cc-106">Instalar la Herramienta de planeación en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7c4cc-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="7c4cc-107">Antes de empezar a diseñar y planear la infraestructura de Skype empresarial Server 2015 con la herramienta de planeación de Skype empresarial Server 2015, primero debe instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="7c4cc-108">No es necesario implementar la herramienta de planeación en una estación de trabajo o servidor que forme parte del dominio o de la infraestructura donde se va a instalar Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="7c4cc-109">El archivo Léame que acompaña a la herramienta de planificación detalla información importante sobre la instalación y el uso de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="7c4cc-110">Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c4cc-111">La herramienta de Planeación requiere la instalación de un usuario con derechos y permisos de administrador en el equipo en el que se va a instalar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="7c4cc-112">Los sistemas operativos compatibles para la instalación y el funcionamiento de la herramienta de planificación son:</span><span class="sxs-lookup"><span data-stu-id="7c4cc-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="7c4cc-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c4cc-113">Windows 10</span></span>

- <span data-ttu-id="7c4cc-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="7c4cc-114">Windows 8</span></span>

- <span data-ttu-id="7c4cc-115">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="7c4cc-115">Windows 8.1</span></span>

- <span data-ttu-id="7c4cc-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="7c4cc-116">Windows Server 2012</span></span>

- <span data-ttu-id="7c4cc-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7c4cc-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="7c4cc-118">Edición de 32 bits de Windows 7</span><span class="sxs-lookup"><span data-stu-id="7c4cc-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="7c4cc-119">Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="7c4cc-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="7c4cc-120">Windows Server 2008 R2 usando WOW</span><span class="sxs-lookup"><span data-stu-id="7c4cc-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="7c4cc-121">Además, la herramienta de Planeación requiere Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="7c4cc-122">Después de que se cumplan los requisitos de preinstalación, puede instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="7c4cc-123">Para instalar la Herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="7c4cc-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="7c4cc-124">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="7c4cc-125">Con el explorador de Windows o una ventana de comandos, busque el directorio en el que ha descargado los archivos de instalación de la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="7c4cc-p103">Busque el archivo SkypeForBusinessPlanningTool.msi. En el Explorador de Windows, haga doble clic en el archivo. En la ventana de línea de comandos, escriba el nombre del archivo y presione **Entrar** para ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="7c4cc-129">En la página principal del **Asistente para la instalación de la herramienta de planeación de Skype Empresarial Server 2015**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="7c4cc-130">Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="7c4cc-p104">Elija dónde quiere instalar los archivos de la Herramienta de planeación. La ubicación predeterminada es C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**. En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos. Después, haga clic en **Aceptar** y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="7c4cc-135">El instalador ya está listo para instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="7c4cc-136">Haga clic en **Instalar** para comenzar el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="7c4cc-137">La instalación se iniciará y se mostrará el progreso de la misma.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="7c4cc-138">Una vez completado el proceso de instalación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="7c4cc-139">La herramienta de planeación está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="7c4cc-140">Software opcional</span><span class="sxs-lookup"><span data-stu-id="7c4cc-140">Optional Software</span></span>
<span data-ttu-id="7c4cc-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="7c4cc-141"></span></span>

<span data-ttu-id="7c4cc-142">La herramienta de planeación de Skype empresarial Server 2015 está diseñada para exportar a Microsoft Excel y Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="7c4cc-143">Si bien estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, pueden agregar valor significativo a la implementación y la documentación del diseño.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="7c4cc-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="7c4cc-144">Microsoft Excel</span></span>

<span data-ttu-id="7c4cc-145">La exportación de su diseño a Microsoft Excel genera un informe con cuatro pestañas en la hoja de cálculo:</span><span class="sxs-lookup"><span data-stu-id="7c4cc-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="7c4cc-146">Resumen: muestra información sobre la configuración del sitio, incluidos el número de usuarios, la configuración de capacidad y la información de perfil del servidor.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="7c4cc-147">Perfil de hardware: muestra un informe de las configuraciones de hardware recomendadas para los servidores especificados en la topología, como la interfaz de CPU, memoria, disco e red.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="7c4cc-148">También contempla la cantidad y las especificaciones recomendadas para los componentes de servidor.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="7c4cc-149">De igual modo, cada servidor está definido por el sitio para proporcionar una representación completa de los requisitos del servidor por sitio.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="7c4cc-150">Requisitos de puertos: muestra un informe de todos los puertos que están habilitados y la asociación con el equilibrio de carga del sistema de nombres de dominio (DNS LB) y los equilibradores de carga de hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="7c4cc-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="7c4cc-151">Este informe es útil para planear las configuraciones de DNS LB y HLB y del firewall.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="7c4cc-152">Informe Resumen: muestra el resumen general de la configuración necesaria para configurar la red del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="7c4cc-153">Informe de certificados: muestra el nombre del sujeto y los nombres alternativos de asunto necesarios para los certificados necesarios para obtener los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="7c4cc-154">Informe de Firewall: muestra los puertos de origen y de destino, así como las direcciones IP de las interfaces externas e internas.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="7c4cc-155">Informe de DNS: muestra el nombre de dominio completo (FQDN) y las direcciones IP/VIP necesarias para cada entrada de DNS que cree.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="7c4cc-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="7c4cc-156">Microsoft Visio</span></span>

<span data-ttu-id="7c4cc-p110">La exportación del diseño a Microsoft Visio genera un diagrama para su uso en fines de documentación de la topología y la infraestructura configuradas. El diagrama importado se puede modificar y reorganizar para adaptarlo a sus necesidades de documentación. El típico diagrama de Visio incluirá:</span><span class="sxs-lookup"><span data-stu-id="7c4cc-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="7c4cc-160">Si el diseño es lo suficientemente grande para requerir más de tres servidores front-end, se creará una página adicional para el grupo front-end, los servidores front-end, el equipo con SQL Server, las direcciones IP y los FQDN.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="7c4cc-161">Topología global: Diagrama de sitios configurados de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="7c4cc-162">Ficha nombre del sitio: muestra la topología de configuración del sitio con servidor perimetral, firewall, red de telefonía pública conmutada (RTC) con puertas de enlace y la implementación de servidor interno.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="7c4cc-163">La implementación interna consta de servidores y grupos de servidores, entre los que se incluyen las secciones front end, los servidores basados en SQL Server, los servicios de dominio de Active Directory, los directores, los servidores de mensajería unificada de Exchange (UM), los servidores de buzón de Exchange y los servidores de Office Web Apps. Servidores de mediación y servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="7c4cc-164">Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con las direcciones IP y FQDN asociados.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="7c4cc-165">El equilibrio de carga de DNS y los equilibradores de carga de hardware también están incluidos.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="7c4cc-166">Además, se muestran los directores y el servidor front-end o el grupo front-end, con el DNS LB o HLB asociado y la dirección IP asignada (la herramienta de planeación admite direcciones IPv4 e IPv6) y FQDN.</span><span class="sxs-lookup"><span data-stu-id="7c4cc-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c4cc-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c4cc-167">See also</span></span>
<span data-ttu-id="7c4cc-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="7c4cc-168"></span></span>

[<span data-ttu-id="7c4cc-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="7c4cc-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
