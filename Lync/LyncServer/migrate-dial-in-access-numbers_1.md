---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a13fdf36dcd36dc71df8ffa06c273c2b2b0f0292
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="c6cc0-102">Migrar los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="c6cc0-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6cc0-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="c6cc0-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="c6cc0-104">La migración de números de acceso telefónico local requiere dos pasos: ejecutar el cmdlet **Import-CsLegacyConfiguration** (completado anteriormente en [importar directivas y configuración](import-policies-and-settings.md)) para migrar los planes de marcado y otras opciones de configuración de números de acceso telefónico y ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="c6cc0-105">Para migrar los números de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c6cc0-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="c6cc0-106">Abra la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="c6cc0-107">En el árbol de consola, haga clic con el botón secundario en el nodo bosque, haga clic en **propiedades**y, después, en **propiedades del operador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="c6cc0-108">En la ficha **números de teléfono de Access** , haga clic en **servicio por grupo** de servidores para ordenar los números de teléfono de acceso por su grupo asociado e identifique todos los números de acceso para el grupo desde el que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="c6cc0-109">Para identificar el URI del SIP para cada número de acceso, haga doble clic en el número de acceso para abrir el cuadro de diálogo **Editar número del operador de conferencia** y busque en **URI del SIP**.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="c6cc0-110">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="c6cc0-111">Para mover cada número de acceso de acceso telefónico local a un grupo hospedado en Lync Server 2013, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c6cc0-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="c6cc0-112">En la herramienta administrativa de Office Communications Server 2007 R2, en la ficha **números de teléfono de Access** , compruebe que no quedan números de acceso telefónico local para el grupo de Office Communications Server 2007 R2 del que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

