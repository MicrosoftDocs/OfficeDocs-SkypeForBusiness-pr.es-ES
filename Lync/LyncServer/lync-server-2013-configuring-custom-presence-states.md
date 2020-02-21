---
title: 'Lync Server 2013: configuración de Estados de presencia personalizados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f93229ee06a3d45db2478003a18ac22a2e7cf59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="9e62b-102">Configuración de los Estados de presencia personalizados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e62b-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e62b-103">_**Última modificación del tema:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="9e62b-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="9e62b-104">Para definir los Estados de presencia personalizados en Lync 2013, cree un archivo de configuración de presencia personalizada XML y, a continuación, especifique su ubicación con los cmdlets **New-CSClientPolicy** o **set-CSClientPolicy** del shell de administración de Lync Server con el parámetro CustomStateURL.</span><span class="sxs-lookup"><span data-stu-id="9e62b-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="9e62b-105">Los archivos de configuración tienen las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9e62b-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="9e62b-106">Los Estados de presencia personalizados se pueden configurar con los indicadores de presencia disponible, ocupado y no molestar.</span><span class="sxs-lookup"><span data-stu-id="9e62b-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="9e62b-107">El atributo Availability determina qué indicador de presencia está asociado con el texto de estado del estado personalizado.</span><span class="sxs-lookup"><span data-stu-id="9e62b-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="9e62b-108">En el ejemplo más adelante en este tema, se muestra el texto de estado Working from Home a la derecha del indicador de presencia verde (disponible).</span><span class="sxs-lookup"><span data-stu-id="9e62b-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="9e62b-109">La longitud máxima del texto de estado es de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9e62b-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="9e62b-110">Se pueden agregar un máximo de cuatro Estados de presencia personalizados.</span><span class="sxs-lookup"><span data-stu-id="9e62b-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="9e62b-111">El parámetro CustomStateURL especifica la ubicación del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9e62b-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="9e62b-112">En Lync 2013, el modo de alta seguridad SIP está habilitado de forma predeterminada, por lo que tendrá que almacenar el archivo de configuración de presencia personalizada en un servidor Web que tenga habilitado HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9e62b-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="9e62b-113">De lo contrario, los clientes de Lync 2013 no podrán conectarse a él.</span><span class="sxs-lookup"><span data-stu-id="9e62b-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="9e62b-114">Por ejemplo, una dirección válida sería `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span><span class="sxs-lookup"><span data-stu-id="9e62b-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e62b-115">Aunque no se recomienda en un entorno de producción, puede probar un archivo de configuración que se encuentra en un recurso compartido de archivos distinto de HTTPS mediante la configuración del registro EnableSIPHighSecurityMode para deshabilitar el modo de alta seguridad SIP en el cliente.</span><span class="sxs-lookup"><span data-stu-id="9e62b-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="9e62b-116">A continuación, puede usar la configuración del registro CustomStateURL para especificar una ubicación que no sea HTTPS para el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9e62b-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="9e62b-117">Tenga en cuenta que Lync 2013 respeta la configuración del registro de Lync 2010, pero el subárbol del registro se ha actualizado.</span><span class="sxs-lookup"><span data-stu-id="9e62b-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="9e62b-118">Crearía la configuración del registro de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9e62b-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9e62b-119">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="9e62b-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="9e62b-120">Tipo: DWORD</span><span class="sxs-lookup"><span data-stu-id="9e62b-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="9e62b-121">Datos del valor: 0</span><span class="sxs-lookup"><span data-stu-id="9e62b-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="9e62b-122">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="9e62b-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="9e62b-123">Tipo: String (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="9e62b-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="9e62b-124">Datos del valor (ejemplos):\\File://lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.xml o File:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</span><span class="sxs-lookup"><span data-stu-id="9e62b-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="9e62b-125">Localice el estado de presencia personalizado especificando uno o más esquemas de identificador de configuración regional (LCID) en el archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="9e62b-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="9e62b-126">El ejemplo más adelante en este tema muestra la localización en inglés-Estados Unidos (1033), Noruego-Bokmål (1044), francés de Francia (1036) y Turco (1055).</span><span class="sxs-lookup"><span data-stu-id="9e62b-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="9e62b-127">Para obtener una lista de LCID, consulte IDs de configuración regional asignada <https://go.microsoft.com/fwlink/p/?linkid=157331>por Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="9e62b-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="9e62b-128">Para agregar Estados de presencia personalizada a Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9e62b-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="9e62b-129">Cree un archivo de configuración XML que use el formato del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e62b-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="9e62b-130">Guarde el archivo de configuración XML en un servidor Web con HTTPS habilitado.</span><span class="sxs-lookup"><span data-stu-id="9e62b-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="9e62b-131">En este ejemplo, el archivo se denomina Presence. XML y se guarda en la https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xmlubicación.</span><span class="sxs-lookup"><span data-stu-id="9e62b-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="9e62b-132">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9e62b-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="9e62b-133">En el shell de administración de Lync Server, defina la ubicación del archivo de configuración XML mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e62b-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="9e62b-134">Use el cmdlet **Grant-CSClientPolicy** para asignar esta nueva Directiva a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9e62b-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="9e62b-135">Para obtener más información, consulte [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) y [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e62b-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="9e62b-136">De forma predeterminada, Lync Server&nbsp;2013 actualiza las directivas y la configuración del cliente cada tres horas.</span><span class="sxs-lookup"><span data-stu-id="9e62b-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="9e62b-137">Si desea seguir usando la configuración de la Directiva de grupo de versiones anteriores, como CustomStateURL, Lync 2013 reconocerá la configuración si se encuentra en el subárbol del registro de la nueva Directiva (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span><span class="sxs-lookup"><span data-stu-id="9e62b-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="9e62b-138">Sin embargo, las directivas de cliente basadas en servidor tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="9e62b-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

