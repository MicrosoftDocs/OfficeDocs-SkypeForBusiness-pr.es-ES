---
title: Usar la herramienta de recuperación de Sala de Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este artículo se describe cómo usar la herramienta de recuperación para salas de Microsoft Teams, que se usaría para poner un sistema obsoleto en un estado compatible.
ms.openlocfilehash: 755a85c9013d160197c8a8d57f74ef18b207e052
ms.sourcegitcommit: 3d393ceded4d64963411cfdc96931952d480ded5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225284"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="5f4c7-103">Usar la herramienta de recuperación de Sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f4c7-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="5f4c7-104">En este artículo se describe cómo usar la herramienta de recuperación para salas de Microsoft Teams, que se usaría para poner un sistema obsoleto en un estado compatible.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="5f4c7-105">Esta herramienta se debe aplicar cuando la consola de Microsoft Team Rooms muestra el error "configuración del sistema fuera de la fecha" o antes de realizar un botón de [inserción.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="5f4c7-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5f4c7-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5f4c7-106">Prerequisites</span></span>

<span data-ttu-id="5f4c7-107">Descargue el [paquete de instalación de Microsoft Team Rooms](https://go.microsoft.com/fwlink/?linkid=851168) más reciente y extráigalo en un Memory stick USB o en un recurso compartido de red accesible para el dispositivo de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="5f4c7-108">La extracción de los archivos desde el MSI puede hacerse con muchos medios.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="5f4c7-109">Cualquier mecanismo que extrae todos los archivos y conserva su estructura de directorios es aceptable.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="5f4c7-110">Una de estas maneras es usar el comando `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` donde `PathToMsi` representa la ruta de acceso completa al paquete de instalación de Microsoft Teams Room y `PathToTarget` representa la ruta de acceso completa de la carpeta en la que desea que se extraigan los archivos.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="5f4c7-111">Ejecutar la herramienta</span><span class="sxs-lookup"><span data-stu-id="5f4c7-111">Running the tool</span></span>

1) <span data-ttu-id="5f4c7-112">Inicie sesión en la cuenta de administrador en el dispositivo de salas de Microsoft Teams e inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="5f4c7-113">Compruebe en el dispositivo de salas de Microsoft Teams a la que tiene `RecoveryTool.ps1 file`acceso el, que está incluido en los archivos extraídos del paquete de instalación de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="5f4c7-114">El kit puede encontrarse en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="5f4c7-115">Ejecutar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="5f4c7-116">Si va a realizar una restauración de fábrica:</span><span class="sxs-lookup"><span data-stu-id="5f4c7-116">If you are performing a factory restore:</span></span>
   - <span data-ttu-id="5f4c7-117">Cuando el script le solicite, seleccione la opción 2: **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-117">When prompted by the script select option 2: **Reset**.</span></span>
   - <span data-ttu-id="5f4c7-118">Si BitLocker está activado, siga las instrucciones que se proporcionan al final de la salida del script para deshabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   - <span data-ttu-id="5f4c7-119">Realice la restauración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-119">Perform the factory restore.</span></span>
      - <span data-ttu-id="5f4c7-120">Abra la aplicación **configuración** y seleccione **Actualizar & seguridad** .</span><span class="sxs-lookup"><span data-stu-id="5f4c7-120">Open the **Settings** app, and select **Update & Security**</span></span>
      - <span data-ttu-id="5f4c7-121">Vaya a la pestaña **recuperación** .</span><span class="sxs-lookup"><span data-stu-id="5f4c7-121">Navigate to the **Recovery** tab.</span></span>
      - <span data-ttu-id="5f4c7-122">Debajo de **restablecer este equipo**, **Seleccione introducción**</span><span class="sxs-lookup"><span data-stu-id="5f4c7-122">Beneath **Reset this PC**, select **Get started**</span></span>
      - <span data-ttu-id="5f4c7-123">Seleccione **quitar todo**y, a continuación, **siguiente** y **restablecer**</span><span class="sxs-lookup"><span data-stu-id="5f4c7-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
      - <span data-ttu-id="5f4c7-124">El sistema se reiniciará varias veces.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-124">The system will reboot multiple times.</span></span> <span data-ttu-id="5f4c7-125">Cuando se complete el restablecimiento, el sistema aparecerá en la pantalla de Windows OOBE.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-125">When the reset is complete, the system will be at the Windows OOBE screen.</span></span>
5) <span data-ttu-id="5f4c7-126">Si está reparando un sistema "obsoleto":</span><span class="sxs-lookup"><span data-stu-id="5f4c7-126">If you are repairing an "out of date" system:</span></span>
    - <span data-ttu-id="5f4c7-127">Cuando el script le solicite, seleccione la opción 1: **reparar**.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-127">When prompted by the script select option 1: **Repair**.</span></span>
    - <span data-ttu-id="5f4c7-128">Al finalizar, reinicie el dispositivo de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-128">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="5f4c7-129">Se reiniciará de nuevo automáticamente y se recargará por completo la segunda vez.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-129">It will reboot again automatically and come up fully recovered the second time.</span></span>

> [!NOTE]
> <span data-ttu-id="5f4c7-130">Existe un problema conocido por el que las salas de Microsoft Teams pueden quedar inutilizables si la opción **mantener mis archivos: quita las aplicaciones y la configuración, pero mantiene su opción de archivos personales** está seleccionada durante el proceso de restablecimiento de Windows.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-130">There is a known issue where the Microsoft Teams Rooms can become unusable if the  **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="5f4c7-131">*No* use esta opción.</span><span class="sxs-lookup"><span data-stu-id="5f4c7-131">Do *not* use this option.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f4c7-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f4c7-132">See also</span></span>

[<span data-ttu-id="5f4c7-133">Ayuda de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f4c7-133">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="5f4c7-134">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f4c7-134">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
