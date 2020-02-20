---
title: Configurar el perfil de usuario
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45d9c18045af3a3fba94070c5f1aa6e04f2b3fb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="3eba0-102">Configurar el perfil de usuario</span><span class="sxs-lookup"><span data-stu-id="3eba0-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eba0-103">_**Última modificación del tema:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="3eba0-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="3eba0-104">Las herramientas incluidas en el paquete de la herramienta de esfuerzo y rendimiento de Lync Server 2013 permiten crear y configurar cuentas de usuario de prueba que puede usar para ejecutar simulaciones de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="3eba0-105">Use la herramienta de creación de usuarios de Lync Server 2013 para crear los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3eba0-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="3eba0-106">(Para obtener más información, consulte [Create Users and Contacts](create-users-and-contacts.md)). Una vez creados los usuarios, configure los perfiles de usuario con la herramienta de configuración de carga de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3eba0-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="3eba0-107">Ejecución de la herramienta de configuración de carga de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3eba0-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="3eba0-108">Para configurar los perfiles de usuario, ejecute la herramienta de configuración de carga de Lync Server 2013 (UserProfileGenerator. exe) y rellene cada una de las pestañas.</span><span class="sxs-lookup"><span data-stu-id="3eba0-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="3eba0-109">UserProfileGenerator. exe genera un directorio para cada uno de los equipos cliente que necesita para ejecutar la simulación.</span><span class="sxs-lookup"><span data-stu-id="3eba0-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="3eba0-110">Cada directorio de cliente también incluye un script para iniciar todas las instancias de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool. exe).</span><span class="sxs-lookup"><span data-stu-id="3eba0-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3eba0-111">Los valores específicos del usuario especificados en UserProfileGenerator deben coincidir con los valores especificados en la herramienta de creación de usuarios de Lync Server 2013 (UserProvisioningTool) para el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3eba0-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="3eba0-112">Rellene los campos de cada ficha de la herramienta de configuración de carga de Lync Server 2013, tal y como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="3eba0-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="3eba0-113">Configuración común</span><span class="sxs-lookup"><span data-stu-id="3eba0-113">Common Configuration</span></span>

