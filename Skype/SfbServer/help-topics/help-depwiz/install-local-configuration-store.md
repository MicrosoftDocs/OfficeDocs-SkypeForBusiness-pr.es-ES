---
title: Instalar almacén de configuración local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Para iniciar la instalación de un nuevo servidor de roles de Skype Empresarial Server 2015, primero debe instalar el SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype Empresarial Server. Debe iniciar sesión en el servidor en el que ejecute el paso Instalar almacén de configuración local como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición del Generador de topologías se leerá desde el documento de definición exportado en lugar del almacén de administración central. Para exportar el documento de definición del Generador de topologías y que esté disponible para los servidores perimetrales, consulte el tema Export Your Topology and Copy It to External Media for Edge Installation.
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827150"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="6e8fc-108">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="6e8fc-108">Install Local Configuration Store</span></span>

<span data-ttu-id="6e8fc-109">Para iniciar la instalación de un nuevo servidor de roles de Skype Empresarial Server 2015, primero debe instalar el SQL Server local que hospedará el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="6e8fc-110">El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="6e8fc-111">Debe iniciar sesión en el servidor en el que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="6e8fc-112">Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="6e8fc-113">El documento de definición del Generador de topologías se leerá desde el documento de definición exportado en lugar del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="6e8fc-114">Para exportar el documento de definición del Generador de topologías y que esté disponible para los servidores perimetrales, consulte el tema [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="6e8fc-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="6e8fc-115">Para empezar la instalación:</span><span class="sxs-lookup"><span data-stu-id="6e8fc-115">To begin the installation:</span></span>

1. <span data-ttu-id="6e8fc-116">En la página de Skype Empresarial Server 2015, junto a **Paso 1:** Instalar almacén de configuración local, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="6e8fc-117">En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="6e8fc-118">Una vez completado el proceso de instalación de configuración del servidor local, haga clic en  **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="6e8fc-119">La instalación de las SQL Server local puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="6e8fc-120">No verá actualizaciones en curso en la pantalla de resumen de la instalación mientras SQL Server se está instalando.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="6e8fc-121">Si desea supervisar el progreso de la instalación, use el Administrador de tareas para ver el SQL Server instalación.</span><span class="sxs-lookup"><span data-stu-id="6e8fc-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


