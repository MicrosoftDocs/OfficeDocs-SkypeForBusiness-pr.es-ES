---
title: Compruebe la conexión a Internet para Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37bd749e44c2020d35a927491553662c74bff01f
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610979"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="801da-102">Compruebe la conexión a Internet para Business Voice</span><span class="sxs-lookup"><span data-stu-id="801da-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="801da-103">Business Voice se encuentra en la nube con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="801da-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="801da-104">Todos los dispositivos que usan Microsoft Teams y Business Voice necesitan una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="801da-104">Every device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="801da-105">Para obtener la mejor experiencia de Business Voice, necesita una conexión a Internet de banda ancha que pueda admitir el máximo número de llamadas telefónicas que su organización podría realizar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="801da-105">To get the best Business Voice experience, you need a broadband Internet connection that can support the maximum number of phone calls that your organization might make at any one time.</span></span> <span data-ttu-id="801da-106">También debe asegurarse de que los equipos de la red pueden conectarse con los servidores de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="801da-106">You also need to make sure that the computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="801da-107">Para seguir estos pasos, debe tener un espacio empresarial con una de las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="801da-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="801da-108">Microsoft 365 Empresa Básico</span><span class="sxs-lookup"><span data-stu-id="801da-108">Microsoft 365 Business Basic</span></span>
* <span data-ttu-id="801da-109">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="801da-109">Microsoft 365 Business Standard</span></span>
* <span data-ttu-id="801da-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="801da-110">Office 365 E1</span></span>
* <span data-ttu-id="801da-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="801da-111">Office 365 E3</span></span>
* <span data-ttu-id="801da-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="801da-112">Office 365 F1</span></span>
* <span data-ttu-id="801da-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="801da-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="801da-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="801da-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="801da-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="801da-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="801da-116">Microsoft 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="801da-116">Microsoft 365 Business</span></span>

<span data-ttu-id="801da-117">No necesita una licencia de Business Voice para seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="801da-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="801da-118">Compruebe la velocidad de la conexión a Internet</span><span class="sxs-lookup"><span data-stu-id="801da-118">Check your Internet connection speed</span></span>

<span data-ttu-id="801da-119">Este artículo le ayudará a determinar si la conexión a Internet es lo suficientemente rápida para el número de personas que necesitan realizar llamadas telefónicas y hospedar videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="801da-119">This article helps determine whether your Internet connection is fast enough for the number of people who need to make phone calls and host video conferences.</span></span> <span data-ttu-id="801da-120">Proporcionará información sobre su organización y recibirá un informe que muestra qué cantidad de su conexión a Internet será usada por Teams y Business Voice.</span><span class="sxs-lookup"><span data-stu-id="801da-120">You'll provide information about your organization and get back a report that shows how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="801da-121">Recopila información sobre la conexión a Internet y los usuarios</span><span class="sxs-lookup"><span data-stu-id="801da-121">Gather information about your Internet connection and users</span></span>

<span data-ttu-id="801da-122">Antes de empezar, necesita la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="801da-122">Before you start, you need the following information:</span></span>

* <span data-ttu-id="801da-123">La velocidad de la conexión a Internet</span><span class="sxs-lookup"><span data-stu-id="801da-123">The speed of your Internet connection</span></span>
* <span data-ttu-id="801da-124">El número de personas que usará Business Voice, principalmente desde su oficina</span><span class="sxs-lookup"><span data-stu-id="801da-124">How many people will use Business Voice mainly from your office</span></span>
* <span data-ttu-id="801da-125">El número de personas que usará Business Voice principalmente desde una ubicación remota, por ejemplo, una oficina en casa</span><span class="sxs-lookup"><span data-stu-id="801da-125">How many people will use Business Voice mainly from a remote location, such as a home office</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="801da-126">Escriba su información en el planificador de red</span><span class="sxs-lookup"><span data-stu-id="801da-126">Enter your information into the network planner</span></span>

<span data-ttu-id="801da-127">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="801da-127">Follow these steps:</span></span>

