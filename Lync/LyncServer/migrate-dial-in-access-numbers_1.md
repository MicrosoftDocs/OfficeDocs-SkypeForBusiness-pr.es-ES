---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc96ef027d63c5d2020bd52d55f378fcf7dacf51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503527"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="48d40-102">Migrar los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="48d40-102">Migrate dial-in access numbers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48d40-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="48d40-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="48d40-104">La migración de los números de acceso telefónico local requiere dos pasos: ejecutar el cmdlet **Import-CsLegacyConfiguration** (completado anteriormente en [importar directivas y configuración](import-policies-and-settings.md)) para migrar los planes de marcado y otras opciones de números de acceso telefónico y ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="48d40-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="48d40-105">Para migrar los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="48d40-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="48d40-106">Abra la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="48d40-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="48d40-107">En el árbol de consola, haga clic con el botón secundario en el nodo del bosque, haga clic en **Propiedades** y, a continuación, haga clic en **Propiedades de operador de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="48d40-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="48d40-108">En la ficha **Números de teléfono de acceso**, haga clic en **Servido por grupo de servidores** para ordenar los números de teléfono de acceso por su grupo asociado e identificar todos los números de acceso para el grupo del que está migrando.</span><span class="sxs-lookup"><span data-stu-id="48d40-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="48d40-109">Para identificar el URI del SIP para cada número de acceso, haga doble clic en el número de acceso para abrir el cuadro de diálogo **Editar número de operador de conferencia** y busque en **URI del SIP**.</span><span class="sxs-lookup"><span data-stu-id="48d40-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="48d40-110">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48d40-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="48d40-111">Para mover cada número de acceso telefónico a un grupo hospedado en Lync Server 2013, ejecute:</span><span class="sxs-lookup"><span data-stu-id="48d40-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="48d40-112">En la herramienta administrativa de Office Communications Server 2007 R2, en la pestaña **números de teléfono de acceso** , compruebe que no quedan números de acceso telefónico para el grupo de Office Communications Server 2007 R2 desde el que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="48d40-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

