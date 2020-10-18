---
title: Crear usuarios y contactos
description: Crear usuarios y contactos.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e45bb1aa737dd8287be15ae72ece2e35a346af1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573086"
---
# <a name="create-users-and-contacts"></a><span data-ttu-id="2f387-103">Crear usuarios y contactos</span><span class="sxs-lookup"><span data-stu-id="2f387-103">Create Users and Contacts</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f387-104">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2f387-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2f387-105">Debe usar la herramienta de aprovisionamiento de usuarios (UserProvisioningTool.exe) de Lync Server 2013 para crear usuarios y contactos como preparación para la prueba de carga de rendimiento y estrés.</span><span class="sxs-lookup"><span data-stu-id="2f387-105">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="2f387-106">A continuación, se incluye una lista de términos y definiciones que puede resultarle útil a la lectura de este tema.</span><span class="sxs-lookup"><span data-stu-id="2f387-106">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="2f387-107">Unidad organizativa: la unidad organizativa (Uo) de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f387-107">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="2f387-108">Federado/grupo cruzado: usuarios que se habilitarán para comunicarse con usuarios de otros servicios de mensajería instantánea (mi), como MSN Network of Internet Services, AOL® y Yahoo \! ®.</span><span class="sxs-lookup"><span data-stu-id="2f387-108">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="2f387-109">Listas de distribución: objetos de los servicios de dominio de Active Directory que contienen una lista de usuarios de los servicios de dominio de Active Directory, que se usan para iniciar comunicaciones con grupos de personas.</span><span class="sxs-lookup"><span data-stu-id="2f387-109">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="2f387-110">Servicio de información de Ubicación: el servicio Lync Server 2013 que, cuando se habilitan y configuran por teléfono, permite la recuperación de la ubicación física para los servicios mejorados 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="2f387-110">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="2f387-111">Números de teléfono de Estados Unidos: los números de teléfono asignados a los usuarios, además del URI de SIP que se usa para enrutar las llamadas entrantes y salientes, y la búsqueda inversa de números (RNL).</span><span class="sxs-lookup"><span data-stu-id="2f387-111">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="2f387-112">Crear usuarios y contactos con UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="2f387-112">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="2f387-113">Debe usar la herramienta de aprovisionamiento de usuarios de Lync Server para crear usuarios y contactos para la simulación de carga.</span><span class="sxs-lookup"><span data-stu-id="2f387-113">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="2f387-114">La herramienta de aprovisionamiento de usuarios de Lync Server se instala con el paquete de la herramienta de esfuerzo y rendimiento de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f387-114">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="2f387-115">Asegúrese de que el instalador del paquete (CapacityPlanningTool.msi) se haya ejecutado en el servidor front-end o en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2f387-115">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="2f387-116">Inicie la herramienta de aprovisionamiento de usuarios de Lync Server; para ello, ejecute el archivo UserProvisioningTool.exe (que se encuentra en% InstalledDirectory% LyncStressAndPerfTool \\ LyncStress) en el servidor front-end o en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2f387-116">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f387-117">Debe haber iniciado sesión como miembro del grupo de seguridad administradores de dominio para poder ejecutar UserProvisioningTool.exe.</span><span class="sxs-lookup"><span data-stu-id="2f387-117">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="2f387-118">Es necesario ejecutar desde este contexto porque UserProvisioningTool.exe creará y configurará nuevos usuarios de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f387-118">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2f387-119">Cuando se crea un número significativo de usuarios (de 10.000 o más), se ejecuta UserProvisioningTool.exe desde un equipo de gama alta.</span><span class="sxs-lookup"><span data-stu-id="2f387-119">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="2f387-120">Tenga en cuenta que el controlador de dominio también experimentará una carga elevada mientras se crean los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f387-120">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="2f387-121">Cuando se abra la herramienta de aprovisionamiento de usuarios de Lync Server, haga clic en **configuración** y seleccione **cargar configuración**.</span><span class="sxs-lookup"><span data-stu-id="2f387-121">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="2f387-122">Para empezar a configurar usuarios y contactos, cargue el archivo predeterminado que se incluye en el paquete, SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="2f387-122">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="2f387-123">Esto rellenará previamente los campos con datos de ejemplo que necesitará revisar en el sistema.</span><span class="sxs-lookup"><span data-stu-id="2f387-123">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="2f387-124">Si tiene un archivo XML preconfigurado que ya contiene una configuración personalizada, cargue ese archivo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2f387-124">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="2f387-125">Rellene los campos de la herramienta de aprovisionamiento de usuarios de Lync Server, tal y como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="2f387-125">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="2f387-126">![Pestaña creación de usuario.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Pestaña creación de usuario.")</span><span class="sxs-lookup"><span data-stu-id="2f387-126">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="2f387-127">Para configurar las opciones del servidor, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2f387-127">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="2f387-128">En **FQDN del grupo de servidores front-end**, escriba el nombre de dominio completo (FQDN) del servidor Standard Edition o del grupo de servidores front-end en el que desea hospedar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f387-128">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="2f387-129">En **Prefijo de nombre de usuario**, escriba un prefijo que desee usar para crear nombres de usuario con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="2f387-129">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="2f387-130">En **contraseña**, especifique una contraseña que se aplicará a todas las cuentas de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="2f387-130">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="2f387-131">En **dominio SIP**, escriba el nombre de dominio que se usará para los URI del SIP de los usuarios de prueba (identificadores uniformes de recursos).</span><span class="sxs-lookup"><span data-stu-id="2f387-131">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="2f387-132">En **dominio de cuenta**, escriba el nombre de dominio de su dominio de servicios de dominio de Active Directory actual, en el que desea crear los usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="2f387-132">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="2f387-133">En **unidad organizativa**, escriba el nombre de la unidad organizativa de los servicios de dominio de Active Directory donde desea crear los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="2f387-133">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="2f387-134">Si la unidad organizativa no existe, se creará.</span><span class="sxs-lookup"><span data-stu-id="2f387-134">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="2f387-135">En **código de área de teléfono**, escriba el código de área de tres dígitos que se usará para las cuentas de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="2f387-135">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="2f387-136">Asegúrese de que el código de área de teléfono no entre en conflicto con otros códigos de área de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f387-136">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="2f387-137">Active la casilla de verificación **voz habilitada** si desea habilitar a los usuarios de prueba para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="2f387-137">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="2f387-138">En **número de usuarios**, especifique el número total de usuarios de prueba que desea crear.</span><span class="sxs-lookup"><span data-stu-id="2f387-138">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="2f387-139">En **iniciar índice**, especifique el número inicial que se utilizará como sufijo en el prefijo del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="2f387-139">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="2f387-140">Botón crear usuarios</span><span class="sxs-lookup"><span data-stu-id="2f387-140">Create Users Button</span></span>

