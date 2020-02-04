---
title: Crear usuarios y contactos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1463a7caaad2bcf36996eaac4bd47e2bab25e6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="abb82-102">Crear usuarios y contactos</span><span class="sxs-lookup"><span data-stu-id="abb82-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abb82-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="abb82-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="abb82-104">Debe usar la herramienta de aprovisionamiento de usuarios de Lync Server 2013 (UserProvisioningTool. exe) para crear usuarios y contactos como preparación para pruebas de carga de rendimiento y estrés.</span><span class="sxs-lookup"><span data-stu-id="abb82-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="abb82-105">Esta es una lista de términos y definiciones que puede que le resulte útil a la lectura de este tema.</span><span class="sxs-lookup"><span data-stu-id="abb82-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="abb82-106">Unidad organizativa: la unidad organizativa de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abb82-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="abb82-107">Federado/grupo cruzado: usuarios que se habilitarán para comunicarse con los usuarios de otros servicios de mensajería instantánea (mi), como la red MSN de servicios de Internet, AOL®\!y Yahoo®.</span><span class="sxs-lookup"><span data-stu-id="abb82-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="abb82-108">Listas de distribución: los objetos de los servicios de dominio de Active Directory que contienen una lista de usuarios de los servicios de dominio de Active Directory, que se usan para iniciar las comunicaciones con grupos de personas.</span><span class="sxs-lookup"><span data-stu-id="abb82-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="abb82-109">Servicio de información de Ubicación: servicio de Lync Server 2013 que, cuando se habilitan y configuran por teléfono, permite la recuperación de la ubicación física de los servicios de 9-1-1 (E9-1-1) mejorados.</span><span class="sxs-lookup"><span data-stu-id="abb82-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="abb82-110">Números de teléfono de Estados Unidos: números de teléfono que se asignan a los usuarios, además del URI de SIP que se usa para el enrutamiento de llamadas entrantes y salientes, y búsqueda inversa de números (RNL).</span><span class="sxs-lookup"><span data-stu-id="abb82-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="abb82-111">Crear usuarios y contactos con UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="abb82-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="abb82-112">Debe usar la herramienta de aprovisionamiento de usuarios de Lync Server para crear usuarios y contactos para simulación de carga.</span><span class="sxs-lookup"><span data-stu-id="abb82-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="abb82-113">La herramienta de aprovisionamiento de usuarios de Lync Server se instala con el paquete de herramientas de estrés y rendimiento de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="abb82-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="abb82-114">Asegúrese de que el instalador del paquete (CapacityPlanningTool. msi) se ha ejecutado en el servidor front-end o en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="abb82-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="abb82-115">Inicie la herramienta de aprovisionamiento de usuarios de Lync Server ejecutando el archivo UserProvisioningTool. exe (que se encuentra en% InstalledDirectory\\% LyncStressAndPerfTool LyncStress) en el servidor front-end o en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="abb82-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="abb82-116">Para ejecutar UserProvisioningTool. exe, debe haber iniciado sesión como miembro del grupo de seguridad administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="abb82-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="abb82-117">Es necesario ejecutarlo desde este contexto porque UserProvisioningTool. exe creará y configurará nuevos usuarios de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abb82-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="abb82-118">Cuando cree un número significativo de usuarios (10.000 o más), ejecute UserProvisioningTool. exe desde un equipo de gama alta.</span><span class="sxs-lookup"><span data-stu-id="abb82-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="abb82-119">Tenga en cuenta que el controlador de dominio también experimentará una carga elevada mientras se crean los usuarios.</span><span class="sxs-lookup"><span data-stu-id="abb82-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="abb82-120">Cuando se abra la herramienta de aprovisionamiento de usuarios de Lync Server, haga clic en **configuración** y seleccione **cargar configuración**.</span><span class="sxs-lookup"><span data-stu-id="abb82-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="abb82-121">Para empezar a configurar usuarios y contactos, cargue el archivo predeterminado que se incluye en el paquete, SampleData. Xml.</span><span class="sxs-lookup"><span data-stu-id="abb82-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="abb82-122">Esto rellenará previamente los campos con datos de ejemplo que necesitará revisar para su sistema.</span><span class="sxs-lookup"><span data-stu-id="abb82-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="abb82-123">Si tiene un archivo XML preconfigurado que ya contiene una configuración personalizada, cargue ese archivo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="abb82-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="abb82-124">Rellene los campos de la herramienta de aprovisionamiento de usuarios de Lync Server, tal y como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="abb82-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="abb82-125">![Pestaña de creación de usuarios.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Pestaña de creación de usuarios.")</span><span class="sxs-lookup"><span data-stu-id="abb82-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="abb82-126">Para configurar las opciones del servidor, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abb82-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="abb82-127">En **FQDN del grupo de servidores front end**, escriba el nombre de dominio completo (FQDN) del servidor Standard Edition o del grupo de servidores front-end en el que desea hospedar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="abb82-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="abb82-128">En **Prefijo de nombre de usuario**, escriba un prefijo que desee usar para crear nombres de usuario con el fin de realizar pruebas.</span><span class="sxs-lookup"><span data-stu-id="abb82-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="abb82-129">En **contraseña**, especifique una contraseña que se aplicará a todas las cuentas de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="abb82-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="abb82-130">En **dominio SIP**, escriba el nombre de dominio que se usará para los URI del SIP de los usuarios de prueba (identificadores uniformes de recursos).</span><span class="sxs-lookup"><span data-stu-id="abb82-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="abb82-131">En **dominio**de la cuenta, escriba el nombre de dominio de su dominio de servicios de dominio de Active Directory actual, en el que desea crear los usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="abb82-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="abb82-132">En **unidad organizativa**, escriba el nombre de la UO de los servicios de dominio de Active Directory donde desea crear los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="abb82-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="abb82-133">Si la OU no existe, se creará.</span><span class="sxs-lookup"><span data-stu-id="abb82-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="abb82-134">En **código de área**, escriba el código de área de tres dígitos que se usará para las cuentas de usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="abb82-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="abb82-135">Asegúrese de que el código de área de teléfono no entra en conflicto con los códigos de área de otros usuarios de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abb82-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="abb82-136">Active la casilla de verificación **voz habilitada** si desea habilitar los usuarios de prueba para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="abb82-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="abb82-137">En **número de usuarios**, especifique el número total de usuarios de prueba que desea crear.</span><span class="sxs-lookup"><span data-stu-id="abb82-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="abb82-138">En **Índice de inicio**, especifique el número inicial que se usará como sufijo para el prefijo del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="abb82-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="abb82-139">Botón crear usuarios</span><span class="sxs-lookup"><span data-stu-id="abb82-139">Create Users Button</span></span>