1. <span data-ttu-id="801da-128">En un explorador, vaya a https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="801da-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="801da-129">Inicie sesión con una cuenta que tenga permisos de Administrador global.</span><span class="sxs-lookup"><span data-stu-id="801da-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="801da-130">La cuenta que usó para conectarse a Microsoft 365 u Office 365 tiene estos permisos.</span><span class="sxs-lookup"><span data-stu-id="801da-130">The account that you used to sign up for Microsoft 365 or Office 365 has these permissions.</span></span>
2. <span data-ttu-id="801da-131">Abra **Planificación** y seleccione **Planeamiento de red**.</span><span class="sxs-lookup"><span data-stu-id="801da-131">Open **Planning** and select **Network planner**.</span></span>
3. <span data-ttu-id="801da-132">En **Planes de red**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="801da-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="801da-133">Escriba un nombre para su plan y después, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="801da-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="801da-134">El plan de red debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="801da-134">Your network plan should look like this:</span></span>

    ![Pantalla principal de Planeamiento de red](../media/network-planner-main.png)
1. <span data-ttu-id="801da-136">Seleccione el nombre de su plan de red.</span><span class="sxs-lookup"><span data-stu-id="801da-136">Select the name of your network plan.</span></span> <span data-ttu-id="801da-137">(Es la **Oficina principal** en la imagen anterior).</span><span class="sxs-lookup"><span data-stu-id="801da-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="801da-138">En la página siguiente, seleccione **Agregar un sitio de red** en la pestaña **Sitios de red**.</span><span class="sxs-lookup"><span data-stu-id="801da-138">On the next page, select **Add a network site** on the **Network sites** tab.</span></span>
3. <span data-ttu-id="801da-139">Rellene solo los campos que se indican en la siguiente captura de pantalla y después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="801da-139">Fill in only the fields that are indicated in the following screenshot, and then select **Save**.</span></span> <span data-ttu-id="801da-140">Deje en blanco los otros campos en esta pantalla y no active las opciones **ExpressRoute** o **Conectado a WAN**.</span><span class="sxs-lookup"><span data-stu-id="801da-140">Leave the other fields on this screen blank, and don't select the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![Información del sitio de Planeamiento de red](../media/network-planner-site-info.png)
1. <span data-ttu-id="801da-142">En la pestaña **Informe**, seleccione **Iniciar un informe**.</span><span class="sxs-lookup"><span data-stu-id="801da-142">On the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="801da-143">Escriba la siguiente información y después, seleccione **Generar informe** para crear un informe que muestre los requisitos de ancho de banda para Teams.</span><span class="sxs-lookup"><span data-stu-id="801da-143">Enter the following information, and then select **Generate report** to create a report that shows the bandwidth requirements for Teams.</span></span> <span data-ttu-id="801da-144">En la siguiente sección se muestra cómo leer el informe.</span><span class="sxs-lookup"><span data-stu-id="801da-144">We show you how to read the report in the next section.</span></span>

    ![Información del informe de Planeamiento de red](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="801da-146">Averigüe cuál es la velocidad mínima de la conexión a Internet</span><span class="sxs-lookup"><span data-stu-id="801da-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="801da-147">Cuando selecciona **Generar informe**, Microsoft 365 u Office 365 crean un informe similar a este:</span><span class="sxs-lookup"><span data-stu-id="801da-147">When you select **Generate report**, Microsoft 365 or Office 365 creates a report that looks like this:</span></span>

![Detalles del informe de Planeamiento de red](../media/network-planner-report.png)

<span data-ttu-id="801da-149">El número resaltado muestra qué proporción de su conexión a Internet usarán Teams y Business Voice.</span><span class="sxs-lookup"><span data-stu-id="801da-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="801da-150">Se recomienda que este número no supere el 30 por ciento de la velocidad total de conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="801da-150">We recommend that this number is no more than 30 percent of your total Internet connection speed.</span></span> <span data-ttu-id="801da-151">Por ejemplo, si su conexión a Internet es de 60 Mbps, Teams y Business Voice no deberían usar más de 18 Mbps.</span><span class="sxs-lookup"><span data-stu-id="801da-151">For example, if your Internet connection is 60 Mbps, Teams and Business Voice should use no more than 18 Mbps.</span></span>

<span data-ttu-id="801da-152">Use esta ecuación para determinar la velocidad mínima de conexión a Internet: *\<highlighted number> / 0,3*.</span><span class="sxs-lookup"><span data-stu-id="801da-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="801da-153">Con el número que está resaltado en la imagen anterior, el cálculo es *4,6875 / 0,3 = 15,6*.</span><span class="sxs-lookup"><span data-stu-id="801da-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="801da-154">En este caso, la velocidad de la conexión a Internet debe ser al menos de 15,6 Mbps.</span><span class="sxs-lookup"><span data-stu-id="801da-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="801da-155">Si Teams y Business Voice usarán más de un 30 por ciento de la velocidad total de conexión a Internet, el número resaltado aparecerá en rojo.</span><span class="sxs-lookup"><span data-stu-id="801da-155">If Teams and Business Voice will use more than 30 percent of your total Internet connection speed, the highlighted number will appear red.</span></span> <span data-ttu-id="801da-156">En ese caso, es posible que tenga que actualizar la conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="801da-156">In that case, you may need to upgrade your Internet connection.</span></span>

![Advertencia de velocidad de conexión](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="801da-158">Asegúrese de que los equipos y dispositivos de su red puedan conectarse a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="801da-158">Make sure the computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="801da-159">Los equipos y dispositivos que usan Business Voice deben usar puertos de red específicos para comunicarse con los servidores de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="801da-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="801da-160">Estos puertos de red son, esencialmente, puertas a través de las que los dispositivos se comunican entre ellos a través de la red o Internet.</span><span class="sxs-lookup"><span data-stu-id="801da-160">These ports are essentially doors through which devices talk to each other over a network or the Internet.</span></span> <span data-ttu-id="801da-161">El firewall necesita permitir que los dispositivos de la red lleguen a Microsoft 365 mediante los siguientes puertos de red de *salida*:</span><span class="sxs-lookup"><span data-stu-id="801da-161">Your firewall needs to allow devices on your network to reach Microsoft 365 through the following *outbound* network ports:</span></span>

* <span data-ttu-id="801da-162">**Puertos TCP** 80 y 443</span><span class="sxs-lookup"><span data-stu-id="801da-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="801da-163">**Puertos UDP** 3478, 3479, 3480 y 3481</span><span class="sxs-lookup"><span data-stu-id="801da-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="801da-164">La forma más sencilla de comprobar si el firewall permite la comunicación en estos puertos de red es realizar una llamada de prueba en Teams:</span><span class="sxs-lookup"><span data-stu-id="801da-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call in Teams:</span></span>

1. <span data-ttu-id="801da-165">Vaya a https://aka.ms/getteams en un equipo de la red e instale Teams.</span><span class="sxs-lookup"><span data-stu-id="801da-165">Go to https://aka.ms/getteams on a computer on your network and install Teams.</span></span> <span data-ttu-id="801da-166">Asegúrese de que el equipo tiene altavoces y un micrófono.</span><span class="sxs-lookup"><span data-stu-id="801da-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="801da-167">Abra Teams e inicie sesión con una cuenta de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="801da-167">Open Teams and sign in by using a Microsoft 365 account.</span></span>
3. <span data-ttu-id="801da-168">En Teams, seleccione su imagen de perfil y después, vaya a **Configuración** > **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="801da-168">In Teams, select your profile picture, and then go to **Settings** > **Devices**.</span></span>
4. <span data-ttu-id="801da-169">En **Dispositivos de audio**, seleccione **Hacer una llamada de prueba**.</span><span class="sxs-lookup"><span data-stu-id="801da-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="801da-170">Siga los pasos para dejar un mensaje y reproducirlo.</span><span class="sxs-lookup"><span data-stu-id="801da-170">Follow the steps to leave a message and have it played back to you.</span></span>

   * <span data-ttu-id="801da-171">Si la llamada se conecta y escucha su mensaje, significa que el firewall está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="801da-171">If the call connects and you hear your message, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="801da-172">Si la llamada se conecta pero no puede escuchar las instrucciones o su mensaje, asegúrese de que los altavoces y el micrófono estén configurados correctamente y vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="801da-172">If the call connects, but you can't hear the instructions or your message, make sure that your speakers and microphone are set up correctly, and then try again.</span></span>
   * <span data-ttu-id="801da-173">Si la llamada no se conecta o si lo hace pero no escucha su mensaje, es posible que necesite actualizar el firewall para permitir el acceso a los puertos de red necesarios.</span><span class="sxs-lookup"><span data-stu-id="801da-173">If the call doesn't connect or it connects but you can't hear your message, you might need to update your firewall to allow access to the required network ports.</span></span> <span data-ttu-id="801da-174">Consulte la documentación del firewall o póngase en contacto con un especialista de TI para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="801da-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="801da-175">Si es un profesional de TI y desea obtener más información sobre cómo preparar redes más grandes o más complejas para que sean compatibles con Business Voice, consulte [Evaluar mi entorno](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="801da-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, see [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="801da-176">Este artículo proporciona información sobre los requisitos de ancho de banda, proxy y firewall, y sobre cómo usar la [Herramienta de evaluación de red](../3-envision-evaluate-my-environment.md#test-the-network) para probar la red.</span><span class="sxs-lookup"><span data-stu-id="801da-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

