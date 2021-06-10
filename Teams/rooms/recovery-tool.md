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
description: En este artículo se explica cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que se usaría para poner un sistema des actualizado en un estado compatible.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117498"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="058e7-103">Usar la herramienta de recuperación de Sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="058e7-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="058e7-104">En este artículo se explica cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que se usaría para poner un sistema des actualizado en un estado compatible.</span><span class="sxs-lookup"><span data-stu-id="058e7-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="058e7-105">Esta herramienta se debe aplicar cuando la consola Salas de Microsoft Teams muestra un error "configuración del sistema desconcúe" o antes de realizar una restauración de fábrica de restablecimiento del botón de [inserción.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="058e7-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="058e7-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="058e7-106">Prerequisites</span></span>

<span data-ttu-id="058e7-107">Descargue el último [Salas de Microsoft Teams de](https://go.microsoft.com/fwlink/?linkid=851168) instalación y extraigalo a una memoria USB o a un recurso compartido de red accesible para Salas de Microsoft Teams dispositivo.</span><span class="sxs-lookup"><span data-stu-id="058e7-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="058e7-108">La extracción de los archivos del MSI puede realizarse por muchos medios.</span><span class="sxs-lookup"><span data-stu-id="058e7-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="058e7-109">Cualquier mecanismo que extrae todos los archivos y conserva su estructura de directorios es aceptable.</span><span class="sxs-lookup"><span data-stu-id="058e7-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="058e7-110">Una de estas maneras es usar el comando en el que se representa la ruta de acceso completa al paquete de instalación de sala de Microsoft Teams y representa la ruta de acceso completa a la carpeta a la que le gustaría extraer los `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` archivos.</span><span class="sxs-lookup"><span data-stu-id="058e7-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="058e7-111">Ejecutar la herramienta</span><span class="sxs-lookup"><span data-stu-id="058e7-111">Running the tool</span></span>

1) <span data-ttu-id="058e7-112">Inicie sesión en la cuenta de administrador en Salas de Microsoft Teams dispositivo e inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="058e7-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="058e7-113">Compruebe desde el Salas de Microsoft Teams dispositivo al que puede obtener acceso , que se incluye en los archivos extraídos del Salas de Microsoft Teams `RecoveryTool.ps1 file` de instalación.</span><span class="sxs-lookup"><span data-stu-id="058e7-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="058e7-114">El kit se puede encontrar en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="058e7-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="058e7-115">Ejecutar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .</span><span class="sxs-lookup"><span data-stu-id="058e7-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="058e7-116">Para realizar una restauración de fábrica:</span><span class="sxs-lookup"><span data-stu-id="058e7-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="058e7-117">Cuando se le solicite por el script, seleccione la opción 2: **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="058e7-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="058e7-118">Si BitLocker, siga las instrucciones proporcionadas al final de la salida del script para deshabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="058e7-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="058e7-119">Realice la restauración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="058e7-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="058e7-120">Abra la **Configuración** y seleccione **Actualizar & seguridad**</span><span class="sxs-lookup"><span data-stu-id="058e7-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="058e7-121">Vaya a la **pestaña Recuperación.**</span><span class="sxs-lookup"><span data-stu-id="058e7-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="058e7-122">Debajo **de Restablecer este equipo,** selecciona **Introducción**</span><span class="sxs-lookup"><span data-stu-id="058e7-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="058e7-123">Selecciona **Quitar todo** y, a **continuación, Siguiente** y **Restablecer**</span><span class="sxs-lookup"><span data-stu-id="058e7-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="058e7-124">El Salas de Microsoft Teams puede quedar inutilizable si la opción Mantener mis archivos: quita las aplicaciones y la **configuración,** pero mantiene la opción de archivos personales seleccionada durante el proceso de Windows restablecer.</span><span class="sxs-lookup"><span data-stu-id="058e7-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="058e7-125">No seleccione esta opción.</span><span class="sxs-lookup"><span data-stu-id="058e7-125">Do not select this option.</span></span>
      5. <span data-ttu-id="058e7-126">El sistema se reiniciará varias veces.</span><span class="sxs-lookup"><span data-stu-id="058e7-126">The system will reboot multiple times.</span></span> <span data-ttu-id="058e7-127">Cuando se complete el restablecimiento, el sistema estará en la Windows "experiencia de fuera de la caja" (OOBE).</span><span class="sxs-lookup"><span data-stu-id="058e7-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="058e7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="058e7-128">See also</span></span>

[<span data-ttu-id="058e7-129">Ayuda de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="058e7-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="058e7-130">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="058e7-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)