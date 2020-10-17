---
title: 'Lync Server 2013: configuración de Windows 8 para tarjetas inteligentes virtuales'
description: 'Lync Server 2013: configurar Windows 8 para tarjetas inteligentes virtuales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112047f91a20dd552c628fb33eba7bb9ad3d0f01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542166"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="b3798-103">Configurar Windows 8 para usar tarjetas inteligentes virtuales con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3798-103">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3798-104">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="b3798-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="b3798-105">Un factor a tener en cuenta al implementar la autenticación en dos fases y la tecnología de tarjetas inteligentes es el costo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b3798-105">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="b3798-106">Windows 8 proporciona una serie de nuevas capacidades de seguridad y una de las características nuevas más interesantes es la compatibilidad con tarjetas inteligentes virtuales.</span><span class="sxs-lookup"><span data-stu-id="b3798-106">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="b3798-107">Para los equipos que disponen de un chip de módulo de plataforma segura (TPM) que cumple la versión 1,2 de la especificación, las organizaciones ahora pueden obtener las ventajas del inicio de sesión con tarjeta inteligente sin necesidad de realizar ninguna inversión adicional en el hardware.</span><span class="sxs-lookup"><span data-stu-id="b3798-107">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="b3798-108">Para obtener más información, consulte uso de tarjetas inteligentes virtuales con Windows 8 en [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) .</span><span class="sxs-lookup"><span data-stu-id="b3798-108">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="b3798-109">Para configurar Windows 8 para tarjetas inteligentes virtuales</span><span class="sxs-lookup"><span data-stu-id="b3798-109">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="b3798-110">Inicie sesión en el equipo con Windows 8 con las credenciales de un usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="b3798-110">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="b3798-111">En la pantalla de inicio de Windows 8, mueva el cursor a la esquina inferior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="b3798-111">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="b3798-112">Seleccione la opción de **búsqueda** y, a continuación, busque el **símbolo del sistema**.</span><span class="sxs-lookup"><span data-stu-id="b3798-112">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="b3798-113">Haga clic con el botón secundario en **símbolo del sistema**y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b3798-113">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="b3798-114">Abra la consola de administración del módulo de plataforma segura (TPM) ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b3798-114">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="b3798-115">En la consola de administración de TPM, compruebe que la versión de la especificación de TPM sea como mínimo de 1,2</span><span class="sxs-lookup"><span data-stu-id="b3798-115">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3798-116">Si recibe un cuadro de diálogo que indica que no se encuentra un módulo de plataforma de confianza (TPM) compatible, compruebe que el equipo tenga un módulo TPM compatible y que esté habilitado en el BIOS del sistema.</span><span class="sxs-lookup"><span data-stu-id="b3798-116">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="b3798-117">Cerrar la consola de administración de TPM</span><span class="sxs-lookup"><span data-stu-id="b3798-117">Close the TPM management console</span></span>

8.  <span data-ttu-id="b3798-118">Desde el símbolo del sistema, cree una nueva tarjeta inteligente virtual con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b3798-118">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3798-119">Para proporcionar un valor PIN personalizado al crear la tarjeta inteligente virtual, use/PIN prompt en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b3798-119">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="b3798-120">Desde el símbolo del sistema, abra la consola de administración de equipos ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b3798-120">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="b3798-121">En la consola de administración de equipos, seleccione **Administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b3798-121">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="b3798-122">Expanda **lectores de tarjetas inteligentes**.</span><span class="sxs-lookup"><span data-stu-id="b3798-122">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="b3798-123">Compruebe que el nuevo lector de tarjetas inteligentes virtuales se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b3798-123">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

