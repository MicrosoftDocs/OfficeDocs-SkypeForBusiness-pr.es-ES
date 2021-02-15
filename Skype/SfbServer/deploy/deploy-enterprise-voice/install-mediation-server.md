---
title: Instalar los archivos del servidor de mediación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumen: obtenga información sobre cómo instalar los archivos del servidor de mediación en Skype Empresarial Server.'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830800"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="880be-103">Instalar los archivos para el servidor de mediación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="880be-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="880be-104">**Resumen:** Obtenga información sobre cómo instalar los archivos para el servidor de mediación en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="880be-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="880be-105">Para completar correctamente este procedimiento, debe haber iniciado sesión, como mínimo, en el servidor como administrador local y usuario de dominio que sea miembro del grupo RTCUniversalReadOnlyAdmins como mínimo.</span><span class="sxs-lookup"><span data-stu-id="880be-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="880be-106">Siga los pasos de este tema para ejecutar el Asistente para la implementación de Skype Empresarial Server para instalar los archivos del servidor de mediación en un equipo que agregó a un grupo de servidores de mediación después de haber usado el Generador de topologías para definir y publicar el grupo.</span><span class="sxs-lookup"><span data-stu-id="880be-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="880be-107">Al instalar el servidor de mediación de archivos, también se instala y asigna el certificado requerido por cada equipo de un grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="880be-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="880be-108">En este tema se supone que ya ha definido y publicado un grupo de servidores de mediación independiente en su topología, tal como se describe en Implementar un servidor de mediación en el Generador de topologías en [Skype Empresarial Server.](deploy-a-mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="880be-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="880be-109">Para instalar los archivos de un grupo de servidores de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="880be-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="880be-110">En el medio de instalación, haga clic con el botón\Setup\amd64\Setup.exey, a continuación, haga clic _\<installation media\>_ \*\*\*\* en Ejecutar **como administrador.**</span><span class="sxs-lookup"><span data-stu-id="880be-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="880be-111">En la página **Ubicación de** instalación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="880be-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="880be-112">En la **página Contrato de licencia para** el usuario final, haga clic en **Aceptar** y, a continuación, haga clic **en Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="880be-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="880be-113">(Necesario para continuar).</span><span class="sxs-lookup"><span data-stu-id="880be-113">(Required to continue.)</span></span>
    
4. <span data-ttu-id="880be-114">En la página Asistente para la implementación de **Skype Empresarial Server,** haga clic en **Instalar o actualizar el sistema de Skype Empresarial Server.**</span><span class="sxs-lookup"><span data-stu-id="880be-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="880be-115">Junto al **paso 1: Instalar almacén de configuración local,** haga clic en **Ejecutar** y, a continuación, siga las instrucciones en pantalla.</span><span class="sxs-lookup"><span data-stu-id="880be-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="880be-116">En la página Configurar réplica local del almacén de administración **central,** acepte el valor predeterminado **Recuperar** directamente desde el Almacén de administración central y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="880be-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="880be-117">En la **página Ejecutar comandos,** cuando el estado de la tarea se muestra como **Completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="880be-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="880be-118">Junto al **paso 2: Instalar o quitar componentes** de Skype Empresarial Server , haga clic en **Ejecutar** y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="880be-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="880be-119">En la **página Ejecutar comandos,** cuando el estado de la tarea se muestra como **Completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="880be-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="880be-120">Junto al **paso 3: Solicitar, instalar o** asignar certificados, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="880be-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="880be-121">Sigue las instrucciones que aparecen en pantalla y acepta la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="880be-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="880be-122">El servidor de mediación requiere un certificado, por lo que ejecutará el paso **3** dos veces: una vez para emitir el certificado necesario y una vez más para asignarlo.</span><span class="sxs-lookup"><span data-stu-id="880be-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="880be-123">Cuando el certificado se haya emitido y asignado correctamente, junto al paso **4:** Iniciar servicios, haga clic en Ejecutar y, a continuación, siga las instrucciones en pantalla.</span><span class="sxs-lookup"><span data-stu-id="880be-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="880be-124">Cuando **el paso 4 se** haya completado correctamente, reinicie el servidor e inicie sesión en el servidor como miembro del grupo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="880be-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="880be-125">En el equipo donde ejecuta el Panel de control  de Skype Empresarial Server, compruebe en la página Topología del Panel de control de Skype Empresarial Server que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde.</span><span class="sxs-lookup"><span data-stu-id="880be-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="880be-126">Si en su lugar aparece una X roja, seleccione el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="880be-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="880be-127">En el menú **Acción,** haga clic **en Iniciar todos los servicios.**</span><span class="sxs-lookup"><span data-stu-id="880be-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="880be-128">Si agregó más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="880be-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="880be-129">Si no necesita instalar archivos para el servidor de mediación para otros equipos, siga los procedimientos descritos en [Configurar troncos](configure-trunks.md) en Skype Empresarial Server para configurar las opciones de conexión troncal entre este grupo de servidores de mediación (o todos los servidores de mediación de un sitio) y su sistema del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="880be-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

