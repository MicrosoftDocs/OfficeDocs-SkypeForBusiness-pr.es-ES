---
title: Crear una configuración de archivado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Resumen: obtenga información sobre cómo crear una configuración de archivado para Skype Empresarial Server.'
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817660"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="9893f-103">Crear una configuración de archivado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9893f-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="9893f-104">**Resumen:** Obtenga información sobre cómo crear una configuración de archivado para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9893f-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="9893f-105">Configurar las opciones de archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="9893f-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="9893f-106">Para configurar las opciones de archivado para un sitio o grupo específico:</span><span class="sxs-lookup"><span data-stu-id="9893f-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="9893f-107">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9893f-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9893f-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9893f-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9893f-109">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="9893f-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="9893f-110">En la página **Configuración de archivado**, haga clic en **Nuevo** y elija una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9893f-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="9893f-111">Para crear una configuración de archivado de sitio, haga clic en Configuración del sitio y, **a** continuación, en Seleccionar un sitio, seleccione el sitio que desea configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="9893f-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="9893f-112">Para crear una configuración de archivado de grupo, haga clic en Configuración del grupo de servidores y, **a** continuación, en Seleccionar un grupo, seleccione el grupo que desea configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="9893f-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="9893f-113">En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="9893f-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="9893f-114">Para habilitar el archivado solo para las sesiones de mensajería instantánea, haga clic en **Archivar sesiones de mensajería instantánea**.</span><span class="sxs-lookup"><span data-stu-id="9893f-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="9893f-115">Para habilitar el archivado tanto para las sesiones de mensajería instantánea como para las conferencias web, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="9893f-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="9893f-116">Para deshabilitar el archivado para esta configuración, haga clic **en Deshabilitar archivado.**</span><span class="sxs-lookup"><span data-stu-id="9893f-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="9893f-117">Además, en **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9893f-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="9893f-118">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.</span><span class="sxs-lookup"><span data-stu-id="9893f-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="9893f-119">Para usar Microsoft Exchange Server almacenar datos de archivado, haga clic en la casilla de **integración de Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="9893f-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="9893f-120">Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9893f-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="9893f-121">Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.</span><span class="sxs-lookup"><span data-stu-id="9893f-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="9893f-122">Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.</span><span class="sxs-lookup"><span data-stu-id="9893f-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="9893f-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9893f-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="9893f-124">Configure las opciones de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9893f-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="9893f-125">También puede configurar las opciones de archivado para un sitio o grupo específico mediante el cmdlet **New-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="9893f-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="9893f-126">El comando siguiente crea una colección de valores de configuración de archivado para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="9893f-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="9893f-127">Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9893f-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="9893f-128">Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados.</span><span class="sxs-lookup"><span data-stu-id="9893f-128">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="9893f-129">En el siguiente ejemplo se crea una colección de opciones de configuración de archivado que, de forma predeterminada, solo permiten el archivado de sesiones de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="9893f-129">The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="9893f-p102">Si lo desea, puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando define la nueva configuración para archivar las sesiones de mensajería instantánea y bloquear la mensajería instantánea del servicio de archivado no está disponible:</span><span class="sxs-lookup"><span data-stu-id="9893f-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="9893f-132">Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9893f-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
