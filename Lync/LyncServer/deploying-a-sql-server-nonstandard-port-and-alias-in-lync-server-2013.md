---
title: Implementación de un puerto y alias no estándar de SQL Server en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1134422c8c55a60858a9fd8c28be2e6ff159d48
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="6fbf0-102">Implementación de un puerto y alias no estándar de SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fbf0-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fbf0-103">_**Última modificación del tema:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="6fbf0-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="6fbf0-104">Microsoft Lync Server 2013 admite el uso de un puerto y un alias no estándar en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="6fbf0-105">El uso de un puerto no estándar de SQL Server y un alias aumenta la seguridad y crea un entorno más flexible para la implementación de Lync.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="6fbf0-106">Estos pasos son un solo paso para proteger correctamente el entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="6fbf0-107">Se deben realizar pasos adicionales para reducir la superficie de ataque de una implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="6fbf0-108">En el siguiente artículo se describen los pasos necesarios para configurar un puerto y un alias no estándar de SQL Server en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="6fbf0-109">Implementación de un puerto y alias no estándar de SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fbf0-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="6fbf0-110">El generador de topologías de Lync Server 2013 admite el uso de un alias de SQL Server como nombre de dominio completo (FQDN) en lugar del FQDN real de SQL Server al configurar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="6fbf0-111">Esto permite que el FQDN real de SQL Server esté oculto para los intrusos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="6fbf0-112">Además, el uso de un puerto no estándar oculta el puerto real de cualquier atacante que intentara atacar la base de datos en el puerto estándar 1433, tal como se muestra en la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="6fbf0-113">![Un pirata informático no conoce el número de puerto que se va a atacar.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un pirata informático no conoce el número de puerto que se va a atacar.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="6fbf0-114">Para poder determinar correctamente el puerto que Lync Server 2013 usa para comunicarse con SQL Server, el atacante debe analizar todos los puertos para obtener la información del puerto.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="6fbf0-115">Un examen de puertos por parte de un atacante aumenta las probabilidades de que la seguridad pueda detectar y detener la instrucción.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="6fbf0-116">Además de agregar mayor seguridad con un puerto no estándar, también puede usar un alias de SQL Server para proporcionar flexibilidad a la implementación.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="6fbf0-117">Esto es útil para reducir los cambios en la configuración en situaciones en las que se requiere un cambio de nombre de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fbf0-118">SQL Server proporciona dos métodos de tolerancia a errores (clústeres de conmutación por error y reflejos).</span><span class="sxs-lookup"><span data-stu-id="6fbf0-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="6fbf0-119">Ambos métodos de tolerancia a errores de SQL Server se admiten con un puerto no estándar de SQL Server y un alias con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="6fbf0-120">Si el back-end de SQL Server usado por el grupo está en una configuración reflejada, el servicio de explorador SQL de los servidores back-end de SQL Server debe ejecutarse para que los servidores front-end se conecten a la base de datos reflejada cuando las bases de datos se conmutan por error a la copia de SQL reflejada. Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="6fbf0-121">Al configurar la conectividad de base de datos de SQL Server desde el generador de topologías o al usar el cmdlet install-CsDatabase, no es posible definir explícitamente un número de puerto no estándar de SQL Server y asociarlo con una instancia de SQL.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="6fbf0-122">Para establecer un puerto no estándar, deberá usar las utilidades de SQL Server y Windows Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="6fbf0-123">Para configurar un puerto y un alias no estándar de SQL Server para su uso con Lync Server 2013, tendrá que completar tres pasos principales.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="6fbf0-124">Los pasos son:</span><span class="sxs-lookup"><span data-stu-id="6fbf0-124">These steps are:</span></span>

  - <span data-ttu-id="6fbf0-125">Confirme que Lync Server 2013 tiene las actualizaciones más recientes aplicadas.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="6fbf0-126">Configure el puerto y el alias no estándar de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="6fbf0-127">Configure Lync Server 2013 con el alias de SQL Server mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="6fbf0-128">Publique la topología y Compruebe la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="6fbf0-129">Confirmar que Lync Server 2013 tiene las actualizaciones más recientes aplicadas</span><span class="sxs-lookup"><span data-stu-id="6fbf0-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="6fbf0-130">Es importante mantener Lync Server 2013 al día.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="6fbf0-131">Para consultar las actualizaciones más recientes e información sobre cómo aplicarlas, consulte [actualizaciones para Lync Server 2013](https://support.microsoft.com/kb/2809243).</span><span class="sxs-lookup"><span data-stu-id="6fbf0-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="6fbf0-132">Configurar el puerto y el alias no estándar de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6fbf0-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="6fbf0-133">El alias y el puerto no estándar de SQL Server se deben configurar en la instancia de la base de datos para que se pueda hacer referencia a él desde el generador de topologías de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="6fbf0-134">Para configurar un puerto y un alias no estándar de SQL Server, tendrá que completar tres pasos principales.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="6fbf0-135">Estos pasos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6fbf0-135">These steps are as follows:</span></span>

  - <span data-ttu-id="6fbf0-136">Cambie los valores predeterminados del protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="6fbf0-137">Cree y configure un alias de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="6fbf0-138">Cree un registro de recursos de nombre canónico (CNAME) del sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="6fbf0-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="6fbf0-139">**Modificación de los valores predeterminados del protocolo TCP/IP**</span><span class="sxs-lookup"><span data-stu-id="6fbf0-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="6fbf0-140">Seleccione **Inicio**y elija **Administrador de configuración de SQL Server**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-141">![El icono de SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "El icono de SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="6fbf0-142">En el panel de navegación, expanda la **instancia de SQL Server**, expanda la opción **configuración de red de SQL Server**y elija **protocolos\>para nombre \<de instancia**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-143">![Ir a propiedades de TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Ir a propiedades de TCP/IP")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="6fbf0-144">En el panel derecho, haga clic con el botón secundario en **TCP/IP**y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="6fbf0-145">Se muestra el cuadro de diálogo Propiedades de TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="6fbf0-146">Seleccione la pestaña **direcciones IP** . La pestaña direcciones IP muestra todas las direcciones IP activas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="6fbf0-147">Se encuentran en el formato IP1, IP2, hasta IPAll, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-148">![Abra propiedades de TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Abra propiedades de TCP/IP.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="6fbf0-149">Borre el campo **puertos dinámicos TCP** para todas las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="6fbf0-150">Si el campo contiene un carácter cero, significa que SQL Server está escuchando en puertos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="6fbf0-151">Asegúrese de que estos campos se hayan borrado y no contengan un cero.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="6fbf0-152">Para la dirección IP que Lync Server usará para conectarse a la base de datos, asegúrese de que **Enabled** está establecido en **yes**, tal como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-153">![Establezca Enabled como sí para la dirección IP correcta.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Establezca Enabled como sí para la dirección IP correcta.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="6fbf0-154">En la sección **IPAll** de la parte inferior del cuadro de diálogo, escriba el puerto deseado en el campo **puerto TCP** , tal como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="6fbf0-155">En este ejemplo, usamos el puerto 50062, pero puede usar cualquier puerto entre 49152 y 65535.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="6fbf0-156">Estos son los puertos asignados al uso dinámico y privado, y esto garantiza que no entren en conflicto con otros puertos que se usan en la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="6fbf0-157">![Establecer puerto en la sección IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Establecer puerto en la sección IPAll.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="6fbf0-158">Haga clic en **Aceptar** para salir del cuadro de diálogo Propiedades de TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="6fbf0-159">Reinicie la instancia de SQL Server seleccionando **servicios de SQL Server** en el panel izquierdo del administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="6fbf0-160">A continuación, haga clic con el botón secundario en **nombre \<\> de instancia de SQL Server** en el panel derecho y seleccione **reiniciar**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-161">![Restablezca el servicio de SQL Server para la instancia.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Restablezca el servicio de SQL Server para la instancia.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6fbf0-162">Asegúrese de actualizar la configuración del firewall para acomodar el nuevo puerto de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="6fbf0-163">**Crear y configurar un alias de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="6fbf0-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="6fbf0-164">Seleccione **Inicio**y elija **Administrador de configuración de SQL Server**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-165">![El icono de SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "El icono de SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="6fbf0-166">En el panel izquierdo, elija expandir la **instancia de SQL Server**, expanda la configuración de la \*\* \<versión\> de SQL Native Client\*\*y, a continuación, elija **alias**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-167">![Alias en el administrador de configuración de SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias en el administrador de configuración de SQL Server.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="6fbf0-168">Haga clic con el botón secundario en **alias**y seleccione **nuevo alias...**.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="6fbf0-169">Escriba el **nombre del alias**, el **número de Puerto**, el **Protocolo**y el **servidor**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-170">![Crear un nuevo alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Crear un nuevo alias")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="6fbf0-171">Asegúrese de escribir el mismo puerto no estándar que usó en el paso anterior, ya que es el puerto en el que se escuchará SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="6fbf0-172">Si un alias configurado se conecta al FQDN o instancia de SQL Server incorrecto, deshabilite y vuelva a habilitar el protocolo de red asociado.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="6fbf0-173">Esto borra la información de conexión almacenada en la memoria caché y permite que el cliente se conecte correctamente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="6fbf0-174">**Crear un registro de recursos CNAME de DNS**</span><span class="sxs-lookup"><span data-stu-id="6fbf0-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="6fbf0-175">Inicie sesión en el equipo que administra DNS.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="6fbf0-176">Seleccione **Inicio**y elija **Administrador del servidor**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-177">![Apertura del administrador del servidor](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Apertura del administrador del servidor")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="6fbf0-178">Seleccione la lista desplegable **herramientas** y, a continuación, seleccione **DNS**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-179">![Abrir DNS desde el administrador del servidor.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Abrir DNS desde el administrador del servidor.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="6fbf0-180">En el panel izquierdo, expanda el nodo nombre del servidor, expanda el nodo zonas de búsqueda directa y elija el dominio relevante.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="6fbf0-181">Haga clic con el botón secundario en el dominio y seleccione **nuevo alias (CNAME)...**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-182">![Selección de la opción para crear un nuevo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selección de la opción para crear un nuevo alias CNAME")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="6fbf0-183">Escriba el **nombre del alias** y el **FQDN de SQL Server**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-184">![Rellenar el cuadro de diálogo CNAME de alias nuevo.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Rellenar el cuadro de diálogo CNAME de alias nuevo.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="6fbf0-185">Elija **Aceptar** para guardar el CNAME y verlo en el administrador de DNS.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="6fbf0-186">Validar la conectividad de base de datos</span><span class="sxs-lookup"><span data-stu-id="6fbf0-186">Validate Database Connectivity</span></span>

<span data-ttu-id="6fbf0-187">Hay muchas formas diferentes de asegurarse de que funciona.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="6fbf0-188">Desea asegurarse de que la base de datos de SQL Server está escuchando en el puerto especificado mediante el alias.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="6fbf0-189">Una comprobación rápida se puede completar con los comandos **netstat** y **telnet** .</span><span class="sxs-lookup"><span data-stu-id="6fbf0-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fbf0-190">El cliente Telnet es una característica que se incluye con Windows Server, pero que debe instalarse.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="6fbf0-191">Para instalar una característica de Windows Server, abra el administrador del servidor y seleccione Agregar roles y características en el menú administrar.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="6fbf0-192">**Uso de netstat y Telnet para comprobar la conectividad de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="6fbf0-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="6fbf0-193">Seleccione **Inicio**y escriba **cmd** para abrir un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="6fbf0-194">Escriba **netstat-a-f**y confirme que SQL Server se está ejecutando con el puerto correcto, tal como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6fbf0-195">![Uso de netstat para comprobar el puerto.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Uso de netstat para comprobar el puerto.")</span><span class="sxs-lookup"><span data-stu-id="6fbf0-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="6fbf0-196">Escriba **Puerto \< \# de nombre\> \<de alias de Telnet** para confirmar la conexión a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="6fbf0-197">Si la conexión se realiza correctamente, Telnet se conectará y no aparecerá un error.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="6fbf0-198">Esto muestra que la instancia de SQL Server está escuchando en el puerto correcto con el alias correcto.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="6fbf0-199">Si hay un problema de conexión a la base de datos de SQL Server, Telnet muestra un error que indica que no se puede establecer la conexión.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="6fbf0-200">Ahora que ya ha comprobado la conectividad de base de datos en el servidor de bases de datos, puede hacer lo mismo con Lync Server (a través de la red) y asegurarse de que no haya ningún firewall que bloquee el acceso a lo largo del proceso.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="6fbf0-201">Conclusión</span><span class="sxs-lookup"><span data-stu-id="6fbf0-201">Conclusion</span></span>

<span data-ttu-id="6fbf0-202">Una vez que se haya configurado el alias de SQL Server, puede usarlo para crear una topología de Lync Server 2013 en la herramienta Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="6fbf0-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="6fbf0-203">Para obtener más información acerca de las topologías, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="6fbf0-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fbf0-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fbf0-204">See Also</span></span>


<span data-ttu-id="6fbf0-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[planeación de la seguridad en Lync Server 2013](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="6fbf0-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="6fbf0-206">Definición y configuración de la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fbf0-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="6fbf0-207">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fbf0-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

