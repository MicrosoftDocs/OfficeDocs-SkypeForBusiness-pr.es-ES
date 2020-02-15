---
title: 'Lync Server 2013: preparación del esquema de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d98f7ba4ac0f2efe8a78ebcaacdc966ac5fdf3a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="3b788-102">Preparar el esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b788-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b788-103">_**Última modificación del tema:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="3b788-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="3b788-104">Antes de empezar a preparar los servicios de dominio de Active Directory, puede abrir los archivos de esquema con un editor de texto, como el Bloc de notas de Windows, o ver las [extensiones de esquema, las clases y los atributos de Active Directory usados por Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) para revisar todas las extensiones de esquema de servicios de dominio de Active Directory que se modificarán para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b788-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="3b788-105">Lync Server usa cuatro archivos de esquema:</span><span class="sxs-lookup"><span data-stu-id="3b788-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="3b788-106">ExternalSchema. ldf, que se usa para la interoperabilidad con Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3b788-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="3b788-107">ServerSchema. ldf, que es el archivo de esquema principal de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b788-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="3b788-108">BackCompatSchema.ldf, que se usa para la interoperabilidad con todos los componentes de versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="3b788-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="3b788-109">VersionSchema.ldf, que se usa para la información de versión del esquema preparado</span><span class="sxs-lookup"><span data-stu-id="3b788-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="3b788-110">Todos los archivos .ldf se instalan durante la preparación del esquema, sin importar si se está migrando desde una versión anterior o si se está realizando una instalación limpia.</span><span class="sxs-lookup"><span data-stu-id="3b788-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="3b788-111">Estos archivos de esquema se instalan en la secuencia que se muestra en la lista anterior y \\se\\encuentran en la carpeta esquema de soporte en los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="3b788-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="3b788-112">Las extensiones de esquema de Lync Server se replican en todos los dominios, lo que afecta al tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="3b788-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="3b788-113">Ejecute la preparación del esquema cuando el uso de la red sea bajo.</span><span class="sxs-lookup"><span data-stu-id="3b788-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b788-114">Si necesita agregar compatibilidad con los clientes móviles de Microsoft® Office Communicator Mobile 2007 R2 para Java y Microsoft® Office Communicator Mobile para Nokia 1,0 a su implementación de Lync Server 2013, debe preparar el esquema de Active Directory para Microsoft Office Communications Server 2007 R2 durante la instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b788-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="3b788-115">Para consultar la documentación y el software necesario <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>, consulte.</span><span class="sxs-lookup"><span data-stu-id="3b788-115">For the necessary software and documentation, see <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="3b788-116">ADSI Edit</span><span class="sxs-lookup"><span data-stu-id="3b788-116">ADSI Edit</span></span>

<span data-ttu-id="3b788-117">El editor de interfaces de servicio de Active Directory (ADSI Edit) es una herramienta administrativa del servicio de dominio de Active Directory (AD DS) que puede usarse para verificar la preparación y replicación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="3b788-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="3b788-118">ADSI Edit se instala de forma predeterminada al instalar el rol AD DS para hacer del servidor un controlador de dominios.</span><span class="sxs-lookup"><span data-stu-id="3b788-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="3b788-119">Para Windows Server 2008 y Windows Server 2008 R2, ADSI Edit (AdsiEdit. msc) se incluye con las herramientas de administración remota del servidor (RSAT).</span><span class="sxs-lookup"><span data-stu-id="3b788-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="3b788-120">También puede instalar las RSAT en servidores de miembros de domino o en servidores independientes.</span><span class="sxs-lookup"><span data-stu-id="3b788-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="3b788-121">El paquete de RSAT se copia de forma predeterminada en estos servidores al instalar Windows, pero no se instala de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3b788-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="3b788-122">Las herramientas individuales se instalan con el Administrador de servidores.</span><span class="sxs-lookup"><span data-stu-id="3b788-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="3b788-123">El editor ADSI se incluye en **Herramientas de administración de roles**, **Herramientas de los Servicios de dominio de Active Directory**, **Herramientas del controlador de dominio de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3b788-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="3b788-124">Para Windows Server 2003, el editor ADSI se incluye con las herramientas de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="3b788-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="3b788-125">Las herramientas de soporte están disponibles en el CD de Windows Server 2003 \\,\\en la carpeta Support Tools, o puede descargarlas desde "herramientas de soporte técnico de Windows server 2003 Service [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)Pack 2 32-bit" en.</span><span class="sxs-lookup"><span data-stu-id="3b788-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="3b788-126">Las instrucciones para instalar las herramientas de soporte desde el CD del producto están disponibles en "instalar herramientas de [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)soporte de Windows" en.</span><span class="sxs-lookup"><span data-stu-id="3b788-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="3b788-127">Adsiedit. dll se registra automáticamente al instalar las herramientas de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="3b788-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="3b788-128">Sin embargo, si copió los archivos en el equipo, debe ejecutar el comando **regsvr32** para registrar el archivo ADSIEdit. dll antes de poder ejecutar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3b788-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3b788-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3b788-129">In This Section</span></span>

  - [<span data-ttu-id="3b788-130">Ejecución de la preparación del esquema de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b788-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="3b788-131">Comprobar la replicación de esquemas de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b788-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b788-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b788-132">See Also</span></span>


[<span data-ttu-id="3b788-133">Preparar el bosque para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b788-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="3b788-134">Preparar dominios para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b788-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

