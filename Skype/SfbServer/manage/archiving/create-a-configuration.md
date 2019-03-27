---
title: Crear una configuración de archivado en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Resumen: Obtenga información sobre cómo crear una configuración de archivado para Skype para Business Server.'
ms.openlocfilehash: 2a45a627ab8bbeedd18d1cbda636606ebc641745
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881287"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="3a182-103">Crear una configuración de archivado en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3a182-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="3a182-104">**Resumen:** Obtenga información sobre cómo crear una configuración de archivado para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a182-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="3a182-105">Configurar las opciones de archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="3a182-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="3a182-106">Para configurar las opciones de archivado para un sitio o servidor determinado:</span><span class="sxs-lookup"><span data-stu-id="3a182-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="3a182-107">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3a182-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3a182-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3a182-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3a182-109">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="3a182-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="3a182-110">En la página **Configuración de archivado**, haga clic en **Nuevo** y haga una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3a182-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="3a182-111">Para crear una configuración de archivado de sitio, haga clic en **Configuración de sitio** y, en **Seleccionar un sitio**, seleccione el sitio que se va a configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="3a182-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="3a182-112">Para crear una configuración de archivado de grupo de servidores, haga clic en **Configuración del grupo de servidores** y, en **Seleccionar un grupo de servidores**, seleccione el grupo de servidores que se va a configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="3a182-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="3a182-113">En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="3a182-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="3a182-114">Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.</span><span class="sxs-lookup"><span data-stu-id="3a182-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="3a182-115">Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) como para las conferencias web, haga clic en **Archivar sesiones de mensajería instantánea (MI) y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="3a182-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="3a182-116">Para deshabilitar el archivado para esta configuración, haga clic en **Deshabilitar archivado**.</span><span class="sxs-lookup"><span data-stu-id="3a182-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="3a182-117">Además, en **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a182-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="3a182-118">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="3a182-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="3a182-119">Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación de la **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="3a182-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="3a182-120">Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3a182-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="3a182-121">Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="3a182-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="3a182-122">Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.</span><span class="sxs-lookup"><span data-stu-id="3a182-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="3a182-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3a182-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="3a182-124">Configurar las opciones de archivado con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a182-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="3a182-125">También puede configurar las opciones de archivado de un sitio o un grupo determinado con el cmdlet **New-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="3a182-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="3a182-126">El comando siguiente crea una colección de opciones de configuración de archivado para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="3a182-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="3a182-127">Como no se especificó ningún parámetro (aparte del parámetro obligatorio Identity) en el comando anterior, la colección nueva de opciones de configuración usará los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="3a182-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="3a182-p101">Para crear una configuración que use valores de propiedad distintos, incluya el valor del parámetro y el parámetro adecuados. En el siguiente ejemplo, se crea una colección de opciones de configuración que, de forma predeterminada, permite el archivado solo de sesiones de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="3a182-p101">To create settings that use different property values, simply include the appropriate parameter and parameter value. The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="3a182-p102">Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando define la nueva configuración para archivar las sesiones de mensajería instantánea y bloquear la mensajería instantánea si el servicio de archivado no está disponible:</span><span class="sxs-lookup"><span data-stu-id="3a182-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="3a182-132">Para obtener más información, vea el tema de ayuda para el cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="3a182-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