<span data-ttu-id="abb82-140">Al hacer clic en el botón crear usuarios, se validan todos los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="abb82-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="abb82-141">Si hay algún error de validación, se le pedirá que corrija esos valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="abb82-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="abb82-142">Si todos los valores de entrada son correctos, comenzará a crear usuarios en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abb82-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="abb82-143">Aparecerá una barra de progreso en la parte inferior de este formulario.</span><span class="sxs-lookup"><span data-stu-id="abb82-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="abb82-144">Le recomendamos que no cierre la aplicación mientras la barra de progreso esté activa.</span><span class="sxs-lookup"><span data-stu-id="abb82-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="abb82-145">La creación de usuarios es un proceso lento.</span><span class="sxs-lookup"><span data-stu-id="abb82-145">User Creation is a slow process.</span></span> <span data-ttu-id="abb82-146">Puede demorar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="abb82-146">It can take several minutes.</span></span> <span data-ttu-id="abb82-147">Si el número de usuarios es muy grande, el proceso puede demorar incluso unas pocas horas.</span><span class="sxs-lookup"><span data-stu-id="abb82-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="abb82-148">Si los usuarios ya existen, se actualizan con los cambios.</span><span class="sxs-lookup"><span data-stu-id="abb82-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="abb82-149">Puede validar que los usuarios se hayan creado iniciando sesión como uno de los usuarios del rango.</span><span class="sxs-lookup"><span data-stu-id="abb82-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="abb82-150">Use el prefijo de usuario, el número de usuario y @sipDomain como nombre de usuario (por ejemplo, LyncUser10@contoso.net), junto con la contraseña especificada.</span><span class="sxs-lookup"><span data-stu-id="abb82-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="abb82-151">Botón eliminar usuarios</span><span class="sxs-lookup"><span data-stu-id="abb82-151">Delete Users Button</span></span>

