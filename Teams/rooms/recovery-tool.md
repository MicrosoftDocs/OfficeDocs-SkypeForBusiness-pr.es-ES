---
title: Usar la herramienta de recuperación de Sala de Microsoft Teams
ms.author: dstrome
author: dstrome
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
description: En este artículo se describe cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que usaría para poner un sistema actualizado en un estado compatible.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021728"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="00b99-103">Usar la herramienta de recuperación de Sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b99-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="00b99-104">En este artículo se describe cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que usaría para poner un sistema actualizado en un estado compatible.</span><span class="sxs-lookup"><span data-stu-id="00b99-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="00b99-105">Esta herramienta debe aplicarse cuando la consola de Salas de Microsoft Teams muestra un error de "configuración del sistema no actualizada" o antes de realizar un restablecimiento de fábrica con el botón [de inserción.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="00b99-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00b99-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="00b99-106">Prerequisites</span></span>

<span data-ttu-id="00b99-107">Descargue el último paquete de instalación de Salas de Microsoft Teams y [extraigalo](https://go.microsoft.com/fwlink/?linkid=851168) a un Memory Stick USB o a un recurso compartido de red accesible desde el dispositivo Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="00b99-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="00b99-108">La extracción de los archivos desde el MSI se puede conseguir mediante muchos medios.</span><span class="sxs-lookup"><span data-stu-id="00b99-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="00b99-109">Cualquier mecanismo que extraiga todos los archivos y conserve su estructura de directorios es aceptable.</span><span class="sxs-lookup"><span data-stu-id="00b99-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="00b99-110">Una de estas maneras es usar el comando donde representa la ruta completa al paquete de instalación de Microsoft Teams Room y representa la ruta de acceso completa a la carpeta a la que quiere extraer los `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` archivos.</span><span class="sxs-lookup"><span data-stu-id="00b99-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="00b99-111">Ejecución de la herramienta</span><span class="sxs-lookup"><span data-stu-id="00b99-111">Running the tool</span></span>

1) <span data-ttu-id="00b99-112">Inicie sesión en la cuenta de administrador del dispositivo de Salas de Microsoft Teams e inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="00b99-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="00b99-113">Compruebe desde el dispositivo salas de Microsoft Teams el que pueda acceder al archivo que se incluye en los archivos extraídos del paquete de instalación de Salas de `RecoveryTool.ps1 file` Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="00b99-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="00b99-114">El kit puede encontrarse en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="00b99-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="00b99-115">`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="00b99-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="00b99-116">Para realizar una restauración de fábrica:</span><span class="sxs-lookup"><span data-stu-id="00b99-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="00b99-117">Cuando el script se lo solicite, seleccione la opción 2: **Restablecer.**</span><span class="sxs-lookup"><span data-stu-id="00b99-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="00b99-118">Si BitLocker está habilitado, sigue las instrucciones proporcionadas al final del resultado del script para deshabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="00b99-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="00b99-119">Realizar la restauración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="00b99-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="00b99-120">Abra la **aplicación Configuración** y seleccione Actualizar **& Seguridad**</span><span class="sxs-lookup"><span data-stu-id="00b99-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="00b99-121">Vaya a la **pestaña Recuperación.**</span><span class="sxs-lookup"><span data-stu-id="00b99-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="00b99-122">Debajo **de Restablecer este equipo,** **selecciona Introducción**</span><span class="sxs-lookup"><span data-stu-id="00b99-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="00b99-123">Selecciona **Quitar todo,** luego **Siguiente** y **Restablecer**</span><span class="sxs-lookup"><span data-stu-id="00b99-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="00b99-124">El dispositivo Salas de Microsoft Teams puede quedar inutilizable si el comando Mantener mis archivos elimina las aplicaciones y la **configuración,** pero mantiene seleccionada la opción de archivos personales durante el proceso de restablecimiento de Windows.</span><span class="sxs-lookup"><span data-stu-id="00b99-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="00b99-125">No seleccione esta opción.</span><span class="sxs-lookup"><span data-stu-id="00b99-125">Do not select this option.</span></span>
      5. <span data-ttu-id="00b99-126">El sistema se reiniciará varias veces.</span><span class="sxs-lookup"><span data-stu-id="00b99-126">The system will reboot multiple times.</span></span> <span data-ttu-id="00b99-127">Cuando se complete el restablecimiento, el sistema estará en la pantalla de Windows "fuera de la caja" (OOBE).</span><span class="sxs-lookup"><span data-stu-id="00b99-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="00b99-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="00b99-128">See also</span></span>

[<span data-ttu-id="00b99-129">Ayuda de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b99-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="00b99-130">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00b99-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
