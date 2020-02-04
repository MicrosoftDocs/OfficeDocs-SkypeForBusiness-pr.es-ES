---
title: 'Lync Server 2013: Iniciar sesión y utilizar Lync 2013 en la máquina virtual'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40c5c18c4e991c3b53e37e090e7f2d960a32f71c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="0e134-102">Iniciar sesión y utilizar Lync 2013 en la máquina virtual</span><span class="sxs-lookup"><span data-stu-id="0e134-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e134-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0e134-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0e134-104">Después de habilitar el complemento VDI, se realizan los pasos siguientes cuando el usuario inicia sesión en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0e134-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="0e134-105">El usuario escribe sus credenciales en el cliente de Lync 2013 que se ejecuta en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="0e134-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="0e134-106">Una vez que Lync detecta la disponibilidad del complemento VDI, Lync le pide al usuario que vuelva a escribir sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="0e134-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="0e134-107">En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para no tener que escribir las credenciales en inicios de sesión posteriores.</span><span class="sxs-lookup"><span data-stu-id="0e134-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="0e134-108">Lync comienza a emparejarse con el complemento VDI.</span><span class="sxs-lookup"><span data-stu-id="0e134-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="0e134-109">Antes de completar el emparejamiento, el cliente muestra dos iconos en la barra de estado de Lync.</span><span class="sxs-lookup"><span data-stu-id="0e134-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="0e134-110">El icono de la esquina inferior izquierda indica que no hay dispositivos de audio disponibles, y el icono parpadeante en la esquina inferior derecha indica que el emparejamiento de VDI está en curso, tal y como se muestra:</span><span class="sxs-lookup"><span data-stu-id="0e134-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="0e134-111">![Icono de VDI de Lync que muestra el emparejamiento correcto](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icono de VDI de Lync que muestra el emparejamiento correcto")</span><span class="sxs-lookup"><span data-stu-id="0e134-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="0e134-112">Una vez realizado el emparejamiento de VDI, los iconos cambian para indicar el dispositivo de audio que se utilizará para las llamadas y el emparejamiento de VDI:</span><span class="sxs-lookup"><span data-stu-id="0e134-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="0e134-113">![Icono de emparejamiento de VDI de Lync que muestra el éxito](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icono de emparejamiento de VDI de Lync que muestra el éxito")</span><span class="sxs-lookup"><span data-stu-id="0e134-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="0e134-114">Después de que Lync emparejado con el complemento VDI, el usuario puede ver su presencia en dispositivos compatibles con Lync que están conectados al equipo local.</span><span class="sxs-lookup"><span data-stu-id="0e134-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="0e134-115">Ahora, el usuario puede colocar y contestar llamadas como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="0e134-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

