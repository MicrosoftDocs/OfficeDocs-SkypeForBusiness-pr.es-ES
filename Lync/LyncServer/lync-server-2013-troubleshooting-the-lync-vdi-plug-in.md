---
title: 'Lync Server 2013: solución de problemas del complemento VDI de Lync'
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
ms.openlocfilehash: f1dfd8082ef0f0cdfc2a7931a675398507daaa51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="ad8a0-102">Solución de problemas del complemento VDI de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad8a0-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad8a0-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="ad8a0-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="ad8a0-104">Solución de problemas relacionados con la instalación del complemento de VDI para Lync en un cliente ligero</span><span class="sxs-lookup"><span data-stu-id="ad8a0-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="ad8a0-105">Si hay problemas con la instalación del complemento VDI en un cliente ligero, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad8a0-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="ad8a0-106">Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="ad8a0-p101">Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación de su fabricante para obtener más instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="ad8a0-109">Resolución de problemas con el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="ad8a0-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="ad8a0-110">Cuando el emparejamiento de complemento de VDI falla, el icono de emparejamiento de la esquina inferior derecha se muestra como una "X" de color rojo, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="ad8a0-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="ad8a0-111">![Icono de VDI de Lync que muestra el emparejamiento correcto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono de VDI de Lync que muestra el emparejamiento correcto")</span><span class="sxs-lookup"><span data-stu-id="ad8a0-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="ad8a0-112">A continuación se indican las posibles razones por las que se producen errores y las acciones correctivas que puede realizar.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="ad8a0-113">**El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**</span><span class="sxs-lookup"><span data-stu-id="ad8a0-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="ad8a0-114">El usuario debe cerrar la sesión de Lync y volver a iniciar sesión con las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="ad8a0-115">Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="ad8a0-116">**Se está ejecutando otra instancia del cliente de escritorio remoto.**</span><span class="sxs-lookup"><span data-stu-id="ad8a0-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="ad8a0-117">Si usan conexión a escritorio remoto en Windows, los usuarios deben hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad8a0-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="ad8a0-118">Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="ad8a0-119">Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="ad8a0-120">Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**. </span><span class="sxs-lookup"><span data-stu-id="ad8a0-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="ad8a0-121">Inicie una nueva sesión de escritorio remoto e intente establecer la conexión de nuevo. </span><span class="sxs-lookup"><span data-stu-id="ad8a0-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="ad8a0-122">**Los archivos necesarios no se han instalado correctamente.**</span><span class="sxs-lookup"><span data-stu-id="ad8a0-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="ad8a0-123">Después de instalar el complemento en el equipo local, los siguientes archivos deberían estar presentes en C:\\archivos\\de programa Microsoft Office\\Office15 (o la letra de unidad correspondiente):</span><span class="sxs-lookup"><span data-stu-id="ad8a0-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="ad8a0-124">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="ad8a0-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="ad8a0-125">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="ad8a0-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="ad8a0-126">Si hay algún problema con el emparejamiento de VDI, asegúrese de que estos archivos están presentes en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="ad8a0-127">**El cliente de Lync se está ejecutando en el equipo local.**</span><span class="sxs-lookup"><span data-stu-id="ad8a0-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="ad8a0-128">Para usar el complemento de VDI para Lync, un cliente de Lync no debe estar ejecutándose en el equipo local; de lo contrario, se producirá un error de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="ad8a0-129">Como práctica recomendada, el usuario no debe instalar un cliente de Lync en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

