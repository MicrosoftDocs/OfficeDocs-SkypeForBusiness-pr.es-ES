---
title: 'Lync Server 2013: restaurar un servidor miembro de Enterprise Edition'
description: 'Lync Server 2013: restaurar un servidor miembro de Enterprise Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576056"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="4d788-103">Restauración de un servidor miembro de Enterprise Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d788-103">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d788-104">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="4d788-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4d788-105">Si se produce un error en un servidor que ejecuta uno de los siguientes roles de servidor, siga el procedimiento de este tema para restaurar el servidor.</span><span class="sxs-lookup"><span data-stu-id="4d788-105">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="4d788-106">Si se producen errores en varios servidores de forma independiente, siga el procedimiento en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="4d788-106">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="4d788-107">Servidor front-end</span><span class="sxs-lookup"><span data-stu-id="4d788-107">Front End Server</span></span>

  - <span data-ttu-id="4d788-108">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="4d788-108">Mediation Server</span></span>

  - <span data-ttu-id="4d788-109">Director</span><span class="sxs-lookup"><span data-stu-id="4d788-109">Director</span></span>

  - <span data-ttu-id="4d788-110">Servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4d788-110">Persistent Chat Server</span></span>

  - <span data-ttu-id="4d788-111">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4d788-111">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4d788-112">Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración.</span><span class="sxs-lookup"><span data-stu-id="4d788-112">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="4d788-113">Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración.</span><span class="sxs-lookup"><span data-stu-id="4d788-113">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="4d788-114">Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="4d788-114">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="4d788-115">Para restaurar un servidor miembro</span><span class="sxs-lookup"><span data-stu-id="4d788-115">To restore a member server</span></span>

1.  <span data-ttu-id="4d788-116">Empiece con un servidor nuevo o limpio que tenga el mismo nombre de dominio completo (FQDN) que el servidor con el error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.</span><span class="sxs-lookup"><span data-stu-id="4d788-116">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d788-117">Siga los procedimientos de implementación de servidores de la organización para realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="4d788-117">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="4d788-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el servidor que va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="4d788-118">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="4d788-119">Vaya a la carpeta o los medios de instalación de Lync Server e inicie el Asistente para la implementación de Lync Server que se encuentra en la \\ instalación de \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="4d788-119">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="4d788-120">Siga el asistente para la implementación para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4d788-120">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="4d788-121">Ejecute el **Paso 1: Instalar el almacén de configuración local** para instalar los archivos de configuración local.</span><span class="sxs-lookup"><span data-stu-id="4d788-121">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="4d788-122">Ejecute el **paso 2: configurar o quitar componentes de Lync Server** para instalar el rol de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d788-122">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="4d788-123">Ejecute el **Paso 3: Solicitar, instalar o asignar certificados** para asignar los certificados.</span><span class="sxs-lookup"><span data-stu-id="4d788-123">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="4d788-124">Ejecute el **Paso 4: Iniciar servicios** para iniciar los servicios en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4d788-124">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="4d788-125">Para obtener más información sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación del rol de servidor que va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="4d788-125">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

