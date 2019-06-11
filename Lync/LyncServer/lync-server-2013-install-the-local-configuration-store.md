---
title: 'Lync Server 2013: Instalar el almacén de configuración local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 135dedc38bbc24dd69dfd44b74c70db8e3397252
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="d42f9-102">Instalar el almacén de configuración local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d42f9-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d42f9-103">_**Última modificación del tema:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="d42f9-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="d42f9-104">Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que es un administrador local y un miembro del grupo RTCUniversalReadOnlyAdmin.</span><span class="sxs-lookup"><span data-stu-id="d42f9-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="d42f9-105">Para poder hacer cualquier cosa con el Asistente para la implementación de Lync Server, necesitamos que el almacén de configuración local exista en un servidor.</span><span class="sxs-lookup"><span data-stu-id="d42f9-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="d42f9-106">El almacén de configuración local es una copia de solo lectura del almacén de administración central, que se crea después de la instalación local de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="d42f9-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="d42f9-107">El almacén de administración central se agrega a la base de datos de SQL Server existente instalada en el servidor Standard Edition o en una base de datos basada en SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="d42f9-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d42f9-108">Si aún no ha ejecutado el programa de instalación de Lync Server 2013 en este servidor, se le pedirá una unidad y una ruta de acceso para instalar Lync Server 2013 en.</span><span class="sxs-lookup"><span data-stu-id="d42f9-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="d42f9-109">Esto le permitirá instalar en una unidad distinta de la del sistema, si su organización lo requiere, o si tiene problemas de espacio.</span><span class="sxs-lookup"><span data-stu-id="d42f9-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="d42f9-110">Puede cambiar la ruta de acceso de la ubicación de instalación de los archivos de Lync Server en el cuadro de diálogo de configuración a una nueva unidad disponible.</span><span class="sxs-lookup"><span data-stu-id="d42f9-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="d42f9-111">Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 se implementarán también.</span><span class="sxs-lookup"><span data-stu-id="d42f9-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="d42f9-112">Para instalar el almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="d42f9-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="d42f9-113">Desde los medios de instalación, vaya \\a\\instalar\\AMD64 Setup. exe y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d42f9-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="d42f9-114">Si se le pide que instale el paquete redistribuible de Microsoft Visual C++ 2012, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="d42f9-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="d42f9-115">En la página **Ubicación de instalación de Lync Server 2013** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d42f9-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="d42f9-116">En la página contrato de licencia para el **usuario final** , revise los términos de licencia, deberá seleccionar **acepto las condiciones del contrato de licencia**y, a continuación, hacer clic en **Aceptar** para poder continuar.</span><span class="sxs-lookup"><span data-stu-id="d42f9-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="d42f9-117">En la página Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d42f9-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="d42f9-118">En la página de **Lync Server 2013** , junto a **STEP1: instalar el almacén de configuración local**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d42f9-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="d42f9-119">En la página **Instalar almacén de configuración local**, asegúrese de que la opción **Recuperar directamente del Almacén de administración central** esté seleccionada y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d42f9-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="d42f9-120">Cuando la instalación de configuración del servidor local haya finalizado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d42f9-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