<span data-ttu-id="2f387-141">Al hacer clic en el botón crear usuarios, se validarán todos los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f387-141">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="2f387-142">Si hay errores de validación, se le pedirá que corrija los valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f387-142">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="2f387-143">Si todos los valores de entrada son correctos, empezará a crear usuarios en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f387-143">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="2f387-144">Aparecerá una barra de progreso en la parte inferior de este formulario.</span><span class="sxs-lookup"><span data-stu-id="2f387-144">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="2f387-145">Le recomendamos que no cierre la aplicación mientras está activa la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="2f387-145">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="2f387-146">La creación de usuarios es un proceso lento.</span><span class="sxs-lookup"><span data-stu-id="2f387-146">User Creation is a slow process.</span></span> <span data-ttu-id="2f387-147">Puede tardar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="2f387-147">It can take several minutes.</span></span> <span data-ttu-id="2f387-148">Si el número de usuarios es muy grande, el proceso podría tardar unas pocas horas.</span><span class="sxs-lookup"><span data-stu-id="2f387-148">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="2f387-149">Si los usuarios ya existen, se actualizan con los cambios.</span><span class="sxs-lookup"><span data-stu-id="2f387-149">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="2f387-150">Puede validar que los usuarios se han creado iniciando sesión como uno de los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2f387-150">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="2f387-151">Use el prefijo de usuario, el número de usuario y @sipDomain como nombre de usuario (por ejemplo, LyncUser10@contoso.net), junto con la contraseña especificada.</span><span class="sxs-lookup"><span data-stu-id="2f387-151">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="2f387-152">Botón eliminar usuarios</span><span class="sxs-lookup"><span data-stu-id="2f387-152">Delete Users Button</span></span>

