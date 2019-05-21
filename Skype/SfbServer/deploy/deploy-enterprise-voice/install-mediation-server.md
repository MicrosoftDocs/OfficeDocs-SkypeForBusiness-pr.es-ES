---
title: Instalar los archivos para el servidor de mediación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumen: Aprenda a instalar los archivos para el servidor de mediación en Skype empresarial Server.'
ms.openlocfilehash: 8ecd5b20f7f3dfac625851c94f313a50fa71af29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299448"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="f5c6c-103">Instalar los archivos para el servidor de mediación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f5c6c-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f5c6c-104">**Resumen:** Obtenga información sobre cómo instalar los archivos para mediar Server en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="f5c6c-105">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio que pertenezca, como mínimo, al grupo RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="f5c6c-106">Siga los pasos que se indican en este tema para ejecutar el Asistente para la implementación de Skype empresarial Server para instalar los archivos de Media Server en un equipo que haya agregado a un grupo de servidores de mediación después de haber usado el generador de topología para definir y publicar el grupo.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="f5c6c-107">Al instalar el servidor de mediación de archivos, también puede instalar y asignar el certificado requerido por cada equipo de un grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f5c6c-108">En este tema se supone que ya ha definido y publicado un grupo de servidores de mediación independiente en su topología, tal como se describe en [implementar un servidor de mediación en el generador de topologías de Skype empresarial Server](deploy-a-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="f5c6c-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="f5c6c-109">Para instalar los archivos de un grupo de servidores de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="f5c6c-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="f5c6c-110">Desde el medio de instalación, haga clic con el botón secundario en _ \<\> medios de instalación_ **\Setup\amd64\Setup.exe**y, después, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="f5c6c-111">En la página **Ubicación de la instalación**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="f5c6c-p102">En la página **Contrato de licencia para el usuario final**, seleccione **Aceptar** y, a continuación, haga clic en **Aceptar**. (Es necesario para poder continuar).</span><span class="sxs-lookup"><span data-stu-id="f5c6c-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="f5c6c-114">En la página Asistente para la **implementación de Skype empresarial Server** , haga clic en **instalar o actualizar el sistema de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="f5c6c-115">Junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="f5c6c-116">En la página **Configurar réplica local del almacén de administración central**, acepte la opción predeterminada **Recuperar directamente de almacén de administración central**; a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f5c6c-117">En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="f5c6c-118">Junto al **paso 2: configurar o quitar componentes de Skype empresarial Server**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="f5c6c-119">En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="f5c6c-p103">Junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado, por eso el **Paso 3** se debe ejecutar dos veces: una para emitir el certificado requerido y una más para asignarlo.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="f5c6c-123">Una vez se ha emitido y asignado correctamente el certificado, junto a **Paso 4: Iniciar servicios**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="f5c6c-124">Tras completar correctamente el **Paso 4**, reinicie el servidor e inicie sesión en él como miembro del grupo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="f5c6c-125">En el equipo en el que esté ejecutando el panel de control de Skype empresarial Server, compruebe en la página **topología** del panel de control de Skype empresarial Server que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="f5c6c-126">Si en lugar de ello aparece una X de color rojo, seleccione el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="f5c6c-127">En el menú **Acción**, haga clic en **Iniciar todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="f5c6c-128">Si ha agregado más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="f5c6c-129">Si no necesita instalar archivos para el servidor de mediación para otros equipos, siga los procedimientos que se describen en [configurar troncos en Skype empresarial Server](configure-trunks.md) para configurar las opciones de conexión troncal entre este grupo de servidores de mediación (o todo el medio de mediación). Servidores en un sitio) y sus pares.</span><span class="sxs-lookup"><span data-stu-id="f5c6c-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

