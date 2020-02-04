---
title: Crear o modificar una colección de opciones de configuración de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8dca9-102">Crear o modificar una colección de opciones de configuración de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dca9-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dca9-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8dca9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8dca9-104">Al instalar Lync Server, obtiene una colección global de la configuración de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="8dca9-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="8dca9-105">Esta configuración se aplica a todos los dispositivos que ejecutan Lync Phone Edition en su implementación.</span><span class="sxs-lookup"><span data-stu-id="8dca9-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="8dca9-106">Puedes cambiar esta configuración en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="8dca9-106">You can change these settings at any time.</span></span> <span data-ttu-id="8dca9-107">También puede configurar una nueva colección de opciones de configuración que se apliquen a los dispositivos de un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="8dca9-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="8dca9-108">La configuración del sitio tiene prioridad sobre la configuración global.</span><span class="sxs-lookup"><span data-stu-id="8dca9-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="8dca9-109">Las opciones de configuración consisten en el nombre de la colección, el ámbito (global o sitio), la configuración de seguridad SIP, el nivel de registro, la calidad de servicio (QoS) de voz, la configuración de bloqueo de teléfono y el bloqueo de teléfono, es decir, cuánto tiempo se desbloquea el número de identificación personal ( PIN) debe ser y b el teléfono permanecerá inactivo antes de bloquearse.</span><span class="sxs-lookup"><span data-stu-id="8dca9-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="8dca9-110">Para crear una colección de opciones de configuración de Lync Phone Edition o editar la configuración de una colección existente</span><span class="sxs-lookup"><span data-stu-id="8dca9-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="8dca9-111">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8dca9-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8dca9-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dca9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8dca9-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8dca9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8dca9-114">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **configuración de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="8dca9-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="8dca9-115">En la página **configuración de dispositivo** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="8dca9-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="8dca9-116">Para crear una nueva colección de opciones de configuración de Lync Phone Edition, haga clic en **nuevo**, seleccione un sitio, haga clic en **Aceptar**, revise la configuración predeterminada y, si lo desea, realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="8dca9-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="8dca9-117">Para modificar la configuración de una colección existente, haga clic en la colección, haga clic en el menú **Editar** , haga clic en **Mostrar detalles**y, a continuación, realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="8dca9-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="8dca9-118">Para volver a usar la configuración predeterminada de la colección global, haga clic en la colección global, haga clic en el menú <STRONG>Editar</STRONG> , haga clic en <STRONG>eliminar</STRONG>y, a continuación, haga clic en <STRONG>Aceptar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8dca9-118">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>.</span></span> <span data-ttu-id="8dca9-119">Esto no eliminará la colección global; simplemente restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8dca9-119">This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="8dca9-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8dca9-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8dca9-121">Crear nuevas opciones de configuración de Lync Phone Edition con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dca9-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8dca9-122">Puede crear opciones de configuración de Lync Phone Edition (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet **New-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8dca9-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="8dca9-123">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8dca9-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8dca9-124">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="8dca9-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="8dca9-125">Para crear una nueva configuración de Lync Phone Edition que use los valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="8dca9-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="8dca9-126">Este comando crea un nuevo conjunto de parámetros de configuración del teléfono UC para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="8dca9-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="8dca9-127">Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="8dca9-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="8dca9-128">Para cambiar un único valor de propiedad al crear nuevas opciones de configuración de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8dca9-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="8dca9-129">Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados.</span><span class="sxs-lookup"><span data-stu-id="8dca9-129">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="8dca9-130">Por ejemplo, para crear una colección de opciones de configuración de teléfono UC que, de forma predeterminada, requieren bloqueo de teléfono, use un comando como este:</span><span class="sxs-lookup"><span data-stu-id="8dca9-130">For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="8dca9-131">Para cambiar varios valores de propiedad al crear nuevas opciones de configuración de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8dca9-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="8dca9-132">Puede incluir varios parámetros para modificar varios valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8dca9-132">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="8dca9-133">Por ejemplo, este comando aplica bloqueo de teléfono y establece también la longitud mínima del PIN en 8 dígitos:</span><span class="sxs-lookup"><span data-stu-id="8dca9-133">For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="8dca9-134">Para obtener más información, vea [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="8dca9-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8dca9-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dca9-135">See Also</span></span>


[<span data-ttu-id="8dca9-136">Eliminar una colección existente de opciones de configuración de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dca9-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="8dca9-137">Establecer la configuración de seguridad de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dca9-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="8dca9-138">Exigir el bloqueo de teléfono en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dca9-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

