---
title: Comprobar la conexión a Internet
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4dbfd1bdaec48ebe8c6adbed86da431a6f4ecbfc
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972281"
---
# <a name="check-your-internet-connection"></a><span data-ttu-id="4abc9-102">Comprobar la conexión a Internet</span><span class="sxs-lookup"><span data-stu-id="4abc9-102">Check your Internet connection</span></span>

<span data-ttu-id="4abc9-103">Business Voice se encuentra en la nube con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4abc9-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="4abc9-104">Todos los equipos y dispositivos que usan Microsoft Teams y Business Voice necesitan una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="4abc9-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span> <span data-ttu-id="4abc9-105">Para obtener la mejor experiencia con Business Voice, necesita una conexión a Internet de banda ancha que sea compatible con el número de llamadas telefónicas que se espera que se realicen en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="4abc9-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="4abc9-106">También tiene que asegurarse de que los equipos de la red pueden conectarse con los servidores de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4abc9-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="4abc9-107">Para seguir estos pasos, debe tener un espacio empresarial con una de las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="4abc9-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="4abc9-108">Office 365 Empresa Essentials</span><span class="sxs-lookup"><span data-stu-id="4abc9-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="4abc9-109">Office 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="4abc9-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="4abc9-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="4abc9-110">Office 365 Enterprise E1</span></span>
* <span data-ttu-id="4abc9-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="4abc9-111">Office 365 Enterprise E3</span></span>
* <span data-ttu-id="4abc9-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="4abc9-112">Office 365 Enterprise F1</span></span>
* <span data-ttu-id="4abc9-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="4abc9-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="4abc9-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="4abc9-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="4abc9-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="4abc9-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="4abc9-116">Microsoft 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="4abc9-116">Microsoft 365 Business</span></span>

<span data-ttu-id="4abc9-117">No necesita una licencia de Business Voice para seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4abc9-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="4abc9-118">Compruebe la velocidad de la conexión a Internet</span><span class="sxs-lookup"><span data-stu-id="4abc9-118">Check your Internet connection speed</span></span>

<span data-ttu-id="4abc9-119">Este artículo le ayudará a determinar si la conexión a Internet es lo suficientemente rápida para el número de personas que necesitan realizar llamadas telefónicas, hospedar videoconferencias, etc.</span><span class="sxs-lookup"><span data-stu-id="4abc9-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="4abc9-120">Introducirá información acerca de su organización y recibirá un informe en el que se indicará la proporción de conexión a Internet que usarán Teams y Business Voice.</span><span class="sxs-lookup"><span data-stu-id="4abc9-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="get-information-about-your-internet-connection-and-users"></a><span data-ttu-id="4abc9-121">Obtener información sobre la conexión a Internet y los usuarios</span><span class="sxs-lookup"><span data-stu-id="4abc9-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="4abc9-122">Antes de empezar, debe averiguar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="4abc9-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="4abc9-123">La velocidad de la conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="4abc9-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="4abc9-124">El número de usuarios que usará Business Voice principalmente desde su oficina.</span><span class="sxs-lookup"><span data-stu-id="4abc9-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="4abc9-125">La cantidad de personas que usará Business Voice principalmente desde una ubicación remota, por ejemplo, una oficina en casa.</span><span class="sxs-lookup"><span data-stu-id="4abc9-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="4abc9-126">Escriba su información en el Planeamiento de red</span><span class="sxs-lookup"><span data-stu-id="4abc9-126">Enter your information into the network planner</span></span>

<span data-ttu-id="4abc9-127">Esto es lo que tiene que hacer:</span><span class="sxs-lookup"><span data-stu-id="4abc9-127">Here's what you need to do:</span></span>

1. <span data-ttu-id="4abc9-128">Abra un explorador, vaya a https://admin.teams.microsoft.com e inicie sesión con una cuenta que tenga permisos de administrador global.</span><span class="sxs-lookup"><span data-stu-id="4abc9-128">Open a browser and go to https://admin.teams.microsoft.com and sign in with an account that has Global Administrator permissions.</span></span> <span data-ttu-id="4abc9-129">La cuenta que usó para registrarse en Office 365 tiene estos permisos.</span><span class="sxs-lookup"><span data-stu-id="4abc9-129">The account you used to sign up for Office 365 has these permissions.</span></span>
1. <span data-ttu-id="4abc9-130">Abra **configuración para toda la organización** y, después, seleccione **Planeamiento de red**.</span><span class="sxs-lookup"><span data-stu-id="4abc9-130">Open **Org-wide settings** and then select **Network planner**.</span></span>
1. <span data-ttu-id="4abc9-131">En **Planes de red**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4abc9-131">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="4abc9-132">Asigne un nombre a su plan y, después, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="4abc9-132">Give your plan a name, and then select **Apply**.</span></span> <span data-ttu-id="4abc9-133">El plan de red debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="4abc9-133">Your network plan should look like this:</span></span>

    ![Pantalla principal de Planeamiento de red](../media/network-planner-main.png)
