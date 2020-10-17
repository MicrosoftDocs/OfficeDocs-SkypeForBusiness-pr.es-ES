---
title: 'Lync Server 2013: solución de problemas del complemento Lync VDI'
description: 'Lync Server 2013: solución de problemas del complemento Lync VDI.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd2c0e3c8a47225f00ce280706dea2287e4dc8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548946"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="3ad61-103">Solución de problemas del complemento Lync VDI en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ad61-103">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ad61-104">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="3ad61-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="3ad61-105">Solución de problemas con la instalación del complemento Lync VDI en un cliente ligero</span><span class="sxs-lookup"><span data-stu-id="3ad61-105">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="3ad61-106">Si encuentra problemas con la instalación del complemento VDI en un cliente ligero, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ad61-106">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="3ad61-107">Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.</span><span class="sxs-lookup"><span data-stu-id="3ad61-107">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="3ad61-p101">Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación de su fabricante para obtener más instrucciones.</span><span class="sxs-lookup"><span data-stu-id="3ad61-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="3ad61-110">Resolución de problemas con el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="3ad61-110">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="3ad61-111">Cuando el emparejamiento con el complemento VDI no funcione, el icono de emparejamiento de la parte inferior derecha mostrará una “X” de color rojo tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="3ad61-111">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="3ad61-112">![Icono de VDI de Lync que muestra el emparejamiento correcto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono de VDI de Lync que muestra el emparejamiento correcto")</span><span class="sxs-lookup"><span data-stu-id="3ad61-112">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="3ad61-113">A continuación se describen posibles razones para los errores, así como las acciones de corrección que puede llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="3ad61-113">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="3ad61-114">**El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**</span><span class="sxs-lookup"><span data-stu-id="3ad61-114">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="3ad61-115">El usuario debe cerrar la sesión de Lync e iniciarla de nuevo con las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="3ad61-115">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="3ad61-116">Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ad61-116">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="3ad61-117">**Se está ejecutando otra instancia del cliente de escritorio remoto.**</span><span class="sxs-lookup"><span data-stu-id="3ad61-117">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="3ad61-118">Si usa conexión a escritorio remoto en Windows, los usuarios deben hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ad61-118">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="3ad61-119">Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="3ad61-119">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="3ad61-120">Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="3ad61-120">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="3ad61-121">Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**.</span><span class="sxs-lookup"><span data-stu-id="3ad61-121">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="3ad61-122">Inicie una nueva sesión de escritorio remoto e intente realizar la conexión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="3ad61-122">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="3ad61-123">**Los archivos necesarios no se han instalado correctamente.**</span><span class="sxs-lookup"><span data-stu-id="3ad61-123">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="3ad61-124">Una vez instalado el complemento en el equipo local, los siguientes archivos deben estar presentes en C: archivos de \\ programa \\ Microsoft Office \\ Office15 (o la letra de unidad correspondiente):</span><span class="sxs-lookup"><span data-stu-id="3ad61-124">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="3ad61-125">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="3ad61-125">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="3ad61-126">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="3ad61-126">UcVdi.dll</span></span>
    
    <span data-ttu-id="3ad61-127">Si hay problemas con el emparejamiento VDI, asegúrese de que estos archivos se encuentran en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="3ad61-127">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="3ad61-128">**El cliente de Lync se está ejecutando en el equipo local.**</span><span class="sxs-lookup"><span data-stu-id="3ad61-128">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="3ad61-129">Para usar el complemento VDI para Lync, un cliente de Lync no debe estar en ejecución en el equipo local; de lo contrario, se producirá un error de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="3ad61-129">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="3ad61-130">Como procedimiento recomendado, el usuario no debe instalar un cliente de Lync en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="3ad61-130">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

