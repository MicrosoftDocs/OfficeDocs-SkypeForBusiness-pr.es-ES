---
title: 'Lync Server 2013: instalar el almacén de configuración local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 478f45ff682b399f911b41d11a16c802181d14ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="d5e49-102">Instalar el almacén de configuración local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5e49-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5e49-103">_**Última modificación del tema:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="d5e49-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="d5e49-104">Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que sea un administrador local y un miembro del grupo al rtcuniversalreadonlyadmin.</span><span class="sxs-lookup"><span data-stu-id="d5e49-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="d5e49-105">Para poder realizar cualquier acción con el Asistente para la implementación de Lync Server, es necesario que el almacén de configuración local exista en un servidor.</span><span class="sxs-lookup"><span data-stu-id="d5e49-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="d5e49-106">El almacén de configuración local es una copia de solo lectura del almacén de administración central, que se crea después de la instalación local de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="d5e49-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="d5e49-107">El propio almacén de administración central se agrega a la base de datos de SQL Server existente instalada en el servidor Standard Edition o en la base de datos basada en SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="d5e49-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5e49-108">Si no ha ejecutado el programa de instalación de Lync Server 2013 en este servidor, se le pedirá una unidad y una ruta de acceso para instalar Lync Server 2013 en.</span><span class="sxs-lookup"><span data-stu-id="d5e49-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="d5e49-109">Esto le permitirá instalar en una unidad distinta de la unidad del sistema, si su organización la necesita, o si tiene problemas de espacio.</span><span class="sxs-lookup"><span data-stu-id="d5e49-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="d5e49-110">Solo puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server en el cuadro de diálogo de instalación a una unidad nueva y disponible.</span><span class="sxs-lookup"><span data-stu-id="d5e49-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="d5e49-111">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 también se implementarán allí.</span><span class="sxs-lookup"><span data-stu-id="d5e49-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="d5e49-112">Para instalar el almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="d5e49-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="d5e49-113">Desde los medios de instalación, vaya \\a\\Setup\\AMD64 Setup. exe y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5e49-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="d5e49-114">Si se le pide que instale el paquete redistribuible de Microsoft Visual C++ 2012, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="d5e49-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="d5e49-115">En la página **Ubicación de instalación de Lync Server 2013** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5e49-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="d5e49-116">En la página contrato de licencia para el **usuario final** , revise los términos de licencia, debe seleccionar **acepto los términos del contrato de licencia**y, a continuación, haga clic en **Aceptar** para poder continuar.</span><span class="sxs-lookup"><span data-stu-id="d5e49-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="d5e49-117">En la página del asistente para la implementación, haga clic en **Instalar o actualizar el sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d5e49-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="d5e49-118">En la página **Lync Server 2013** , junto a **paso 1: instalar almacén de configuración local**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d5e49-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="d5e49-119">En la página **instalar el almacén de configuración local** , asegúrese de que la opción **recuperar directamente del almacén de administración central** esté seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d5e49-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="d5e49-120">Una vez completada la instalación de configuración del servidor local, debe hacer clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d5e49-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

