---
title: 'Lync Server 2013: comprobación de actualizaciones del analizador de procedimientos recomendados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97dff101a581927ba0d508da45b1f648d1b9908
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520617"
---
# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="2d153-102">Buscar actualizaciones en el analizador de procedimientos recomendados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d153-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d153-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2d153-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2d153-104">Cuando se inicia el analizador de procedimientos recomendados, la herramienta le proporciona una opción para buscar las actualizaciones más recientes para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="2d153-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="2d153-105">Si hay una actualización disponible, puede descargar la actualización.</span><span class="sxs-lookup"><span data-stu-id="2d153-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="2d153-106">Si elige no descargar actualizaciones o si el analizador de procedimientos recomendados no puede acceder a Internet, puede seguir usando la versión que ya está en el equipo.</span><span class="sxs-lookup"><span data-stu-id="2d153-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d153-107">Si necesita autenticación de proxy para acceder a Internet, el analizador de procedimientos recomendados no puede tener acceso a las nuevas actualizaciones que puede descargar.</span><span class="sxs-lookup"><span data-stu-id="2d153-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="2d153-108">Sin embargo, puede descargar manualmente la última versión de RtcBPA.msi desde el centro de descarga de Microsoft en <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A> .</span><span class="sxs-lookup"><span data-stu-id="2d153-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="2d153-109">Después de descargar el archivo, puede copiarlo en el equipo en el que desea actualizar el analizador de procedimientos recomendados y usar el archivo. msi para instalar la nueva versión de la herramienta en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="2d153-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="2d153-110">Para actualizar las reglas del analizador de procedimientos recomendados, debe ejecutar la herramienta como administrador en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="2d153-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="2d153-111">Si no ha iniciado sesión con una cuenta que sea miembro del grupo administradores y se han detectado actualizaciones, cierre el analizador de procedimientos recomendados y, a continuación, use el siguiente procedimiento para iniciar el programa.</span><span class="sxs-lookup"><span data-stu-id="2d153-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="2d153-112">Para abrir el analizador de procedimientos recomendados como administrador para buscar actualizaciones</span><span class="sxs-lookup"><span data-stu-id="2d153-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="2d153-113">En un equipo en el que se haya instalado el analizador de procedimientos recomendados, haga clic en **Inicio**, seleccione **Microsoft Lync Server 2013**, haga clic con el botón secundario en **analizador de procedimientos recomendados**y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2d153-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="2d153-114">Especifique las credenciales de una cuenta que sea miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="2d153-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