<span data-ttu-id="3eba0-114">La ficha **configuración común** de la herramienta de configuración de carga de Lync Server 2013 se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="3eba0-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="3eba0-115">Rellene los campos de la ficha **configuración común** , tal y como se describe en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="3eba0-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="3eba0-116">![Ficha Configuración común.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Ficha Configuración común.")</span><span class="sxs-lookup"><span data-stu-id="3eba0-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="3eba0-117">En **número de equipos disponibles**, escriba o haga clic en el número de equipos que desea usar para ejecutar LyncPerfTool. exe.</span><span class="sxs-lookup"><span data-stu-id="3eba0-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="3eba0-118">Le recomendamos que tenga un equipo por cada 4.500 usuarios que vaya a simular.</span><span class="sxs-lookup"><span data-stu-id="3eba0-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="3eba0-119">Ese número puede variar si se reduce el nivel de carga o si solo se usa un subconjunto de las características disponibles.</span><span class="sxs-lookup"><span data-stu-id="3eba0-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="3eba0-120">(Los niveles de carga se establecen en la ficha **escenarios generales** ).</span><span class="sxs-lookup"><span data-stu-id="3eba0-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="3eba0-121">En **prefijo para los nombres de usuario**, escriba el prefijo del nombre de usuario de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3eba0-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="3eba0-122">Para iniciar sesión, el identificador uniforme de recursos (URI) será: UserPrefix\[índice de inicio de usuario... (Número de usuarios: 1) \]@User dominio.</span><span class="sxs-lookup"><span data-stu-id="3eba0-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="3eba0-123">En **contraseña para todos los usuarios**, escriba la contraseña que se usó para crear los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3eba0-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="3eba0-124">Si deja este campo en blanco, el nombre de usuario se usará como la contraseña.</span><span class="sxs-lookup"><span data-stu-id="3eba0-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="3eba0-125">En **Índice de inicio de usuario**, haga clic o escriba el índice del primer usuario que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="3eba0-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="3eba0-126">Puede configurar diferentes rangos para distintos tipos o niveles de carga, pero debe ejecutar UserProfileGenerator. exe una vez por el intervalo que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="3eba0-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="3eba0-127">En **número de usuarios**, haga clic o escriba el número total de usuarios que va a configurar.</span><span class="sxs-lookup"><span data-stu-id="3eba0-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="3eba0-128">En **dominio de usuario**, escriba el dominio que se usará para el URI del SIP.</span><span class="sxs-lookup"><span data-stu-id="3eba0-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="3eba0-129">Se usa para construir el URI de SIP de cada usuario para iniciar sesión en el servidor front-end de Lync Server 2013 o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3eba0-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="3eba0-130">Puede ser diferente del dominio de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="3eba0-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="3eba0-131">En **dominio de cuenta**, escriba el inicio de sesión de dominio de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3eba0-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="3eba0-132">Escriba el número máximo de puntos de conexión simultáneos en el **Inicio de sesión por segundo (por instancia)** para los que desea que la herramienta inicie sesión en todos los extremos o usuarios.</span><span class="sxs-lookup"><span data-stu-id="3eba0-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="3eba0-133">La frecuencia recomendada es \<= 2 por segundo/el SKU estándar fe.</span><span class="sxs-lookup"><span data-stu-id="3eba0-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="3eba0-134">En **proxy de acceso o FQDN del grupo**de servidores, escriba el nombre de dominio completo (FQDN) del servidor al que desea que se conecten los clientes.</span><span class="sxs-lookup"><span data-stu-id="3eba0-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="3eba0-135">Si los usuarios inician sesión externamente, especifique el proxy de acceso.</span><span class="sxs-lookup"><span data-stu-id="3eba0-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="3eba0-136">Si los usuarios son internos, especifique el FQDN de su grupo de servidores o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3eba0-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="3eba0-137">En **Puerto**, haga clic o escriba el puerto que desea que usen los usuarios para SIP (el valor predeterminado es 5061).</span><span class="sxs-lookup"><span data-stu-id="3eba0-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="3eba0-138">Para la configuración del servidor de red externo, especifique el **proxy de acceso o el FQDN del grupo** de servidores y el **Puerto**.</span><span class="sxs-lookup"><span data-stu-id="3eba0-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="3eba0-139">Esta configuración se usa únicamente para la simulación de carga de extremos externos.</span><span class="sxs-lookup"><span data-stu-id="3eba0-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="3eba0-140">Escenarios generales</span><span class="sxs-lookup"><span data-stu-id="3eba0-140">General Scenarios</span></span>

<span data-ttu-id="3eba0-141">La ficha **escenarios generales** de la herramienta de configuración de carga de Lync Server 2013 se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="3eba0-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="3eba0-142">Configure los niveles de carga y los parámetros para cada uno de los escenarios generales que desee ejecutar o deje deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3eba0-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="3eba0-143">![Ficha escenarios generales.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Ficha escenarios generales.")</span><span class="sxs-lookup"><span data-stu-id="3eba0-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="3eba0-144">En la **mensajería instantánea**, que incluye punto a punto y Conferencia, especifique el valor adecuado para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3eba0-145">Los valores de nivel de carga para todos los campos (excepto servicios de información de ubicación) están <STRONG>deshabilitados</STRONG>, <STRONG>bajo</STRONG>, <STRONG>medio</STRONG>, <STRONG>alto</STRONG>y <STRONG>personalizado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3eba0-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="3eba0-146">Cuando se selecciona Low, Medium, High o Custom, se generarán configuraciones para cada modalidad y cliente.</span><span class="sxs-lookup"><span data-stu-id="3eba0-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="3eba0-147">High dará como resultado que la carga máxima admitida se genere para el servidor, Medium corresponde al 60 por ciento de la carga y Low equivale al 30 por ciento de la carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="3eba0-148">En audioconferencia, que solo es **audioconferencia, especifique**el valor adecuado para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="3eba0-149">Las llamadas punto a punto se tratan en la sección escenarios de voz más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="3eba0-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="3eba0-150">Para habilitar la multivista, abra la pestaña **avanzadas** de esa modalidad.</span><span class="sxs-lookup"><span data-stu-id="3eba0-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="3eba0-151">En **uso compartido de aplicaciones**, especifique el valor adecuado para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="3eba0-152">En la **colaboración de datos**, que incluye la Conferencia de datos, especifique el valor adecuado para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="3eba0-153">En **expansión**de la lista de distribución, especifique el valor adecuado para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="3eba0-154">También debe hacer clic en el botón **avanzadas** y, a continuación, rellenar los campos con los mismos valores que ha configurado en la ficha **lista de distribución** de la herramienta de creación de usuarios de Lync Server (UserProvisioningTool. exe).</span><span class="sxs-lookup"><span data-stu-id="3eba0-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="3eba0-155">Para obtener más información sobre estos campos, consulte [crear usuarios y contactos](create-users-and-contacts.md) .</span><span class="sxs-lookup"><span data-stu-id="3eba0-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="3eba0-156">En **consulta Web**de la libreta de direcciones, que es el servicio de búsqueda de la libreta de direcciones (no la descarga del archivo de la libreta de direcciones), especifique el valor adecuado para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="3eba0-157">Para habilitar la descarga de la libreta de direcciones, haga clic en el botón **Opciones avanzadas** correspondiente y, a continuación, establezca **EnableABSDownload** en true.</span><span class="sxs-lookup"><span data-stu-id="3eba0-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="3eba0-158">En **servicio de grupo de respuesta**, especifique el valor adecuado para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="3eba0-159">También debe hacer clic en el botón **Opciones avanzadas** correspondiente y, a continuación, especificar los URI de los grupos de respuesta que ya ha creado al aprovisionar agentes del servicio del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3eba0-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="3eba0-160">Debe especificar al menos un grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3eba0-160">You must specify at least one response group.</span></span> <span data-ttu-id="3eba0-161">Use punto y coma para separar varios grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3eba0-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="3eba0-162">Actualice RGSUriSuffixStartIndex y RGSUriSuffixEndIndex a los valores reales.</span><span class="sxs-lookup"><span data-stu-id="3eba0-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="3eba0-163">En **servicios de información de ubicación**, seleccione el valor adecuado para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="3eba0-164">El nivel de carga para los servicios de información de ubicación debe estar **habilitado** o **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="3eba0-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3eba0-165">Cada uno de los escenarios tiene un botón <STRONG>avanzado</STRONG> situado junto a él y un conjunto de casillas de verificación que habilitan variaciones de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="3eba0-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="3eba0-166"><STRONG>Ad-hoc</STRONG> significa generar una simulación de conferencias que se crearán a lo largo de la hora.</span><span class="sxs-lookup"><span data-stu-id="3eba0-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="3eba0-167"><STRONG>Conf de gran tamaño</STRONG> significa que se simulará un escenario de conferencia de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="3eba0-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="3eba0-168"><STRONG>External</STRONG> significa también simular usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="3eba0-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="3eba0-169">Estos botones y casillas de verificación permiten el acceso a valores específicos de cada escenario que cambiarán el comportamiento de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool) y facilitarán la personalización.</span><span class="sxs-lookup"><span data-stu-id="3eba0-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="3eba0-170">Para cada escenario de la ficha <STRONG>escenarios generales</STRONG> (excepto para servicios de información de ubicación), si el valor de nivel de carga es <STRONG>personalizado</STRONG>, la tasa de conversaciones se calculará usando el campo correspondiente en el cuadro de diálogo <STRONG>Opciones avanzadas</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3eba0-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="3eba0-171">El nombre del campo difiere en función del escenario, pero la descripción del campo será "Nota: este número solo se usará si se selecciona personalizado en el menú desplegable".</span><span class="sxs-lookup"><span data-stu-id="3eba0-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="3eba0-172">En general, los valores <STRONG>alto</STRONG>, <STRONG>medio</STRONG>y <STRONG>bajo</STRONG> modificarán las tasas de conversación por modalidad en línea con el modelo de usuario que es un equilibrio de todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="3eba0-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="3eba0-173">Si es necesario cambiar el nivel de carga por modalidad debido a una diferencia en el uso esperado, se recomienda usar una tasa de conversación <STRONG>personalizada</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3eba0-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="3eba0-174">Escenarios de voz</span><span class="sxs-lookup"><span data-stu-id="3eba0-174">Voice Scenarios</span></span>