1. <span data-ttu-id="4abc9-135">Haga clic en el nombre del plan de red (**Oficina principal** en la imagen anterior).</span><span class="sxs-lookup"><span data-stu-id="4abc9-135">Click on your network plan's name (**Main office** in the picture above).</span></span>
1. <span data-ttu-id="4abc9-136">En la página siguiente, seleccione **Agregar un sitio de red** en la pestaña **Sitios de red**.</span><span class="sxs-lookup"><span data-stu-id="4abc9-136">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
1. <span data-ttu-id="4abc9-137">Rellene la información siguiente y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4abc9-137">Fill out the following information and then select **Save**.</span></span>

    ![Información del sitio de Planeamiento de red](../media/network-planner-site-info.png)
1. <span data-ttu-id="4abc9-139">En la pestaña **Informe**, seleccione **Iniciar un informe**.</span><span class="sxs-lookup"><span data-stu-id="4abc9-139">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="4abc9-140">Rellene la información siguiente y, a continuación, seleccione **Guardar informe**</span><span class="sxs-lookup"><span data-stu-id="4abc9-140">Fill out the following information and then select **Generate report**</span></span>

    ![Información del informe de Planeamiento de red](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="4abc9-142">Averigüe cuál es la velocidad mínima de la conexión a Internet</span><span class="sxs-lookup"><span data-stu-id="4abc9-142">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="4abc9-143">Cuando selecciona **Generar informe**, Office 365 crea un informe similar a este:</span><span class="sxs-lookup"><span data-stu-id="4abc9-143">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![Detalles del informe de Planeamiento de red](../media/network-planner-report.png)

<span data-ttu-id="4abc9-145">El número resaltado muestra qué proporción de su conexión a Internet usarán Teams y Business Voice.</span><span class="sxs-lookup"><span data-stu-id="4abc9-145">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="4abc9-146">Se recomienda que este número no supere el 30 % de la velocidad total de conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="4abc9-146">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="4abc9-147">Por ejemplo, si su conexión a Internet es 60 Mbps, Teams y Business Voice no deben ocupar más de 18 Mbps.</span><span class="sxs-lookup"><span data-stu-id="4abc9-147">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="4abc9-148">Para averiguar la velocidad de conexión a Internet mínima, haga este cálculo: `<highlighted number> / .3`.</span><span class="sxs-lookup"><span data-stu-id="4abc9-148">You can find your minimum Internet connection speed by doing this calculation: `<highlighted number> / .3`.</span></span> <span data-ttu-id="4abc9-149">Si usa el número resaltado de la imagen anterior, el cálculo sería `4.6875 / .3 = 15.6`.</span><span class="sxs-lookup"><span data-stu-id="4abc9-149">Using the highlighted number in the picture above, the calculation would be `4.6875 / .3 = 15.6`.</span></span> <span data-ttu-id="4abc9-150">Esto significa que la velocidad mínima de conexión a Internet debe ser de al menos 15,6 Mbps.</span><span class="sxs-lookup"><span data-stu-id="4abc9-150">This means your minimum Internet connection speed needs to be at least 15.6Mbps.</span></span>

<span data-ttu-id="4abc9-151">Si Teams y Business Voice van a usar más de un 30 % de la velocidad total de conexión a Internet, el número resaltado se mostrará en rojo.</span><span class="sxs-lookup"><span data-stu-id="4abc9-151">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="4abc9-152">Si esto ocurre, es posible que tenga que actualizar la conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="4abc9-152">If this happens, you might need to upgrade your Internet connection.</span></span>

![Advertencia de velocidad de conexión](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="4abc9-154">Asegúrese de que los equipos y dispositivos de su red puedan conectarse a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4abc9-154">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="4abc9-155">Para funcionar correctamente, los equipos y dispositivos que desee usar con Business Voice necesitan comunicarse con servidores de Microsoft 365 que usen puertos de red específicos.</span><span class="sxs-lookup"><span data-stu-id="4abc9-155">To work correctly, computers and devices you want to use with Business Voice need to communicate with Microsoft 365 servers using specific network ports.</span></span> <span data-ttu-id="4abc9-156">Los puertos de red son, esencialmente, las puertas a través de las que los equipos y dispositivos pueden comunicarse entre sí por la red o por Internet.</span><span class="sxs-lookup"><span data-stu-id="4abc9-156">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="4abc9-157">El firewall necesita permitir que equipos y dispositivos de la red lleguen a Microsoft 365 mediante los siguientes puertos de red de salida:</span><span class="sxs-lookup"><span data-stu-id="4abc9-157">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="4abc9-158">**Puertos TCP** 80 y 443</span><span class="sxs-lookup"><span data-stu-id="4abc9-158">TCP ports 80 and 443 outgoing from clients that will use Teams</span></span>
* <span data-ttu-id="4abc9-159">**Puertos UDP** 3478, 3479, 3480 y 3481</span><span class="sxs-lookup"><span data-stu-id="4abc9-159">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="4abc9-160">La forma más sencilla de comprobar si el firewall permite la comunicación en estos puertos de red es realizar una llamada de prueba con Teams.</span><span class="sxs-lookup"><span data-stu-id="4abc9-160">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span> <span data-ttu-id="4abc9-161">Para realizar una llamada de prueba, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4abc9-161">To make a test call, do the following:</span></span>

1. <span data-ttu-id="4abc9-162">Vaya a https://aka.ms/getteams en un equipo de la red para instalar Teams.</span><span class="sxs-lookup"><span data-stu-id="4abc9-162">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="4abc9-163">Asegúrese de que los altavoces y un micrófono estén conectados a este equipo.</span><span class="sxs-lookup"><span data-stu-id="4abc9-163">Make sure speakers and a microphone are connected to this computer.</span></span>
2. <span data-ttu-id="4abc9-164">Abra Teams e inicie sesión con una cuenta de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4abc9-164">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="4abc9-165">En Teams, seleccione su imagen de perfil y, a continuación, **Configuración** > **Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="4abc9-165">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="4abc9-166">Elija **Realizar una llamada de prueba** en **Dispositivos de audio**</span><span class="sxs-lookup"><span data-stu-id="4abc9-166">Choose **Make a test call** under **Audio devices**</span></span>
5. <span data-ttu-id="4abc9-167">Siga las indicaciones para dejar un mensaje y pedir que se lo reproduzcan</span><span class="sxs-lookup"><span data-stu-id="4abc9-167">Follow the prompts to leave a message and have it played back to you</span></span>

* <span data-ttu-id="4abc9-168">Si la llamada se conecta y puede escuchar su mensaje grabado, el firewall está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4abc9-168">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
* <span data-ttu-id="4abc9-169">Si la llamada se conecta pero no oye las preguntas o el mensaje grabado, asegúrese de que el equipo y los parlantes estén configurados correctamente y que el equipo los haya detectado.</span><span class="sxs-lookup"><span data-stu-id="4abc9-169">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span> <span data-ttu-id="4abc9-170">Inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="4abc9-170">Try again.</span></span>
* <span data-ttu-id="4abc9-171">Si la llamada no se conecta o si lo hace pero no escucha su mensaje grabado, es posible que tenga que actualizar el firewall para permitir los puertos de red enumerados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4abc9-171">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="4abc9-172">Consulte la documentación del firewall para saber cómo permitir que los puertos de red lleguen a Internet o póngase en contacto con un especialista de TI para que le ayude.</span><span class="sxs-lookup"><span data-stu-id="4abc9-172">Check your firewall's documentation on how to allow network ports to reach the Internet, or contact an IT specialist to help you.</span></span>

<span data-ttu-id="4abc9-173">Si es un profesional de TI y desea obtener más información sobre cómo preparar redes más grandes o de mayor complejidad para que sean compatibles con Business Voice, eche un vistazo a [Evaluar mi entorno](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4abc9-173">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="4abc9-174">El artículo [Evaluar mi entorno](../3-envision-evaluate-my-environment.md) ofrece información adicional sobre los requisitos de ancho de banda, proxy y firewall, y también sobre cómo probar la red con la [Herramienta de evaluación de red](../3-envision-evaluate-my-environment.md#test-the-network).</span><span class="sxs-lookup"><span data-stu-id="4abc9-174">The [Evaluate my environment](../3-envision-evaluate-my-environment.md) article gives additional information about bandwidth, proxy, and firewall requirements and also how to test your network using the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network).</span></span>
