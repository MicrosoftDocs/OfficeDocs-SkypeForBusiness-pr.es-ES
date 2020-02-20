---
title: Ejecutar LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325a3dab058132dfe6bbf8558ebe771450f36ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a><span data-ttu-id="6b152-102">Ejecutar LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="6b152-102">Run LyncPerfTool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b152-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="6b152-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="6b152-104">Antes de ejecutar la herramienta stress and performance de Lync Server 2013 (LyncPerfTool. exe), debe crear usuarios, contactos y escenarios.</span><span class="sxs-lookup"><span data-stu-id="6b152-104">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="6b152-105">Para obtener información detallada acerca del uso de las herramientas para realizar estas acciones, consulte [Create Users and Contacts](create-users-and-contacts.md) y [Configure User Profile](configure-user-profile.md).</span><span class="sxs-lookup"><span data-stu-id="6b152-105">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="6b152-106">Al ejecutar estas herramientas, también se generará un archivo que ejecutará LyncPerfTool. exe como parte de un archivo por lotes con los parámetros necesarios incluidos.</span><span class="sxs-lookup"><span data-stu-id="6b152-106">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="6b152-107">Ejecución de la herramienta de esfuerzo y rendimiento de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b152-107">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="6b152-108">La herramienta UserProfileGenerator. exe crea un archivo por lotes que permite ejecutar LyncPerfTool. exe mediante el registro de los contadores de rendimiento de LyncPerfTool y la carga del archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="6b152-108">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="6b152-109">El archivo por lotes ejecuta una instancia de LyncPerfTool. exe por cada archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6b152-109">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="6b152-110">Para ejecutar el archivo por lotes, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b152-110">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="6b152-111">Copie la carpeta que contiene los archivos y las carpetas de configuración en el directorio que contiene LyncStressTool. exe en cada equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="6b152-111">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="6b152-112">(Por ejemplo, si ha generado los archivos de configuración en la carpeta denominada\_1,28 13.16.16, copie esa carpeta a la carpeta que contiene LyncPerfTool. exe en cada cliente).</span><span class="sxs-lookup"><span data-stu-id="6b152-112">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="6b152-113">Navegue a la carpeta del cliente con el número adecuado y ejecute el script por lotes RunClient.</span><span class="sxs-lookup"><span data-stu-id="6b152-113">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="6b152-114">Puede simplemente hacer doble clic en el archivo por lotes en el explorador de Windows y ejecutará todos los archivos de configuración de ese número de cliente.</span><span class="sxs-lookup"><span data-stu-id="6b152-114">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="6b152-115">También puede ejecutar el script desde la carpeta del cliente correspondiente mediante la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6b152-115">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="6b152-116">Para ejecutar LyncPerfTool. exe directamente, abra un símbolo del sistema y, a continuación, escriba el comando siguiente en la línea de comandos (cuando haga esto por primera vez, asegúrese de registrar los contadores de rendimiento regsvr32/i/n/s LyncPerfToolPerf. dll, tal y como se muestra en la nota más adelante en este tema\<): LyncPerfTool. exe/File: configXML\></span><span class="sxs-lookup"><span data-stu-id="6b152-116">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="6b152-117">Para que la herramienta muestre los valores en el archivo de configuración, incluya el parámetro/displayfile en el comando anterior, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="6b152-117">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="6b152-118">Para finalizar el proceso, presione Ctrl + C.</span><span class="sxs-lookup"><span data-stu-id="6b152-118">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b152-119">Antes de ejecutar LyncPerfTool directamente, debe registrar los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6b152-119">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="6b152-120">Escriba el siguiente comando para registrar los contadores de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="6b152-120">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="6b152-121">Cada instancia de LyncPerfTool. exe que inicie iniciará inmediatamente la sesión de los usuarios, normalmente a una tasa de un usuario por segundo.</span><span class="sxs-lookup"><span data-stu-id="6b152-121">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="6b152-122">La frecuencia máxima de inicio de sesión de usuario para el grupo es de unos 12 por segundo.</span><span class="sxs-lookup"><span data-stu-id="6b152-122">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="6b152-123">Esto significa que no debe iniciar más de 12 instancias de LyncPerfTool al mismo tiempo, mientras los usuarios aún están iniciando sesión.</span><span class="sxs-lookup"><span data-stu-id="6b152-123">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="6b152-124">1000 los usuarios tardarán unos 20 minutos en iniciar sesión por completo, a una por segundo.</span><span class="sxs-lookup"><span data-stu-id="6b152-124">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b152-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b152-125">See Also</span></span>


[<span data-ttu-id="6b152-126">Crear usuarios y contactos</span><span class="sxs-lookup"><span data-stu-id="6b152-126">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="6b152-127">Configurar el perfil de usuario</span><span class="sxs-lookup"><span data-stu-id="6b152-127">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