<span data-ttu-id="3eba0-175">La ficha **escenarios de voz** de la herramienta de configuración de carga de Lync Server 2013 se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="3eba0-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="3eba0-176">Use la pestaña **escenarios de voz** para configurar todos los escenarios relacionados con la voz.</span><span class="sxs-lookup"><span data-stu-id="3eba0-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="3eba0-177">![Ficha escenarios de voz.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Ficha escenarios de voz.")</span><span class="sxs-lookup"><span data-stu-id="3eba0-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="3eba0-178">En **VoIP**, haga clic en el botón **avanzadas** y, a continuación, proporcione valores para los campos **PhoneAreaCode** y **LocationProfile** (plan de marcado).</span><span class="sxs-lookup"><span data-stu-id="3eba0-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="3eba0-179">También debe especificar un valor para el **nivel de carga**.</span><span class="sxs-lookup"><span data-stu-id="3eba0-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="3eba0-180">Si se habilita el nivel de carga de **VoIP** y la **puerta de enlace RTC/RTC** , siempre se generará un archivo de configuración de red telefónica conmutada (RTC) en el archivo de configuración de comunicaciones unificadas (UC) que simulará las llamadas externas.</span><span class="sxs-lookup"><span data-stu-id="3eba0-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="3eba0-181">En **puerta de enlace de comunicaciones unificadas/RTC**, especifique un valor para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="3eba0-182">Si selecciona un nivel de carga que no sea **deshabilitado**, debe proporcionar un valor para el **código de área RTC** haciendo clic en el botón **Agregar** en servidor de mediación y RTC.</span><span class="sxs-lookup"><span data-stu-id="3eba0-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="3eba0-183">Compruebe que tiene una ruta configurada para ese código de área.</span><span class="sxs-lookup"><span data-stu-id="3eba0-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3eba0-184">Puede usar el panel de control de Lync Server o el shell de administración de Lync Server para comprobar la configuración de la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="3eba0-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="3eba0-185">En el **operador de conferencia**, especifique un valor para el nivel de carga.</span><span class="sxs-lookup"><span data-stu-id="3eba0-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="3eba0-186">Al seleccionar un nivel de carga (distinto de **deshabilitado**), se habilitará el campo **número de teléfono** .</span><span class="sxs-lookup"><span data-stu-id="3eba0-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="3eba0-187">Escriba el número de teléfono del operador automático que desea usar.</span><span class="sxs-lookup"><span data-stu-id="3eba0-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="3eba0-188">Además, haga clic en el botón **avanzadas** y, a continuación, especifique un valor para el campo **LocationProfile** .</span><span class="sxs-lookup"><span data-stu-id="3eba0-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="3eba0-189">En **servicio de estacionamiento de llamadas**, especifique el valor adecuado para el **nivel de carga**.</span><span class="sxs-lookup"><span data-stu-id="3eba0-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="3eba0-190">En el **servidor de mediación y**en la RTC, para cada servidor de mediación que desee usar, debe tener un simulador de RTC independiente.</span><span class="sxs-lookup"><span data-stu-id="3eba0-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="3eba0-191">Una vez que haya determinado el cliente que va a usar como simulador, debe configurar el servidor de mediación para enrutar las llamadas a ese equipo en el puerto del simulador RTC que configuró.</span><span class="sxs-lookup"><span data-stu-id="3eba0-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="3eba0-192">Haga clic en **Agregar** para configurar el valor para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3eba0-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3eba0-193">Cada uno de los escenarios tiene un botón <STRONG>avanzado</STRONG> situado junto a él.</span><span class="sxs-lookup"><span data-stu-id="3eba0-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="3eba0-194">Estos botones permiten el acceso a valores específicos de cada escenario que cambiarán el comportamiento de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool) y habilitación de la personalización.</span><span class="sxs-lookup"><span data-stu-id="3eba0-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="3eba0-195">Para cada escenario de la <STRONG>pestaña escenarios de voz</STRONG> , si el valor de nivel de <STRONG>carga</STRONG> es <STRONG>personalizado</STRONG>, la tasa de conversaciones se calculará usando el campo correspondiente en el cuadro de diálogo <STRONG>Opciones avanzadas</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3eba0-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="3eba0-196">El nombre del campo difiere en función del escenario, pero la descripción del campo será "Nota: este número solo se usará si se selecciona personalizado en el menú desplegable".</span><span class="sxs-lookup"><span data-stu-id="3eba0-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="3eba0-197">Acceder</span><span class="sxs-lookup"><span data-stu-id="3eba0-197">Reach</span></span>

