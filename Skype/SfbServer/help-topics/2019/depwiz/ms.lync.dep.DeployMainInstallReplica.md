---
title: Instalar almacén de configuración local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Para comenzar la instalación de un nuevo servidor de roles de Skype empresarial, primero debe instalar el servidor SQL Server local que hospedará el almacén de configuración local. El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype empresarial Server.
ms.openlocfilehash: 365529c3c9cb15ea50cd6a482bd2a69143daa219
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794799"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="02d28-104">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="02d28-104">Install Local Configuration Store</span></span>

<span data-ttu-id="02d28-105">Para comenzar la instalación de un nuevo servidor de roles de Skype empresarial, primero debe instalar el servidor SQL Server local que hospedará el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="02d28-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="02d28-106">El almacén de configuración local actuará como una réplica de solo lectura del almacén de administración central (CMS) de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="02d28-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="02d28-107">Necesita iniciar sesión en el servidor que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="02d28-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="02d28-108">Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="02d28-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="02d28-109">El documento de definición del generador de topología se leerá desde el documento de definición exportado en lugar del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="02d28-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="02d28-110">Para exportar el documento de definición del generador de topología y hacer que esté disponible para los servidores perimetrales, vea el tema[exportar su topología y copiarla en medios externos para la instalación perimetral](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="02d28-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="02d28-111">Para empezar la instalación:</span><span class="sxs-lookup"><span data-stu-id="02d28-111">To begin the installation:</span></span>

1. <span data-ttu-id="02d28-112">En la página de Skype empresarial Server, junto a **STEP1: instalar almacén de configuración local**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="02d28-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="02d28-113">En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02d28-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="02d28-114">Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="02d28-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="02d28-115">La instalación del servidor SQL Server local puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="02d28-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="02d28-116">No verá actualizaciones en curso en la pantalla Resumen de la instalación mientras se está instalando SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02d28-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="02d28-117">Si desea supervisar el progreso de la instalación, use el administrador de tareas para ver la configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02d28-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


