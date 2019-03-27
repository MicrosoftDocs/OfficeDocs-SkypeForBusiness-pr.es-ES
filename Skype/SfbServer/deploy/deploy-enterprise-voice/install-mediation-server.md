---
title: Instalar los archivos para el servidor de mediación en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumen: Obtenga información sobre cómo instalar los archivos para el servidor de mediación en Skype para Business Server.'
ms.openlocfilehash: ab02655dc812815c79720d76c87bfefe91c90c73
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877541"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="78bb8-103">Instalar los archivos para el servidor de mediación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="78bb8-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="78bb8-104">**Resumen:** Obtenga información sobre cómo instalar los archivos para el servidor de mediación en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="78bb8-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="78bb8-105">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio que pertenezca, como mínimo, al grupo RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="78bb8-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="78bb8-106">Use los pasos de este tema para ejecutar Skype para el Asistente para la implementación empresarial Server instalar los archivos para el servidor de mediación en un equipo que ha agregado a un grupo de servidores de mediación después de utilizar el generador de topología para definir y publicar el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="78bb8-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="78bb8-107">Al instalar los archivos de servidor de mediación, también instalar y asignar el certificado requerido por cada equipo en un grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="78bb8-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="78bb8-108">En este tema se da por supuesto que ya ha definido y ha publicado un grupo de servidores de mediación independiente en la topología, tal y como se describe en [implementar un servidor de mediación en el generador de Skype para Business Server](deploy-a-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="78bb8-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="78bb8-109">Para instalar los archivos de un grupo de servidores de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="78bb8-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="78bb8-110">Desde los medios de instalación, haga clic con el botón _ \<medios de instalación de\> _ **\Setup\amd64\Setup.exe**y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="78bb8-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="78bb8-111">En la página **Ubicación de la instalación**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78bb8-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="78bb8-p102">En la página **Contrato de licencia para el usuario final**, seleccione **Aceptar** y, a continuación, haga clic en **Aceptar**. (Es necesario para poder continuar).</span><span class="sxs-lookup"><span data-stu-id="78bb8-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="78bb8-114">En la página de **Skype para el Asistente para la implementación de Business Server** , haga clic en **instalar o actualización de Skype para Business Server System**.</span><span class="sxs-lookup"><span data-stu-id="78bb8-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="78bb8-115">Junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.</span><span class="sxs-lookup"><span data-stu-id="78bb8-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="78bb8-116">En la página **Configurar réplica local del almacén de administración central**, acepte la opción predeterminada **Recuperar directamente de almacén de administración central**; a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78bb8-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="78bb8-117">En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="78bb8-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="78bb8-118">Junto a **paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="78bb8-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="78bb8-119">En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="78bb8-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="78bb8-p103">Junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado, por eso el **Paso 3** se debe ejecutar dos veces: una para emitir el certificado requerido y una más para asignarlo.</span><span class="sxs-lookup"><span data-stu-id="78bb8-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="78bb8-123">Una vez se ha emitido y asignado correctamente el certificado, junto a **Paso 4: Iniciar servicios**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.</span><span class="sxs-lookup"><span data-stu-id="78bb8-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="78bb8-124">Tras completar correctamente el **Paso 4**, reinicie el servidor e inicie sesión en él como miembro del grupo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="78bb8-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="78bb8-125">En el equipo donde se ejecuta Skype para el Panel de Control de servidor empresarial, compruebe en la página de **topología** de Skype para el Panel de Control de servidor empresarial que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde.</span><span class="sxs-lookup"><span data-stu-id="78bb8-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="78bb8-126">Si en lugar de ello aparece una X de color rojo, seleccione el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="78bb8-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="78bb8-127">En el menú **Acción**, haga clic en **Iniciar todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="78bb8-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="78bb8-128">Si agrega más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos en el grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="78bb8-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="78bb8-129">Si no es necesario instalar archivos para servidor de mediación para los demás equipos, a continuación, siga los procedimientos descritos en [Configure troncos en Skype para Business Server](configure-trunks.md) para configurar las opciones para la conexión del tronco entre este grupo de servidores de servidor de mediación (o mediación todos los Los servidores en un sitio) y su mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="78bb8-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

