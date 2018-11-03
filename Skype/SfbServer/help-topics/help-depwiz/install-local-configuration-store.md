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
description: Para comenzar la instalación de un nuevo Skype para servidor de funciones de Business Server 2015, primero debe instalar al servidor SQL Server local que se va a hospedar el almacén de configuración local. El almacén de configuración local van a actuar como una réplica de sólo lectura de la Skype para el almacén de Administración Central de servidor empresarial (CMS). Necesita iniciar sesión en el servidor que ejecute el paso Instalar almacén de configuración local como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup. Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup. El documento de definición de generador de topología se leerán desde el documento exportado definición en lugar de desde el almacén de Administración Central. Para exportar el documento de definición de generador de topologías y ponerlo a disposición de los servidores perimetrales, vea el tema exportar la topología y copiar a medios externos para la instalación perimetral.
ms.openlocfilehash: f9abb450b03aae7b7b188f527069a6a5b268a30f
ms.sourcegitcommit: f9410a182f571d2a8ebe71ecd91ec97f83d8e077
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2018
ms.locfileid: "25942861"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="30267-108">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="30267-108">Install Local Configuration Store</span></span>

<span data-ttu-id="30267-109">Para comenzar la instalación de un nuevo Skype para servidor de funciones de Business Server 2015, primero debe instalar al servidor SQL Server local que se va a hospedar el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="30267-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="30267-110">El almacén de configuración local van a actuar como una réplica de sólo lectura de la Skype para el almacén de Administración Central de servidor empresarial (CMS).</span><span class="sxs-lookup"><span data-stu-id="30267-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="30267-111">Necesita iniciar sesión en el servidor que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="30267-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="30267-112">Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="30267-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="30267-113">El documento de definición de generador de topología se leerán desde el documento exportado definición en lugar de desde el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="30267-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="30267-114">Para exportar el documento de definición de generador de topologías y ponerlo a disposición de los servidores perimetrales, vea el tema [exportar la topología y copiar a medios externos para la instalación perimetral](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="30267-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="30267-115">Para empezar la instalación:</span><span class="sxs-lookup"><span data-stu-id="30267-115">To begin the installation:</span></span>

1. <span data-ttu-id="30267-116">En el Skype para página Business Server 2015, junto a **paso 1: instalar almacén de configuración Local**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="30267-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="30267-117">En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="30267-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="30267-118">Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="30267-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="30267-119">La instalación del servidor SQL local puede tardar un poco.</span><span class="sxs-lookup"><span data-stu-id="30267-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="30267-120">No verá las actualizaciones en progreso en la pantalla de resumen de instalación mientras se instala SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30267-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="30267-121">Si desea supervisar el progreso de la instalación, use el Administrador de tareas para ver el programa de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30267-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


