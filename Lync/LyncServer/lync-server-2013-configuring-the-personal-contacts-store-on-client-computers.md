---
title: 'Lync Server 2013: configuración del almacén de contactos personales en equipos cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e035c360d339b48157969c75a1702beff03da634
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="c55db-102">Configuración del almacén de contactos personales en equipos cliente para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c55db-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c55db-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="c55db-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="c55db-104">Si está integrando Microsoft Lync Server 2013 y Microsoft Exchange Server 2013, se recomienda que configure el almacén de contactos personales en todos los equipos cliente que ejecuten Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="c55db-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="c55db-105">En concreto, debe configurar Lync para usar Exchange como almacén de contactos personales y, al mismo tiempo, asegurarse de que los usuarios no pueden invalidar dicha decisión.</span><span class="sxs-lookup"><span data-stu-id="c55db-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="c55db-106">Esto puede hacerse creando y configurando un valor del registro en cada equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="c55db-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="c55db-107">Tenga en cuenta que esto no es necesario en los equipos que ejecutan Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c55db-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="c55db-108">Para configurar este valor en un solo equipo, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="c55db-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="c55db-109">En el equipo cliente, haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c55db-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c55db-110">En el cuadro de diálogo **Ejecutar**, escriba regedit y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c55db-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="c55db-111">En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **software**, expanda **directivas**, expanda **Microsoft**y, a continuación, expanda **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="c55db-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="c55db-112">Haga clic con el botón secundario en **Communicator**, seleccione **nuevo**y, a continuación, haga clic en **valor DWORD (32-bit)**.</span><span class="sxs-lookup"><span data-stu-id="c55db-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="c55db-113">Una vez creado el nuevo valor, escriba **PersonalContactStoreOverride** y, a continuación, presione Entrar para cambiar el nombre del valor.</span><span class="sxs-lookup"><span data-stu-id="c55db-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c55db-114">Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.</span><span class="sxs-lookup"><span data-stu-id="c55db-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="c55db-115">Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c55db-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="c55db-116">Para obtener más información, consulte la documentación de [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543)la Directiva de grupo en.</span><span class="sxs-lookup"><span data-stu-id="c55db-116">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