<span data-ttu-id="abb82-152">Al hacer clic en el botón eliminar usuarios, se validan todos los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="abb82-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="abb82-153">Si hay algún error de validación, se le pedirá que corrija esos valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="abb82-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="abb82-154">Si todos los valores de entrada son correctos, empezará a deshabilitar y eliminar usuarios en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abb82-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="abb82-155">Aparecerá una barra de progreso en la parte inferior de este formulario.</span><span class="sxs-lookup"><span data-stu-id="abb82-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="abb82-156">Le recomendamos que no cierre la aplicación mientras la barra de progreso esté activa.</span><span class="sxs-lookup"><span data-stu-id="abb82-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="abb82-157">Solo se admiten números de teléfono con formato estadounidense.</span><span class="sxs-lookup"><span data-stu-id="abb82-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="abb82-158">Los números de teléfono siempre se asignan a los usuarios y todos los usuarios creados por UserProvisioningTool. exe están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="abb82-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="abb82-159">Cualquier escenario que use el número de teléfono, como el operador automático de la Conferencia o las llamadas UC-RTC, use este número de teléfono para enrutar las llamadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="abb82-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="abb82-160">Por esta razón, todos los usuarios deben tener un número de teléfono único.</span><span class="sxs-lookup"><span data-stu-id="abb82-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="abb82-161">Si tiene que crear dos veces usuarios, el comando fallará a menos que use un código de área diferente o si los usuarios anteriores se han deshabilitado mediante el cmdlet <STRONG>Disable-CsUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="abb82-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="abb82-162">Antes de crear contactos, primero debe completar la replicación de usuario, desde la ficha usuarios. Si acaba de crear los usuarios, debe esperar hasta que se complete la replicación de Lync Server y se llenen las cuentas de usuario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="abb82-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="abb82-163">Si los usuarios no han terminado de replicarse, verá un error.</span><span class="sxs-lookup"><span data-stu-id="abb82-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="abb82-164">Sabrá Cuándo los usuarios han terminado de replicar si el servicio de front-end de Lync Server 2013 se ha iniciado o si ejecuta correctamente el cmdlet <STRONG>Get-CsUser</STRONG> en el último usuario.</span><span class="sxs-lookup"><span data-stu-id="abb82-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="abb82-165">Ficha creación de contactos</span><span class="sxs-lookup"><span data-stu-id="abb82-165">Contacts Creation Tab</span></span>

<span data-ttu-id="abb82-166">La ficha creación de contactos le permite especificar los detalles de los contactos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="abb82-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="abb82-167">![Pestaña de creación de contactos.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Pestaña de creación de contactos.")</span><span class="sxs-lookup"><span data-stu-id="abb82-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="abb82-168">Para configurar los contactos de los usuarios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abb82-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="abb82-169">En promedio de contactos por usuario, especifique la cantidad promedio de contactos que se van a rellenar en las listas de contactos de cada uno de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="abb82-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="abb82-170">Seleccione la casilla fijo Si desea crear un número igual de contactos para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="abb82-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="abb82-171">Si desea variar el número de contactos creados para los usuarios, desactive la casilla.</span><span class="sxs-lookup"><span data-stu-id="abb82-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="abb82-172">En promedio de grupos de contactos por usuario, especifique el número de grupos de contactos por usuario.</span><span class="sxs-lookup"><span data-stu-id="abb82-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="abb82-173">Este número debe ser menor que el promedio de contactos por usuario.</span><span class="sxs-lookup"><span data-stu-id="abb82-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="abb82-174">En el porcentaje de contactos federado/grupo cruzado, especifique un número entre 0 y 100.</span><span class="sxs-lookup"><span data-stu-id="abb82-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="abb82-175">Este porcentaje de contactos se creará con los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="abb82-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="abb82-176">En el prefijo de usuario federado/grupo cruzado, especifique el nombre de usuario de los usuarios federados que se agregará a las listas de contactos de los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="abb82-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="abb82-177">En dominio SIP de usuario federado/grupo cruzado, especifique el nombre de dominio SIP de los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="abb82-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="abb82-178">Ninguno de los usuarios debe haber iniciado sesión al crear contactos.</span><span class="sxs-lookup"><span data-stu-id="abb82-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="abb82-179">En la ficha creación de usuario, compruebe que los parámetros son correctos.</span><span class="sxs-lookup"><span data-stu-id="abb82-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="abb82-180">El intervalo de usuarios para los que se crearán los contactos se obtiene de la pestaña creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="abb82-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="abb82-181">Haga clic en crear contactos para comenzar la creación de contactos.</span><span class="sxs-lookup"><span data-stu-id="abb82-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="abb82-182">Este proceso puede demorar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="abb82-182">This process can take several minutes.</span></span> <span data-ttu-id="abb82-183">Una vez completada, aparecerá un cuadro de diálogo con el mensaje "la operación se completó correctamente".</span><span class="sxs-lookup"><span data-stu-id="abb82-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="abb82-184">Puede validar los contactos que se crearon iniciando sesión como un usuario creado desde la pestaña creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="abb82-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="abb82-185">Una vez que se crean los contactos, esta herramienta reiniciará todos los servidores front-end en el grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="abb82-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="abb82-186">Es posible que se tarde más (hasta 2 horas) en iniciarse los servidores front-end, dependiendo de cuántos contactos haya creado esta operación.</span><span class="sxs-lookup"><span data-stu-id="abb82-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="abb82-187">Lista de distribución</span><span class="sxs-lookup"><span data-stu-id="abb82-187">Distribution List</span></span>

