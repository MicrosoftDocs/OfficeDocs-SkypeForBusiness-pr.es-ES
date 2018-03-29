---
title: Instalar almacén de configuración local
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Para comenzar la instalación de un nuevo Skype para servidor de funciones de servidor de negocios 2015, primero debe instalar al local de SQL Server que alojará el almacén de configuración local. El almacén de configuración local actuará como una réplica de sólo lectura de la Skype para el almacén de Administración Central de Business Server (CMS). Debe ser iniciado sesión en el servidor que está ejecutando el paso de almacenamiento de configuración Local de instalación como administrador local en el equipo y pertenencia la RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición de generador de topología se leerán desde el documento de definición exportados en lugar de desde el almacén de Administración Central. Para exportar el documento de definición de generador de topología y ponerla a disposición de los servidores perimetrales, vea el tema exportar su topología y copiar a medios externos para la instalación de borde.
ms.openlocfilehash: adce98e053b6959c3513885fc53f1616df1c1125
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="bb439-108">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="bb439-108">Install Local Configuration Store</span></span>
 
<span data-ttu-id="bb439-109">Para comenzar la instalación de un nuevo Skype para servidor de funciones de servidor de negocios 2015, primero debe instalar al local de SQL Server que alojará el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="bb439-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="bb439-110">El almacén de configuración local actuará como una réplica de sólo lectura de la Skype para el almacén de Administración Central de Business Server (CMS).</span><span class="sxs-lookup"><span data-stu-id="bb439-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="bb439-111">Necesita iniciar sesión en el servidor que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="bb439-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="bb439-112">Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="bb439-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="bb439-113">El documento de definición de generador de topología se leerán desde el documento de definición exportados en lugar de desde el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="bb439-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="bb439-114">Para exportar el documento de definición de generador de topología y ponerla a disposición de los servidores perimetrales, vea el tema[exportar su topología y copiar a medios externos para la instalación de borde](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="bb439-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>
  
<span data-ttu-id="bb439-115">Para empezar la instalación:</span><span class="sxs-lookup"><span data-stu-id="bb439-115">To begin the installation:</span></span>
  
1. <span data-ttu-id="bb439-116">En el Skype para página Business Server 2015, junto a **paso 1: almacenamiento de configuración Local de instalación**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bb439-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>
    
2. <span data-ttu-id="bb439-117">En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb439-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>
    
3. <span data-ttu-id="bb439-118">Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb439-118">When the local server configuration installation is complete, click **Finish**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb439-119">La instalación de los locales de SQL Server puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="bb439-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="bb439-120">No verá las actualizaciones sobre el progreso en la pantalla Resumen de la instalación mientras se instala SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bb439-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="bb439-121">Si desea supervisar el progreso de la instalación, utilice el Administrador de tareas para ver el programa de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bb439-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span> 
  