<span data-ttu-id="2f387-153">Al hacer clic en el botón eliminar usuarios, se validarán todos los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f387-153">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="2f387-154">Si hay errores de validación, se le pedirá que corrija los valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f387-154">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="2f387-155">Si todos los valores de entrada son correctos, empezará a deshabilitar y eliminar usuarios en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f387-155">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="2f387-156">Aparecerá una barra de progreso en la parte inferior de este formulario.</span><span class="sxs-lookup"><span data-stu-id="2f387-156">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="2f387-157">Le recomendamos que no cierre la aplicación mientras está activa la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="2f387-157">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="2f387-158">Solo se admiten números de teléfono con formato estadounidense.</span><span class="sxs-lookup"><span data-stu-id="2f387-158">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="2f387-159">Los números de teléfono se asignan siempre a los usuarios y todos los usuarios creados por UserProvisioningTool.exe están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="2f387-159">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="2f387-160">Los escenarios que usan el número de teléfono, como el operador automático de conferencia o las llamadas de UC-RTC, usan este número de teléfono para enrutar las llamadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f387-160">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="2f387-161">Por este motivo, todos los usuarios deben tener un número de teléfono único.</span><span class="sxs-lookup"><span data-stu-id="2f387-161">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="2f387-162">Si tiene que crear dos veces usuarios, se producirá un error en el comando a menos que use otro código de área o si los usuarios anteriores se han deshabilitado mediante el cmdlet <STRONG>Disable-CsUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="2f387-162">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="2f387-163">Antes de crear contactos, debe completar primero la replicación de usuario, que se realiza desde la pestaña usuarios. Si acaba de crear los usuarios, debe esperar hasta que se complete la replicación de Lync Server y se llenen las cuentas de usuario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f387-163">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="2f387-164">Si los usuarios no han terminado de replicarse, verá un error.</span><span class="sxs-lookup"><span data-stu-id="2f387-164">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="2f387-165">Sabrá Cuándo los usuarios han terminado de replicarse si se ha iniciado el servicio front-end de Lync Server 2013 o si se ha ejecutado correctamente el cmdlet <STRONG>Get-CsUser</STRONG> en el último usuario.</span><span class="sxs-lookup"><span data-stu-id="2f387-165">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="2f387-166">Pestaña creación de contactos</span><span class="sxs-lookup"><span data-stu-id="2f387-166">Contacts Creation Tab</span></span>

<span data-ttu-id="2f387-167">La ficha creación de contactos le permite especificar los detalles de los contactos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f387-167">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="2f387-168">![Pestaña creación de contactos.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Pestaña creación de contactos.")</span><span class="sxs-lookup"><span data-stu-id="2f387-168">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="2f387-169">Para configurar los contactos de los usuarios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2f387-169">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="2f387-170">En promedio de contactos por usuario, especifique el número medio de contactos que se van a rellenar en las listas de contactos de cada uno de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f387-170">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="2f387-171">Active la casilla de verificación fijo Si desea crear un número igual de contactos para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="2f387-171">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="2f387-172">Si desea variar el número de contactos creados para los usuarios, desactive la casilla.</span><span class="sxs-lookup"><span data-stu-id="2f387-172">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="2f387-173">En grupos de contactos promedio por usuario, especifique el número de grupos de contactos por usuario.</span><span class="sxs-lookup"><span data-stu-id="2f387-173">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="2f387-174">Este número debe ser menor que el promedio de contactos por usuario.</span><span class="sxs-lookup"><span data-stu-id="2f387-174">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="2f387-175">En porcentaje de contactos de Federated/Cross pools, especifique un número entre 0 y 100.</span><span class="sxs-lookup"><span data-stu-id="2f387-175">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="2f387-176">Este porcentaje de contactos se creará con los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="2f387-176">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="2f387-177">En el prefijo de usuario de federado/grupo cruzado, especifique el nombre de usuario para los usuarios federados que se agregarán a las listas de contactos de los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="2f387-177">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="2f387-178">En dominio SIP de usuario federado/grupo cruzado, especifique el nombre de dominio SIP de los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="2f387-178">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f387-179">Ninguno de los usuarios debe iniciar sesión al crear contactos.</span><span class="sxs-lookup"><span data-stu-id="2f387-179">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="2f387-180">En la ficha creación de usuario, compruebe que los parámetros son correctos.</span><span class="sxs-lookup"><span data-stu-id="2f387-180">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="2f387-181">El rango de usuarios para los que se crearán los contactos se obtiene de la pestaña creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f387-181">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="2f387-182">Haga clic en crear contactos para iniciar la creación de contactos.</span><span class="sxs-lookup"><span data-stu-id="2f387-182">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="2f387-183">Este proceso puede tardar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="2f387-183">This process can take several minutes.</span></span> <span data-ttu-id="2f387-184">Una vez finalizado, aparecerá un cuadro de diálogo con el mensaje "la operación se completó correctamente".</span><span class="sxs-lookup"><span data-stu-id="2f387-184">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="2f387-185">Puede validar los contactos que se crearon iniciando sesión como un usuario que se creó desde la pestaña creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f387-185">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f387-186">Una vez creados los contactos, esta herramienta reiniciará todos los servidores front-end del grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="2f387-186">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="2f387-187">Los servidores front-end pueden tardar más tiempo (hasta 2 horas) en iniciarse, en función de cuántos contactos haya creado esta operación.</span><span class="sxs-lookup"><span data-stu-id="2f387-187">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="2f387-188">Lista de distribución</span><span class="sxs-lookup"><span data-stu-id="2f387-188">Distribution List</span></span>