<span data-ttu-id="abb82-188">Una de las características de la herramienta de rendimiento y estrés de Lync Server 2013 es simular la característica de expansión de la lista de distribución (DL) en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="abb82-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="abb82-189">Si no va a habilitar la expansión de DL en UserProvisioningTool, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="abb82-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="abb82-190">![Pestaña de creación de listas de distribución.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Pestaña de creación de listas de distribución.")</span><span class="sxs-lookup"><span data-stu-id="abb82-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="abb82-191">La pestaña lista de distribución le permite crear listas de distribución que la herramienta esfuerzo y rendimiento usará para la característica de expansión de la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="abb82-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="abb82-192">Antes de crear las listas de distribución, Lync Server 2013 debe estar instalado.</span><span class="sxs-lookup"><span data-stu-id="abb82-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="abb82-193">Debe tener instalado ForestPrep de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abb82-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="abb82-194">En caso contrario, los atributos de DL no existen en el esquema de los servicios de dominio de Active Directory y la herramienta no podrá crear listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="abb82-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="abb82-195">Para configurar listas de distribución, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abb82-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="abb82-196">En número de listas de distribución, especifique el número total de listas de distribución que desea crear.</span><span class="sxs-lookup"><span data-stu-id="abb82-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="abb82-197">(Le recomendamos que comience con el doble de usuarios).</span><span class="sxs-lookup"><span data-stu-id="abb82-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="abb82-198">Se numeran de 0 a n-1.</span><span class="sxs-lookup"><span data-stu-id="abb82-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="abb82-199">En Prefijo de lista de distribución, especifique el prefijo que tendrá la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="abb82-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="abb82-200">Por ejemplo, si especifica 100 DLs y un prefijo de testDL, las listas de distribución se denominarán testDL0, testDL1 y así sucesivamente, a través de testDL99.</span><span class="sxs-lookup"><span data-stu-id="abb82-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="abb82-201">En la lista de miembros mínimos de una lista de distribución, especifique el número mínimo de usuarios que desea agregar en cada lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="abb82-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="abb82-202">En máximo de miembros de una lista DISTR., especifique el número máximo de usuarios que desea agregar en cada lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="abb82-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="abb82-203">Botón crear listas de distribución</span><span class="sxs-lookup"><span data-stu-id="abb82-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="abb82-204">Al hacer clic en el botón crear listas de distribución, la herramienta consulta servicios de dominio de Active Directory para ver si ya existen listas de distribución que coincidan con el prefijo y los números.</span><span class="sxs-lookup"><span data-stu-id="abb82-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="abb82-205">La herramienta creará solo las que aún no existen.</span><span class="sxs-lookup"><span data-stu-id="abb82-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="abb82-206">Al agregar miembros a estas listas de distribución recién creadas, se seleccionarán los usuarios del rango especificado en la pestaña creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="abb82-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="abb82-207">Ficha Configuración del servicio de información de ubicación</span><span class="sxs-lookup"><span data-stu-id="abb82-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="abb82-208">Una de las características de la herramienta Lync Server 2013 stress and performance es generar archivos de configuración ficticios para el servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="abb82-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="abb82-209">El servicio de información de ubicación normalmente no tiene ningún impacto significativo en el rendimiento de los servidores.</span><span class="sxs-lookup"><span data-stu-id="abb82-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="abb82-210">![Pestaña de configuración del servicio de información de ubicación.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Pestaña de configuración del servicio de información de ubicación.")</span><span class="sxs-lookup"><span data-stu-id="abb82-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="abb82-211">Si elige probar esta característica, puede rellenar los valores mencionados en el formulario y, a continuación, hacer clic en el botón generar archivos de configuración de LIS.</span><span class="sxs-lookup"><span data-stu-id="abb82-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="abb82-212">Generará archivos CSV llamados subred LIS\_. csv, conmutadores\_Lis. csv, puertos\_Lis. csv y Lis\_. csv de lis.</span><span class="sxs-lookup"><span data-stu-id="abb82-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="abb82-213">Después, puede importar estos archivos CSV en la base de datos de LIS con el cmdlet **set-CsLisSubnet** , el cmdlet Set **-CsLisSwitch** , el cmdlet **set-CsLisPort** y el cmdlet **set-CsWirelessAccessPoint** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="abb82-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

