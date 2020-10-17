---
title: 'Lync Server 2013: comprobación de la replicación del esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 483a8125969fffc0db2c8f72bca3fc5b8001d943
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527627"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="01784-102">Comprobar la replicación de esquemas de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01784-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01784-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="01784-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="01784-104">Antes de ejecutar la preparación del bosque, compruebe manualmente que la partición del esquema se ha replicado.</span><span class="sxs-lookup"><span data-stu-id="01784-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="01784-105">Para comprobar manualmente la replicación del esquema</span><span class="sxs-lookup"><span data-stu-id="01784-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="01784-106">Inicie sesión en un controlador de dominio como miembro del grupo Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="01784-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="01784-107">Abra el Editor ADSI. Para ello, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, haga clic en **Editor ADSI**.</span><span class="sxs-lookup"><span data-stu-id="01784-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="01784-108">También puede ejecutar <STRONG>adsiedit.msc</STRONG> en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="01784-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="01784-109">En el árbol de Microsoft Management Console (MMC), haga clic en **Editor ADSI** si aún no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="01784-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="01784-110">En el menú **Acción**, haga clic en **Conectar con**.</span><span class="sxs-lookup"><span data-stu-id="01784-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="01784-111">En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="01784-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="01784-112">En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="01784-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="01784-113">Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente.</span><span class="sxs-lookup"><span data-stu-id="01784-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="01784-114">Si este objeto no existe o los valores de los atributos **rangeUpper** y **rangeLower** son distintos de lo que se ha especificado, el esquema no se ha modificado o no se ha replicado.</span><span class="sxs-lookup"><span data-stu-id="01784-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01784-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01784-115">See Also</span></span>


[<span data-ttu-id="01784-116">Ejecución de la preparación del esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01784-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="01784-117">Preparar el esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01784-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

