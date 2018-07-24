---
title: Instalar almacén de configuración local
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de un nuevo Skype para servidor de rol de servidor empresarial, primero debe instalar al servidor SQL Server local que se va a hospedar el almacén de configuración local. El almacén de configuración local van a actuar como una réplica de sólo lectura de la Skype para el almacén de Administración Central de servidor empresarial (CMS).
ms.openlocfilehash: ab19a45925a25b97e9b1c478c631ee71fe999b83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993673"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="d1946-104">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="d1946-104">Install Local Configuration Store</span></span>
 
<span data-ttu-id="d1946-105">Para comenzar la instalación de un nuevo Skype para servidor de rol de servidor empresarial, primero debe instalar al servidor SQL Server local que se va a hospedar el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="d1946-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="d1946-106">El almacén de configuración local van a actuar como una réplica de sólo lectura de la Skype para el almacén de Administración Central de servidor empresarial (CMS).</span><span class="sxs-lookup"><span data-stu-id="d1946-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="d1946-107">Necesita iniciar sesión en el servidor que ejecute el paso **Instalar almacén de configuración local** como administrador local en el equipo, además de ser miembro del grupo RTCUniversalServerAdmins o del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="d1946-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="d1946-108">Si la instalación se efectúa en un servidor perimetral, no hace falta ser miembro del grupo RTCUniversalServerAdmins ni del grupo RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="d1946-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="d1946-109">El documento de definición de generador de topología se leerán desde el documento exportado definición en lugar de desde el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="d1946-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="d1946-110">Para exportar el documento de definición de generador de topologías y ponerlo a disposición de los servidores perimetrales, vea el tema[exportar la topología y copiar a medios externos para la instalación perimetral](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="d1946-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>
  
<span data-ttu-id="d1946-111">Para empezar la instalación:</span><span class="sxs-lookup"><span data-stu-id="d1946-111">To begin the installation:</span></span>
  
1. <span data-ttu-id="d1946-112">En el Skype para página Business Server, junto a **paso 1: instalar almacén de configuración Local**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d1946-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>
    
2. <span data-ttu-id="d1946-113">En la página **Configuración del servidor local**, compruebe que esté seleccionada la opción **Recuperar la configuración automáticamente del almacén de administración central** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d1946-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>
    
3. <span data-ttu-id="d1946-114">Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d1946-114">When the local server configuration installation is complete, click **Finish**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d1946-115">La instalación del servidor SQL local puede tardar un poco.</span><span class="sxs-lookup"><span data-stu-id="d1946-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="d1946-116">No verá las actualizaciones en progreso en la pantalla de resumen de instalación mientras se instala SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1946-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="d1946-117">Si desea supervisar el progreso de la instalación, use el Administrador de tareas para ver el programa de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1946-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span> 
  