<span data-ttu-id="3eba0-198">REACH es una nueva experiencia en Lync Server 2013 que admite escenarios de conferencia a través del servidor de API Web de comunicaciones unificadas (UCWA) instalado en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="3eba0-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="3eba0-199">En la siguiente figura se muestra la ficha **alcance** de la herramienta de configuración de carga de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3eba0-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="3eba0-200">Use la ficha **alcance** para configurar todos los escenarios relacionados con el alcance.</span><span class="sxs-lookup"><span data-stu-id="3eba0-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="3eba0-201">![Ficha alcance.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Ficha alcance.")</span><span class="sxs-lookup"><span data-stu-id="3eba0-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="3eba0-202">Haga clic en el botón **avanzadas** junto a **Configuración general de alcance**.</span><span class="sxs-lookup"><span data-stu-id="3eba0-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="3eba0-203">Establezca el campo **UcwaTargetServerUrl** en la dirección IP virtual (VIP) del grupo de directores o en la VIP del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="3eba0-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="3eba0-204">En **uso compartido de aplicaciones**, **colaboración de datos**y **mensajería instantánea**, seleccione el valor adecuado para el **nivel de carga**.</span><span class="sxs-lookup"><span data-stu-id="3eba0-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3eba0-205">Cada uno de los escenarios tiene un botón <STRONG>avanzado</STRONG> situado junto a él.</span><span class="sxs-lookup"><span data-stu-id="3eba0-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="3eba0-206">Estos botones permiten el acceso a valores específicos de cada escenario que cambiarán el comportamiento de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool) y habilitación de la personalización.</span><span class="sxs-lookup"><span data-stu-id="3eba0-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="3eba0-207">Para cada uno de los escenarios de Reach, si el <STRONG>nivel de carga</STRONG> es <STRONG>personalizado</STRONG>, se usa el valor especificado en el campo <STRONG>ConversationsPerHour</STRONG> en lugar del predeterminado</span><span class="sxs-lookup"><span data-stu-id="3eba0-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="3eba0-208">Use la ficha **movilidad** para configurar todos los escenarios relacionados con la movilidad.</span><span class="sxs-lookup"><span data-stu-id="3eba0-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="3eba0-209">![Ficha movilidad.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Ficha movilidad.")</span><span class="sxs-lookup"><span data-stu-id="3eba0-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="3eba0-210">Haga clic en el botón **Opciones avanzadas** junto a **movilidad (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="3eba0-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="3eba0-211">Establezca el campo **UcwaTargetServerUrl** en la dirección IP virtual (VIP) del grupo de directores o en la VIP del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="3eba0-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="3eba0-212">En **presencia y audio de mensajería\\instantánea P2P**, seleccione el valor adecuado para el **nivel de carga** para habilitar la simulación de escenario de movilidad.</span><span class="sxs-lookup"><span data-stu-id="3eba0-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3eba0-213">Cada uno de los escenarios tiene un botón <STRONG>avanzado</STRONG> situado junto a él.</span><span class="sxs-lookup"><span data-stu-id="3eba0-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="3eba0-214">Estos botones permiten el acceso a valores específicos de cada escenario que cambiarán el comportamiento de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool) y habilitación de la personalización.</span><span class="sxs-lookup"><span data-stu-id="3eba0-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="3eba0-215">Para cada uno de los escenarios de Reach, si el <STRONG>nivel de carga</STRONG> es <STRONG>personalizado</STRONG>, se usa el valor especificado en el campo <STRONG>ConversationsPerHour</STRONG> en lugar del predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3eba0-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="3eba0-216">Resumen</span><span class="sxs-lookup"><span data-stu-id="3eba0-216">Summary</span></span>

<span data-ttu-id="3eba0-217">La ficha **Resumen** de la herramienta de configuración de carga de Lync Server 2013 se muestra en la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="3eba0-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="3eba0-218">![Ficha Resumen.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Ficha Resumen.")</span><span class="sxs-lookup"><span data-stu-id="3eba0-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="3eba0-219">La pestaña **Resumen** indica qué usuarios deben usar para cada uno de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="3eba0-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="3eba0-220">Es posible configurar manualmente los intervalos de números de usuario activando la casilla de verificación **Habilitar la generación de intervalo de usuario personalizado** y, a continuación, haciendo doble clic en el escenario de la tabla que tiene el **intervalo de usuarios** que desea personalizar.</span><span class="sxs-lookup"><span data-stu-id="3eba0-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="3eba0-221">Compruebe (RunClient. bat) Agregue un retraso de inicio de sesión al iniciar el, a fin de incluir retrasos en los archivos por lotes generados para que correspondan a la tasa de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="3eba0-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="3eba0-222">Esto es útil para evitar la sobrecarga del servidor al iniciar sesión en un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="3eba0-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="3eba0-223">Haga clic en **generar archivos**y seleccione la carpeta en la que desea generar la configuración.</span><span class="sxs-lookup"><span data-stu-id="3eba0-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="3eba0-224">Cuando los archivos se hayan creado correctamente, aparecerá un cuadro de diálogo similar a la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="3eba0-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="3eba0-225">![Confirmación de que se han creado los archivos.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Confirmación de que se han creado los archivos.")</span><span class="sxs-lookup"><span data-stu-id="3eba0-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3eba0-226">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eba0-226">See Also</span></span>


[<span data-ttu-id="3eba0-227">Crear usuarios y contactos</span><span class="sxs-lookup"><span data-stu-id="3eba0-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
