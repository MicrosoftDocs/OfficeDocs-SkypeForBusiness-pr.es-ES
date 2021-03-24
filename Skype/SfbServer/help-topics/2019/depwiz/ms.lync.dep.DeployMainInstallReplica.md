---
title: Instalar almacén de configuración local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de un nuevo servidor de roles de Skype Empresarial Server, primero debe instalar el servidor local SQL Server que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype Empresarial Server.
ms.openlocfilehash: 78492f8ce913d8f73336ae4f6cdf06fd340ed5f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095984"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="e9507-104">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="e9507-104">Install Local Configuration Store</span></span>

<span data-ttu-id="e9507-105">Para comenzar la instalación de un nuevo servidor de roles de Skype Empresarial Server, primero debe instalar el servidor local SQL Server que hospedará el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="e9507-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="e9507-106">El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e9507-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="e9507-107">Debe iniciar sesión en el servidor en el que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="e9507-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="e9507-108">Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="e9507-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="e9507-109">El documento de definición del Generador de topologías se leerá del documento de definición exportado en lugar del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="e9507-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="e9507-110">Para exportar el documento de definición del Generador de topologías y hacerlo disponible para los servidores perimetrales, vea el tema[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span><span class="sxs-lookup"><span data-stu-id="e9507-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="e9507-111">Para empezar la instalación:</span><span class="sxs-lookup"><span data-stu-id="e9507-111">To begin the installation:</span></span>

1. <span data-ttu-id="e9507-112">En la página Skype Empresarial Server, junto a **Paso 1: Instalar almacén de configuración local,** haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e9507-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="e9507-113">En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9507-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="e9507-114">Una vez completado el proceso de instalación de configuración del servidor local, haga clic en  **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e9507-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="e9507-115">La instalación de la SQL Server local puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="e9507-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="e9507-116">No verá actualizaciones sobre el progreso en la pantalla de resumen de instalación mientras SQL Server se está instalando.</span><span class="sxs-lookup"><span data-stu-id="e9507-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="e9507-117">Si desea supervisar el progreso de la instalación, use el Administrador de tareas para ver el SQL Server instalación.</span><span class="sxs-lookup"><span data-stu-id="e9507-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>