<span data-ttu-id="2f387-189">Una de las características de la herramienta stress and performance de Lync Server 2013 es simular la característica de expansión de la lista de distribución (DL) en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2f387-189">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="2f387-190">Si no va a habilitar la expansión de DL en UserProvisioningTool, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="2f387-190">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="2f387-191">![Ficha creación de lista de distribución.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Ficha creación de lista de distribución.")</span><span class="sxs-lookup"><span data-stu-id="2f387-191">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="2f387-192">La ficha Lista de distribución le permite crear listas de distribución que la herramienta stress and Performance usará para la característica de expansión de listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="2f387-192">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="2f387-193">Antes de crear las listas de distribución, es necesario que Lync Server 2013 ya esté instalado.</span><span class="sxs-lookup"><span data-stu-id="2f387-193">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="2f387-194">Debe haber ejecutado Lync Server 2013 ForestPrep.</span><span class="sxs-lookup"><span data-stu-id="2f387-194">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="2f387-195">De lo contrario, los atributos DL no existen en el esquema de servicios de dominio de Active Directory y la herramienta no podrá crear listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="2f387-195">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="2f387-196">Para configurar listas de distribución, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2f387-196">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="2f387-197">En número de listas de distribución, especifique el número total de DL que desea crear.</span><span class="sxs-lookup"><span data-stu-id="2f387-197">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="2f387-198">(Le recomendamos que empiece con el doble del número de usuarios).</span><span class="sxs-lookup"><span data-stu-id="2f387-198">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="2f387-199">Se numeran de 0 a n-1.</span><span class="sxs-lookup"><span data-stu-id="2f387-199">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="2f387-200">En Prefijo de lista de distribución, especifique el prefijo que tendrá la DL.</span><span class="sxs-lookup"><span data-stu-id="2f387-200">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="2f387-201">Por ejemplo, si especifica 100 DLs y un prefijo de testDL, las listas de distribución recibirán el nombre testDL0, testDL1, etc., a través de testDL99.</span><span class="sxs-lookup"><span data-stu-id="2f387-201">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="2f387-202">En miembros mínimos de una lista Dist., especifique el número mínimo de usuarios que se agregarán en cada lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="2f387-202">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="2f387-203">En número máximo de miembros de una lista de distribución, especifique el número máximo de usuarios que se agregarán en cada lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="2f387-203">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="2f387-204">Botón crear listas de distribución</span><span class="sxs-lookup"><span data-stu-id="2f387-204">Create Distribution Lists Button</span></span>

<span data-ttu-id="2f387-205">Al hacer clic en el botón crear listas de distribución, la herramienta consulta servicios de dominio de Active Directory para ver si las listas de distribución que coinciden con el prefijo y los números ya existen.</span><span class="sxs-lookup"><span data-stu-id="2f387-205">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="2f387-206">La herramienta solo creará las que aún no existen.</span><span class="sxs-lookup"><span data-stu-id="2f387-206">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="2f387-207">Cuando se agregan miembros a estas listas de distribución recién creadas, se seleccionan los usuarios del rango especificado en la pestaña creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f387-207">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="2f387-208">Ficha Configuración del servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="2f387-208">Location Info Service Config Tab</span></span>

<span data-ttu-id="2f387-209">Una de las características de la herramienta de esfuerzo y rendimiento de Lync Server 2013 es generar archivos de configuración ficticio para el servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="2f387-209">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="2f387-210">El servicio de información de ubicación no suele tener un impacto significativo en el rendimiento de los servidores.</span><span class="sxs-lookup"><span data-stu-id="2f387-210">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="2f387-211">![Ficha Configuración del servicio de información de ubicación.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Ficha Configuración del servicio de información de ubicación.")</span><span class="sxs-lookup"><span data-stu-id="2f387-211">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="2f387-212">Si elige probar esta característica, puede rellenar los valores mencionados en el formulario y, a continuación, hacer clic en el botón generar archivos de configuración de LIS.</span><span class="sxs-lookup"><span data-stu-id="2f387-212">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="2f387-213">Se generarán archivos CSV denominados LIS \_Subnet.csv, lis \_Switches.csv, LIS \_Ports.csv y Lis \_WAP.csv.</span><span class="sxs-lookup"><span data-stu-id="2f387-213">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="2f387-214">A continuación, puede importar estos archivos CSV a la base de datos de LIS mediante el cmdlet **set-CsLisSubnet** , el cmdlet **set-CsLisSwitch** , el cmdlet **set-CsLisPort** y el cmdlet **set-CsWirelessAccessPoint** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2f387-214">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

