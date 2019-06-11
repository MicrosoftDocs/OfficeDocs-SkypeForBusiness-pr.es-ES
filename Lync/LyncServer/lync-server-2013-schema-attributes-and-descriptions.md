---
title: 'Lync Server 2013: descripciones y atributos de esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="e8518-102">Atributos y descripciones de esquema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8518-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8518-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e8518-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e8518-104">En esta sección se describen todos los atributos de esquema usados por Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8518-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="e8518-105">Para las clases asociadas a los atributos, consulte [atributos de esquema por clase en Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="e8518-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="e8518-106">Para obtener una lista de las clases y atributos que son nuevos en Lync Server 2013, consulte [cambios en el esquema de Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e8518-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="e8518-107">Los atributos que están vinculados se especifican como vínculos hacia adelante o vínculos hacia atrás.</span><span class="sxs-lookup"><span data-stu-id="e8518-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="e8518-108">Un atributo que hace referencia a otro objeto es un vínculo hacia adelante; el atributo del otro objeto que hace referencia al primer objeto es un vínculo hacia atrás.</span><span class="sxs-lookup"><span data-stu-id="e8518-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="e8518-109">Los vínculos de reenvío son actualizables, mientras que los vínculos posteriores son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e8518-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="e8518-110">Algunos atributos tienen un valor de máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="e8518-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="e8518-111">Para estos atributos, cada configuración está representada por un bit y el valor decimal que se muestra representa la posición del bit.</span><span class="sxs-lookup"><span data-stu-id="e8518-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="e8518-112">Las posiciones de bits comienzan con el bit 0.</span><span class="sxs-lookup"><span data-stu-id="e8518-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="e8518-113">Por ejemplo, 1 (binario) es el bit 0 establecido y 10000 (binario) es el bit 4 establecido.</span><span class="sxs-lookup"><span data-stu-id="e8518-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="e8518-114">Cada bit representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="e8518-114">Each bit represents a property.</span></span> <span data-ttu-id="e8518-115">A continuación se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="e8518-115">The following are some examples:</span></span>

  - <span data-ttu-id="e8518-116">10000 (binario) tiene un valor decimal de 16 (es decir, el bit 4 está establecido).</span><span class="sxs-lookup"><span data-stu-id="e8518-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="e8518-117">100 millones (binario) tiene un valor decimal de 256 (es decir, el bit 8 está establecido).</span><span class="sxs-lookup"><span data-stu-id="e8518-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="e8518-118">1100 (binario) tiene un valor decimal de 12 (es decir, los bits 2 y 3 están establecidos; las propiedades representadas por los dos bits están habilitadas).</span><span class="sxs-lookup"><span data-stu-id="e8518-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="e8518-119">1111000001 (binario) tiene un valor decimal de 961 (es decir, están establecidos los bits 0, 6, 7, 8 y 9; las propiedades de cada uno de estos bits están habilitadas).</span><span class="sxs-lookup"><span data-stu-id="e8518-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="e8518-120">Atributos de esquema para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8518-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8518-121">Atributo</span><span class="sxs-lookup"><span data-stu-id="e8518-121">Attribute</span></span></th>
<th><span data-ttu-id="e8518-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8518-122">Description</span></span></th>
<th><span data-ttu-id="e8518-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8518-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8518-124">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="e8518-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="e8518-125">Un atributo existente en servicios de dominio de Active Directory que está ahora asociado a las clases <strong>msRTCSIP-Pool</strong> y <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="e8518-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="e8518-126">Este atributo especifica el nombre de dominio completo (FQDN) de un grupo o servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="e8518-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="e8518-127">Un valor válido para cada segmento es de 63 caracteres; un valor válido para todo el FQDN es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8518-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8518-128">Novedades de Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="e8518-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="e8518-130">Este atributo contiene la representación de cadena del nombre distintivo (DN) del objeto de otro bosque que corresponde a este objeto.</span><span class="sxs-lookup"><span data-stu-id="e8518-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="e8518-131">Este atributo se usa para la expansión del grupo de distribución y la asistencia automática.</span><span class="sxs-lookup"><span data-stu-id="e8518-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="e8518-132">Este atributo se define en el esquema predeterminado de Active Directory para Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="e8518-133">Para evitar tener que actualizar AD DS a Windows Server 2003 R2, la preparación del esquema de Active Directory extiende el esquema de Windows Server 2003 con esta definición de atributo.</span><span class="sxs-lookup"><span data-stu-id="e8518-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="e8518-134">Novedades de Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="e8518-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="e8518-136">Este atributo de valor múltiple contiene la configuración del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="e8518-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="e8518-137">Este atributo se comparte con la mensajería unificada de Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="e8518-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="e8518-138">Novedades de Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="e8518-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="e8518-140">Este atributo de valor múltiple contiene los identificadores para las directivas de retención que se aplican al usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="e8518-141">Las directivas de retención mantienen los elementos del buzón de correo para el usuario durante el período de espera.</span><span class="sxs-lookup"><span data-stu-id="e8518-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="e8518-142">Este atributo se comparte con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e8518-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="e8518-143">Novedades de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8518-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="e8518-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="e8518-145">Este atributo almacena información del proveedor de servicios de audioconferencia para un usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="e8518-146">Novedades de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="e8518-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="e8518-148">Este atributo señala a la entrada de servicio de confianza del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8518-149">Novedades de Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="e8518-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="e8518-151">Este atributo contiene una lista de aplicaciones hospedadas en el servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e8518-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="e8518-152">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="e8518-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="e8518-154">Este atributo especifica las opciones para el contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8518-155">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="e8518-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="e8518-157">Este atributo contiene el idioma principal del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8518-158">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="e8518-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="e8518-160">Este atributo de valor múltiple contiene los idiomas secundarios para el contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8518-161">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="e8518-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="e8518-163">Este atributo contiene una lista de servidores de aplicaciones que pertenecen a este grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="e8518-164">El vínculo de reenvío correspondiente a este atributo de vínculo de retroceso es <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-165">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="e8518-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="e8518-167">Este atributo señala al grupo al que pertenece este servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e8518-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="e8518-168">Este es el vínculo hacia adelante.</span><span class="sxs-lookup"><span data-stu-id="e8518-168">This is the forward link.</span></span> <span data-ttu-id="e8518-169">El correspondiente vínculo de retroceso es <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-170">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-171">msRTCSIP-ArchiveDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-172">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-173">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-174">msRTCSIP-ArchiveDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-175">Este atributo especifica el valor predeterminado global dentro del límite del bosque para archivar todas las comunicaciones de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e8518-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="e8518-176">Esto lo aplica la capa del agente de archivado.</span><span class="sxs-lookup"><span data-stu-id="e8518-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="e8518-177">El intervalo de valores para este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8518-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-178"><strong>True</strong>: archivar todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="e8518-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="e8518-179"><strong>False</strong>: no archivar todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="e8518-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="e8518-180">Este atributo controla globalmente, dentro del límite del bosque, cómo se archivan las comunicaciones de los usuarios dentro de una red interna.</span><span class="sxs-lookup"><span data-stu-id="e8518-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="e8518-181"><strong>Comportamiento de Live Communications Server 2005 (ahora retirado)</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="e8518-182">El intervalo de valores para este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8518-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-183">0: archivar el cuerpo del mensaje [bit 0]</span><span class="sxs-lookup"><span data-stu-id="e8518-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="e8518-184">1: no archivar el cuerpo del mensaje [bit 0]</span><span class="sxs-lookup"><span data-stu-id="e8518-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="e8518-185"><strong>Comportamiento de Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="e8518-186">El intervalo de valores para este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8518-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-187">0: ArchiveFederationDefaultWithoutBody (retirado)</span><span class="sxs-lookup"><span data-stu-id="e8518-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="e8518-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="e8518-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="e8518-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="e8518-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="e8518-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="e8518-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="e8518-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8518-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8518-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8518-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8518-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="e8518-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="e8518-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8518-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8518-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8518-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8518-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8518-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8518-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="e8518-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="e8518-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="e8518-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="e8518-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="e8518-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="e8518-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="e8518-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="e8518-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="e8518-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-202">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-203">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-204">msRTCSIP-ArchiveFederationDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-205">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-206">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-207">msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-208">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-209">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="e8518-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="e8518-211">Este atributo es un entero usado como campo de bits para controlar si se van a archivar las comunicaciones de un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="e8518-212">Este control lo aplica la capa del agente de archivado.</span><span class="sxs-lookup"><span data-stu-id="e8518-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="e8518-213">Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="e8518-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8518-214">El ámbito de este atributo es específico de un solo usuario o contacto.</span><span class="sxs-lookup"><span data-stu-id="e8518-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="e8518-215">Los valores válidos (y las posiciones de bits asociadas) en Lync Server son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-216">0: no archivar (sin bit establecido)</span><span class="sxs-lookup"><span data-stu-id="e8518-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="e8518-217">1: retirado (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="e8518-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e8518-218">2: retirado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="e8518-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e8518-219">4: comunicaciones internas de archivo (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="e8518-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8518-220">8: archivar comunicaciones federadas (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="e8518-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="e8518-221">Los valores anteriores válidos en Live Communications Server 2005 son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-222">0: Use el valor predeterminado definido por <strong>msRTCSIP-ArchiveDefault</strong> y <strong>msRTCSIP-ArchiveFederation</strong> en este orden de prioridad:</span><span class="sxs-lookup"><span data-stu-id="e8518-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-223">1: archivo</span><span class="sxs-lookup"><span data-stu-id="e8518-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="e8518-224">2: no archivar</span><span class="sxs-lookup"><span data-stu-id="e8518-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="e8518-225">3: archivar sin el cuerpo del mensaje</span><span class="sxs-lookup"><span data-stu-id="e8518-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="e8518-226">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-227">msRTCSIP-ArchivingServerData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-228">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-229">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-230">msRTCSIP-ArchivingServerVersion (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-231">Este atributo define la versión del servicio de archivado.</span><span class="sxs-lookup"><span data-stu-id="e8518-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="e8518-232">Este atributo es un tipo entero monotonously que se incrementa con cada lanzamiento oficial de producto.</span><span class="sxs-lookup"><span data-stu-id="e8518-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="e8518-233">Los valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="e8518-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-234">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8518-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e8518-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e8518-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="e8518-236">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="e8518-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e8518-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8518-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e8518-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e8518-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-239">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-240">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="e8518-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="e8518-242">Este atributo especifica el nombre de dominio completo (FQDN) del servidor back-end de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="e8518-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="e8518-243">Puesto que solo puede haber un único servidor de servicios de fondo por grupo, se trata de un atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="e8518-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="e8518-244">El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8518-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8518-245">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="e8518-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="e8518-247">Este atributo contiene el identificador del grupo de servidores que hospeda el directorio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="e8518-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="e8518-248">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="e8518-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="e8518-250">Este atributo contiene el identificador de un directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e8518-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="e8518-251">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="e8518-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="e8518-253">Este atributo contiene el identificador de la agrupación a la que se mueve el directorio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="e8518-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="e8518-254">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-255">msRTCSIP-default</span><span class="sxs-lookup"><span data-stu-id="e8518-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="e8518-256">Este atributo booleano define si el uso del teléfono es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e8518-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="e8518-257">Si este atributo se establece en <strong>true</strong>, el uso del teléfono es un uso predeterminado y el administrador no puede eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="e8518-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="e8518-258">Si este atributo se establece en <strong>false</strong>, el uso se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="e8518-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="e8518-259">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="e8518-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="e8518-261">Este atributo identifica la dirección URL de Communicator Web Access para los usuarios que están fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="e8518-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="e8518-262">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="e8518-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="e8518-264">Este atributo identifica la dirección URL de Communicator Web Access para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="e8518-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="e8518-265">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-266">msRTCSIP-DefaultLocationProfileLink (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-267">Este atributo de valor único contiene el nombre distintivo (DN) de un objeto de clase de Perfil de ubicación asignado a él.</span><span class="sxs-lookup"><span data-stu-id="e8518-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="e8518-268">Vínculo hacia adelante: <strong>identificador de vínculo 11036</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="e8518-269">El correspondiente vínculo de retroceso es <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-270">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-271">msRTCSIP-DefaultPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-272">Este atributo Boolean especifica si la Directiva es una directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e8518-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="e8518-273">La Directiva es una directiva predeterminada cuando se establece en <strong>true</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-274">Novedades de Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8518-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="e8518-275">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-276">msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-277">Este atributo especifica el FQDN del servidor perimetral que está ejecutando el servicio perimetral de acceso, si se puede obtener acceso a él directamente, o del equilibrador de carga de hardware para un grupo de servidores que ejecutan el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="e8518-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="e8518-278">Si solo se puede acceder a los servidores que ejecutan Access Edge a través de uno o más directores, este atributo especifica el FQDN y, opcionalmente, el número de puerto del director o del equilibrador de carga de hardware que atiende un grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="e8518-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="e8518-279">El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8518-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8518-280">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-281">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-283">Este atributo representa el número de puerto que debe usarse para conectarse al servidor que ejecuta el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="e8518-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="e8518-284">El valor válido es un valor entero que especifica el puerto que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e8518-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="e8518-285">El valor predeterminado es 5061.</span><span class="sxs-lookup"><span data-stu-id="e8518-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="e8518-286">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-287">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-289">Este atributo representa el período de tiempo de espera predeterminado de la suscripción de presencia.</span><span class="sxs-lookup"><span data-stu-id="e8518-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="e8518-290">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-291">msRTCSIP-DefRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-292">Este atributo representa la ventana de tiempo de espera de registro predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e8518-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8518-293">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-295">Este atributo representa la ventana de tiempo de espera predeterminada de la suscripción de datos de itinerancia.</span><span class="sxs-lookup"><span data-stu-id="e8518-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8518-296">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="e8518-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="e8518-298">Este atributo se usa en una topología de dominio dividida y contiene un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="e8518-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="e8518-299">Novedades de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-300">msRTCSIP-Description (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-301">Este atributo de cadena Unicode de valor único contiene una descripción detallada de esta ruta de teléfono o regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="e8518-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="e8518-302">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-303">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="e8518-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="e8518-305">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="e8518-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="e8518-307">Este atributo representa un dominio configurado para el registrador.</span><span class="sxs-lookup"><span data-stu-id="e8518-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="e8518-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="e8518-309">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-310">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="e8518-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8518-312">Este atributo especifica el FQDN del servidor que ejecuta el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="e8518-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="e8518-313">El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8518-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8518-314">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-315">msRTCSIP-EnableBestEffortNotify (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-316">Este atributo controla si un servidor genera una solicitud de notificación de mejor esfuerzo (BENOTIFY), en lugar de una solicitud NOTIFY, en respuesta a una solicitud SUBSCRIBE de un cliente.</span><span class="sxs-lookup"><span data-stu-id="e8518-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="e8518-317">BENOTIFY es una extensión que mejora el rendimiento del Protocolo de enlace para notificaciones en el que el servidor genera solicitudes BENOTIFY, en lugar de solicitudes de notificación ordinarias.</span><span class="sxs-lookup"><span data-stu-id="e8518-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="e8518-318">La ventaja de rendimiento es que una solicitud BENOTIFY no requiere una respuesta 200 del cliente, ya que la solicitud NOTIFY sí.</span><span class="sxs-lookup"><span data-stu-id="e8518-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="e8518-319">Los valores válidos son <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e8518-320">Live Communications Server 2003 no admite solicitudes BENOTIFY.</span><span class="sxs-lookup"><span data-stu-id="e8518-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="e8518-321">Para interactuar con aplicaciones de servidor escritas con la API de servidor de Live Communications Server 2003 que se ejecuta en Live Communications Server 2005 y en servidores de terceros, las solicitudes BENOTIFY pueden deshabilitarse estableciendo su valor en <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e8518-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="e8518-322">BENOTIFY no forma parte del proceso de estandarización de SIP (el equipo de tareas de ingeniería de Internet) IETF.</span><span class="sxs-lookup"><span data-stu-id="e8518-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="e8518-323">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-324">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-325">msRTCSIP-EnableFederation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-326">Este atributo es un modificador global que los administradores de ti usan para configurar si los usuarios pueden comunicarse con usuarios de otras organizaciones.</span><span class="sxs-lookup"><span data-stu-id="e8518-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="e8518-327">Permite a un administrador sobrescribir el atributo <strong>FederationEnabled</strong> de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="e8518-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="e8518-328">Este atributo puede ser útil para ayudar a proteger la red interna de ataques de Internet que pueden estar causados por gusanos, virus o ataques dirigidos a la compañía.</span><span class="sxs-lookup"><span data-stu-id="e8518-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="e8518-329">Los valores válidos (y las posiciones de bits asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-330">1: habilitado para conectividad de mensajería instantánea pública (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="e8518-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e8518-331">2: reservado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="e8518-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e8518-332">4: reservado (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="e8518-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8518-333">8: reservado (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="e8518-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e8518-334">16: control remoto de llamadas habilitado [telefonía] (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="e8518-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="e8518-335">64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios invitar a usuarios anónimos a reuniones (bit 6)</span><span class="sxs-lookup"><span data-stu-id="e8518-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="e8518-336">128: UCEnabled (habilitar usuarios para comunicaciones unificadas) (posición de bit 7)</span><span class="sxs-lookup"><span data-stu-id="e8518-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="e8518-337">256: EnabledForEnhancedPresence (habilitar usuario para conectividad de mensajería instantánea pública) (posición de bit 8)</span><span class="sxs-lookup"><span data-stu-id="e8518-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="e8518-338">512: RemoteCallControlDualMode (posición de bit 9)</span><span class="sxs-lookup"><span data-stu-id="e8518-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-339">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-340">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="e8518-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="e8518-342">Este atributo indica si los servicios empresariales se cargan en el servidor dado.</span><span class="sxs-lookup"><span data-stu-id="e8518-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e8518-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="e8518-344">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="e8518-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="e8518-346">Este atributo contiene el código de marcado para acceso externo.</span><span class="sxs-lookup"><span data-stu-id="e8518-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="e8518-347">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="e8518-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="e8518-349">Este atributo controla si un solo usuario está habilitado para la Federación.</span><span class="sxs-lookup"><span data-stu-id="e8518-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="e8518-350">La capa de servicios empresariales la aplica.</span><span class="sxs-lookup"><span data-stu-id="e8518-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="e8518-351">Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="e8518-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8518-352">Los valores válidos son <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-353">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="e8518-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="e8518-355">Este atributo es una lista con varios valores de los nombres de dominio de todos los servidores Enterprise Edition asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="e8518-356">Vínculo anterior: <strong>identificador de vínculo 11023</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="e8518-357">El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-358">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-359">msRTCSIP-gateways (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-360">Este atributo de cadena de valor múltiple contiene una lista de puertas de enlace y puertos (por puerta de enlace).</span><span class="sxs-lookup"><span data-stu-id="e8518-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="e8518-361">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-362">msRTCSIP-GlobalSettingsData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-363">Este atributo almacena pares de nombre: valor.</span><span class="sxs-lookup"><span data-stu-id="e8518-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="e8518-364">El par nombre: valor ya definido es para permitir el <strong>sondeo de la configuración de presencia</strong> .</span><span class="sxs-lookup"><span data-stu-id="e8518-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="e8518-365">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="e8518-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="e8518-367">Este atributo es un identificador único de un grupo que se usa para agrupar las entradas de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e8518-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="e8518-368">Novedades de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-369">msRTCSIP-HomeServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-370">Novedades de Live Communications Server 2003 (no usado).</span><span class="sxs-lookup"><span data-stu-id="e8518-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="e8518-371">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-372">msRTCSIP-HomeServerString (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-373">Novedades de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e8518-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e8518-374">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-375">msRTCSIP-HomeUsers (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-376">Novedades de Live Communications Server 2003 (no usado).</span><span class="sxs-lookup"><span data-stu-id="e8518-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="e8518-377">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="e8518-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="e8518-379">Este atributo controla si un solo usuario está habilitado para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="e8518-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="e8518-380">La capa de servicios empresariales la aplica.</span><span class="sxs-lookup"><span data-stu-id="e8518-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="e8518-381">Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="e8518-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8518-382">Los valores válidos son <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-383">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-384">msRTCSIP-IsMaster (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-385">Novedades de Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8518-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e8518-386">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-387">msRTCSIP-line</span><span class="sxs-lookup"><span data-stu-id="e8518-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="e8518-388">Este atributo de valor único contiene el identificador de dispositivo (el URI de SIP o el URI de TEL? del teléfono que usa Lync para telefonía).</span><span class="sxs-lookup"><span data-stu-id="e8518-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="e8518-389">Este atributo está marcado para la replicación del catálogo global y está indizado.</span><span class="sxs-lookup"><span data-stu-id="e8518-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="e8518-390">Si un usuario está habilitado para Enterprise Voice, este atributo almacena la versión normalizada E. 164 del número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="e8518-391">Novedades de Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="e8518-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="e8518-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="e8518-393">Este atributo de valor único contiene el URI SIP del servidor de puerta de enlace CSTA-SIP.</span><span class="sxs-lookup"><span data-stu-id="e8518-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="e8518-394">Este atributo está marcado para la replicación del catálogo global, pero no está indizado.</span><span class="sxs-lookup"><span data-stu-id="e8518-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="e8518-395">Novedades de Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="e8518-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-396">msRTCSIP-LocalNormalizationData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-397">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-398">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-399">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-400">msRTCSIP-LocalNormalizationLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-401">Este atributo de valor múltiple contiene una lista de nombres completos de normalización (DN) de normalización asociados con este perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="e8518-402">El tipo de este atributo es un binario DN.</span><span class="sxs-lookup"><span data-stu-id="e8518-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="e8518-403">Existe una relación de uno a varios entre el perfil de ubicación y las reglas de normalización locales.</span><span class="sxs-lookup"><span data-stu-id="e8518-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="e8518-404">El orden de la lista de DNs de normalización local debe mantenerse en el orden especificado por el administrador.</span><span class="sxs-lookup"><span data-stu-id="e8518-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="e8518-405">La conservación del pedido se mantiene mediante la parte binaria del código binario DN, que especifica el índice del pedido.</span><span class="sxs-lookup"><span data-stu-id="e8518-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="e8518-406">Vínculo hacia adelante: <strong>identificador de vínculo 11034</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="e8518-407">El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-408">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-409">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="e8518-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="e8518-411">Este atributo contiene una lista de opciones para la regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="e8518-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="e8518-412">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-413">msRTCSIP-LocationName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-414">Este atributo de valor único contiene un nombre descriptivo para el perfil de ubicación que indica la ubicación que representa este perfil.</span><span class="sxs-lookup"><span data-stu-id="e8518-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="e8518-415">Dado que puede haber varios perfiles de ubicación, el administrador necesita una forma de distinguir los distintos perfiles.</span><span class="sxs-lookup"><span data-stu-id="e8518-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="e8518-416">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-417">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-418">msRTCSIP-locationProfileBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-419">Este atributo de valor múltiple contiene una lista de nombres distintivos del perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="e8518-420">Este atributo especifica el vínculo de retroceso a uno o más perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="e8518-421">Vínculo anterior: <strong>identificador de vínculo 11035</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="e8518-422">Este atributo corresponde al vínculo de reenvío <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-423">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-424">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-425">msRTCSIP-LocationProfileData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-426">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-427">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-428">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="e8518-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="e8518-430">Este atributo contiene las opciones para el perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="e8518-431">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="e8518-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="e8518-433">Este atributo de valor múltiple contiene una lista de contactos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="e8518-434">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="e8518-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="e8518-436">Este atributo de valor múltiple contiene una lista de perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="e8518-437">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-439">Este atributo representa el número máximo de solicitudes de búsqueda pendientes por servidor.</span><span class="sxs-lookup"><span data-stu-id="e8518-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="e8518-440">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-442">El atributo representa el número máximo de suscripciones por usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="e8518-443">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-445">Este atributo representa la ventana máximo de tiempo de espera de suscripción.</span><span class="sxs-lookup"><span data-stu-id="e8518-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8518-446">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-447">msRTCSIP-MaxRegistrationsTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-448">Este atributo representa el límite máximo de registros de la ventana de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e8518-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8518-449">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-451">Este atributo representa la ventana de tiempo de espera máxima de suscripciones de datos de movilidad.</span><span class="sxs-lookup"><span data-stu-id="e8518-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8518-452">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="e8518-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="e8518-454">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-455">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="e8518-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="e8518-457">Este atributo es un atributo del punto de control de servicio en la clase de equipo que especifica un vínculo a la fábrica de la unidad de control multipunto (MCU) a la que pertenece.</span><span class="sxs-lookup"><span data-stu-id="e8518-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="e8518-458">Este punto de control de servicio y atributo se crea para cada MCU de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e8518-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="e8518-459">Cada MCU de Microsoft debe encontrar el servidor back-end del grupo al que pertenece, a fin de recuperar la configuración de nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="e8518-460">El valor de este atributo es el nombre distintivo (DN) del generador MCU.</span><span class="sxs-lookup"><span data-stu-id="e8518-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="e8518-461">Este es un atributo de valor único y está marcado para replicación de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="e8518-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8518-462">Vínculo hacia adelante: <strong>identificador de vínculo 11026</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="e8518-463">El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-464">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="e8518-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="e8518-466">Este es un atributo reservado de cadena múltiple.</span><span class="sxs-lookup"><span data-stu-id="e8518-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="e8518-467">La configuración almacenada en este atributo se representa como un par nombre = valor.</span><span class="sxs-lookup"><span data-stu-id="e8518-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="e8518-468">Los pares de nombre definido actualmente = valor son:</span><span class="sxs-lookup"><span data-stu-id="e8518-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="e8518-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-470">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="e8518-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="e8518-472">Este es un atributo de valor único que contiene el nombre distintivo (DN) de un solo generador MCU asociado con un grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="e8518-473">Vínculo hacia adelante: <strong>identificador de vínculo 11024</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="e8518-474">El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-475">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="e8518-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="e8518-477">Este atributo es una cadena de valor único que especifica el GUID del proveedor de factoría MCU.</span><span class="sxs-lookup"><span data-stu-id="e8518-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="e8518-478">Según el valor de GUID, el proceso de fábrica de MCU determina si se debe atender a este tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="e8518-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="e8518-479">Si el valor de GUID es <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, el proceso de fábrica de MCU (disponible de forma predeterminada en Lync Server) lo procesará.</span><span class="sxs-lookup"><span data-stu-id="e8518-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="e8518-480">Para cualquier otro valor de GUID, el proceso de fábrica de MCU no procesará el tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="e8518-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="e8518-481">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="e8518-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="e8518-483">Este atributo es una lista con varios valores de nombres completos (DN).</span><span class="sxs-lookup"><span data-stu-id="e8518-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="e8518-484">Este atributo contiene una lista de todos los servidores MCU del mismo tipo y proveedor asociados a este generador MCU.</span><span class="sxs-lookup"><span data-stu-id="e8518-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="e8518-485">El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8518-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="e8518-486">Vínculo anterior: identificador de vínculo 11027</span><span class="sxs-lookup"><span data-stu-id="e8518-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="e8518-487">El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-488">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="e8518-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="e8518-490">Este atributo es una cadena de valor único que especifica el medio que el MCU puede controlar.</span><span class="sxs-lookup"><span data-stu-id="e8518-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="e8518-491">Los tipos válidos compatibles son:</span><span class="sxs-lookup"><span data-stu-id="e8518-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-492">satisfacción</span><span class="sxs-lookup"><span data-stu-id="e8518-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="e8518-493">audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="e8518-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="e8518-494">Chatea</span><span class="sxs-lookup"><span data-stu-id="e8518-494">chat</span></span></p></li>
<li><p><span data-ttu-id="e8518-495">conf. teléfono</span><span class="sxs-lookup"><span data-stu-id="e8518-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-496">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="e8518-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="e8518-498">Este atributo es una cadena de valor único que especifica el nombre de un proveedor de la MCU.</span><span class="sxs-lookup"><span data-stu-id="e8518-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="e8518-499">Todos los MCU de Microsoft especificarán que este atributo sea <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-500">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-501">msRTCSIP-MeetingFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-502">Este atributo define diferentes opciones de reunión que se habilitan globalmente para todos los usuarios o los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="e8518-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="e8518-503">Este atributo es un valor de máscara de bits de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="e8518-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="e8518-504">Los valores válidos (y las posiciones de bits asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-505">0: AllowOrganizeMeetingWithAnonymousParticipants es None (no permite que los usuarios inviten a usuarios anónimos a reuniones) (sin ningún bit)</span><span class="sxs-lookup"><span data-stu-id="e8518-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="e8518-506">4: AllowOrganizeMeetingWithAnonymousParticipants es todos (permitir que todos los usuarios inviten a usuarios anónimos a reuniones) (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="e8518-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8518-507">8: AllowOrganizeMeetingWithAnonymousParticipants es UsePerUserSetting (permitir a los usuarios invitar a usuarios anónimos a reuniones según la configuración por usuario) (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="e8518-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e8518-508">16: UserPerUserMeetingPolicy (se define la Directiva de reunión por usuario) (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="e8518-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-509">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-510">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-511">msRTCSIP-MeetingPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-512">Este atributo especifica el nombre completo (DN) de la Directiva que el administrador ha asignado a este usuario como un atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="e8518-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="e8518-513">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-514">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-516">Este atributo representa la ventana de tiempo de espera de suscripción de presencia mínima.</span><span class="sxs-lookup"><span data-stu-id="e8518-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8518-517">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-518">msRTCSIP-MinRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-519">Este atributo representa la ventana de tiempo de espera de registro mínimo.</span><span class="sxs-lookup"><span data-stu-id="e8518-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8518-520">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-521">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-523">Este atributo representa la ventana de tiempo de espera de la suscripción de datos de itinerancia mínima.</span><span class="sxs-lookup"><span data-stu-id="e8518-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8518-524">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-525">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="e8518-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="e8518-527">Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e8518-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="e8518-528">Novedades de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8518-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="e8518-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="e8518-530">Este atributo contiene opciones e indicadores que definen la configuración de movilidad.</span><span class="sxs-lookup"><span data-stu-id="e8518-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="e8518-531">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="e8518-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="e8518-533">Este atributo contiene el DN de un objeto de directiva de movilidad.</span><span class="sxs-lookup"><span data-stu-id="e8518-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="e8518-534">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-535">msRTCSIP-NumDevicesPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-536">Este atributo representa la cantidad permitida de dispositivos en los que un usuario puede registrarse para comunicaciones SIP y suscribirse a la presencia.</span><span class="sxs-lookup"><span data-stu-id="e8518-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="e8518-537">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-538">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="e8518-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="e8518-540">Este atributo especifica las opciones que están habilitadas para el objeto de usuario o contacto.</span><span class="sxs-lookup"><span data-stu-id="e8518-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="e8518-541">Este atributo es un valor de máscara de bits de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="e8518-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="e8518-542">Cada opción está representada por un bit.</span><span class="sxs-lookup"><span data-stu-id="e8518-542">Each option is represented by a bit.</span></span> <span data-ttu-id="e8518-543">Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="e8518-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8518-544">Los valores válidos (y las posiciones de bits asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-545">1: habilitado para conectividad de mensajería instantánea (mi) pública (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="e8518-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e8518-546">2: reservado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="e8518-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e8518-547">4: reservado (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="e8518-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8518-548">8: reservado (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="e8518-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e8518-549">16: control remoto de llamadas habilitado [telefonía] (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="e8518-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="e8518-550">64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios invitar a usuarios anónimos a reuniones (bit 6)</span><span class="sxs-lookup"><span data-stu-id="e8518-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="e8518-551">128: UCEnabled (habilitar usuarios para UC) (posición de bit 7)</span><span class="sxs-lookup"><span data-stu-id="e8518-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="e8518-552">256: EnabledForEnhancedPresence (habilitar usuario para conectividad de mensajería instantánea pública) (posición de bit 8)</span><span class="sxs-lookup"><span data-stu-id="e8518-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="e8518-553">512: RemoteCallControlDualMode (posición de bit 9)</span><span class="sxs-lookup"><span data-stu-id="e8518-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-554">Novedades de Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="e8518-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="e8518-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="e8518-556">Este atributo se usa en las topologías de bosque de recursos y central para habilitar el inicio de sesión único cuando el ObjectSID de un usuario de la cuenta principal de Windows NT Server se copia en este atributo del objeto de usuario o contacto correspondiente del recurso o del bosque central.</span><span class="sxs-lookup"><span data-stu-id="e8518-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="e8518-557">Communicator Web Access busca un usuario en AD DS con este atributo o el ObjectSID del usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="e8518-558">Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="e8518-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="e8518-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="e8518-560">Este atributo es el nombre de recursos uniforme (URN) del propietario de un contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8518-561">Novedades de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-562">msRTCSIP-Pattern (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-563">Este atributo de cadena de valor único contiene un patrón usado para hacer coincidir números de marcado con el formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="e8518-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="e8518-564">Si el número de marcado coincide con este patrón, la traducción se aplica al número marcado.</span><span class="sxs-lookup"><span data-stu-id="e8518-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="e8518-565">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-566">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-567">msRTCSIP-PhoneRouteBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-568">Este atributo de valor múltiple contiene una lista de nombres distintivos de rutas de teléfono (DN).</span><span class="sxs-lookup"><span data-stu-id="e8518-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="e8518-569">Este atributo especifica el vínculo de retroceso a una o más rutas de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e8518-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="e8518-570">Vínculo anterior: <strong>identificador de vínculo 11033</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="e8518-571">Este atributo corresponde al vínculo de reenvío <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-572">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-573">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-574">msRTCSIP-PhoneRouteData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-575">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-576">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-577">msRTCSIP-PhoneRouteName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-578">Este atributo de cadena Unicode de valor único especifica el nombre descriptivo de la ruta telefónica, de modo que el administrador puede hacer referencia a ella fácilmente.</span><span class="sxs-lookup"><span data-stu-id="e8518-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="e8518-579">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-580">msRTCSIP-PhoneUsageData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-581">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-582">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-583">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-584">msRTCSIP-PolicyContent (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-585">Este atributo es una cadena Unicode de valor único.</span><span class="sxs-lookup"><span data-stu-id="e8518-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="e8518-586">Este atributo de cadena contiene la definición de directiva en formato XML.</span><span class="sxs-lookup"><span data-stu-id="e8518-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="e8518-587">La definición del esquema XML es común en los distintos tipos de Directiva, solo la configuración es distinta para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="e8518-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="e8518-588">La definición de esquema XML (XSD) se define de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e8518-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="e8518-589">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-590">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-591">msRTCSIP-PolicyData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-592">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-593">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-594">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-595">msRTCSIP-PolicyType (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-596">Este atributo de cadena Unicode de valor único contiene el tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="e8518-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="e8518-597">Los tipos de directiva válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-598">satisfacción</span><span class="sxs-lookup"><span data-stu-id="e8518-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="e8518-599">telefonía</span><span class="sxs-lookup"><span data-stu-id="e8518-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-600">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-601">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="e8518-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="e8518-603">Este atributo especifica un vínculo al grupo al que pertenece el equipo.</span><span class="sxs-lookup"><span data-stu-id="e8518-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="e8518-604">Este atributo se establece independientemente de si el equipo está ejecutando la versión Standard Edition o la versión Enterprise de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8518-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="e8518-605">Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="e8518-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8518-606">El valor válido es el nombre de dominio del grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="e8518-607">Vínculo hacia adelante: <strong>identificador de vínculo 11022</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="e8518-608">El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-609">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="e8518-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="e8518-611">Se trata de un atributo de valor múltiple que contiene una lista de los nombres completos (DN) de los grupos a los que está asociada la fábrica del MCU.</span><span class="sxs-lookup"><span data-stu-id="e8518-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="e8518-612">Vínculo anterior: <strong>identificador de vínculo 11025</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="e8518-613">El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-614">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="e8518-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="e8518-616">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-617">Novedades de Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="e8518-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="e8518-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="e8518-619">Este atributo especifica un nombre arbitrario para un grupo que se muestra en la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="e8518-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="e8518-620">El administrador puede cambiar este nombre.</span><span class="sxs-lookup"><span data-stu-id="e8518-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="e8518-621">El valor válido es una cadena que representa el nombre de un grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="e8518-622">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="e8518-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8518-624">Este atributo es un valor de cadena de valor único.</span><span class="sxs-lookup"><span data-stu-id="e8518-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="e8518-625">El valor de este atributo, cuando está presente, representa el FQDN de dominio del grupo si el administrador desea crear un grupo front-end con un FQDN que no se ajuste a la estructura de dominios de Active Directory en la que se crea el grupo front-end (por ejemplo, un SIP espacio de nombres separado del espacio de nombres del sistema de nombres de dominio (DNS)).</span><span class="sxs-lookup"><span data-stu-id="e8518-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="e8518-626">Le recomendamos que asigne el FQDN del dominio del grupo de servidores front-end a la parte de nombre de dominio como el dominio de Active Directory en el que se encuentra el grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="e8518-627">Por lo tanto, cuando no hay ningún valor en este atributo, el FQDN del grupo de servidores front-end se establece de forma predeterminada en la estructura de nombres de dominio de Active Directory, como indica el atributo <strong>DnsHostName</strong> .</span><span class="sxs-lookup"><span data-stu-id="e8518-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="e8518-628">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="e8518-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="e8518-630">Lista con varios valores de los nombres de dominio de todos los servidores de Lync Server, Enterprise Edition asociados a un grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="e8518-631">Este atributo de tipo entero define si el grupo es capaz de la mensajería instantánea (mi), la presencia y las reuniones.</span><span class="sxs-lookup"><span data-stu-id="e8518-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="e8518-632">Los posibles tipos de valor válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-633">Undefined: mensajería instantánea y servicio de presencia (Live Communications Server 2005 y 2003)</span><span class="sxs-lookup"><span data-stu-id="e8518-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="e8518-634">1: mensajería instantánea y servicio de presencia (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="e8518-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="e8518-635">2: mensajería instantánea y presencia y servicio de reuniones (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="e8518-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-636">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="e8518-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="e8518-638">Este atributo especifica si un grupo de servidores ejecuta un servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e8518-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="e8518-639">Este atributo es un valor de máscara de bits de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="e8518-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="e8518-640">Cada opción está representada por un bit.</span><span class="sxs-lookup"><span data-stu-id="e8518-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="e8518-641">Los valores válidos (y las posiciones de bits asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-642">1: servidor Standard Edition, usuarios de hosts (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="e8518-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e8518-643">2: servidor Enterprise Edition, usuarios de hosts (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="e8518-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e8518-644">4: servidor Standard Edition, aplicaciones de hosts (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="e8518-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8518-645">8: servidor Enterprise Edition, aplicaciones para hosts (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="e8518-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="e8518-646">Puesto que Lync Server no es compatible con los grupos que hospedan solo aplicaciones, los únicos valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-647">5: servidor Standard Edition, hospeda usuarios y aplicaciones (posiciones de bits 0 y 2)</span><span class="sxs-lookup"><span data-stu-id="e8518-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="e8518-648">10: servidor Enterprise Edition, hospeda usuarios y aplicaciones (posiciones de bits 1 y 3)</span><span class="sxs-lookup"><span data-stu-id="e8518-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-649">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="e8518-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="e8518-651">Este atributo define la versión del grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-651">This attribute defines the pool version.</span></span> <span data-ttu-id="e8518-652">Es un tipo entero que se incrementa con cada lanzamiento de producto principal.</span><span class="sxs-lookup"><span data-stu-id="e8518-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="e8518-653">Los posibles tipos de valor válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8518-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="e8518-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e8518-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="e8518-656">2: Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="e8518-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e8518-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8518-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e8518-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e8518-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e8518-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e8518-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-660">Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="e8518-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="e8518-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="e8518-662">Este atributo contiene opciones e indicadores que definen la configuración de presencia.</span><span class="sxs-lookup"><span data-stu-id="e8518-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="e8518-663">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="e8518-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="e8518-665">Este atributo contiene el DN de un objeto de directiva de presencia.</span><span class="sxs-lookup"><span data-stu-id="e8518-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="e8518-666">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="e8518-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="e8518-668">Este atributo habilita a un usuario o contacto para mensajería SIP.</span><span class="sxs-lookup"><span data-stu-id="e8518-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="e8518-669">Se agrega a la clase de contacto porque en la topología del bosque central, los objetos de contacto, no los objetos de usuario, están habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="e8518-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="e8518-670">El valor válido es el nombre completo del servidor Standard Edition o del grupo front-end de Enterprise Edition en el que se aloja un usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="e8518-671">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="e8518-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="e8518-673">Este atributo contiene la dirección SIP de un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="e8518-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="e8518-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="e8518-675">Este atributo contiene el identificador del dispositivo de línea privada.</span><span class="sxs-lookup"><span data-stu-id="e8518-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="e8518-676">Novedades de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-677">msRTCSIP-enrutable</span><span class="sxs-lookup"><span data-stu-id="e8518-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="e8518-678">Este atributo es un atributo booleano que se usa para determinar si Lync Server está autorizado a enrutar a este servicio mediante su dirección GRUU.</span><span class="sxs-lookup"><span data-stu-id="e8518-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="e8518-679">Si este valor se establece en <strong>true</strong>, Lync Server está autorizado para enrutar a este servicio.</span><span class="sxs-lookup"><span data-stu-id="e8518-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="e8518-680">Si este valor se establece en <strong>false</strong>, Lync Server no está autorizado a enrutar a este servicio.</span><span class="sxs-lookup"><span data-stu-id="e8518-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="e8518-681">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-682">msRTCSIP-RouteUsageAttribute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-683">Este atributo de cadena Unicode de valor único define un atributo que califica el uso de una ruta de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e8518-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="e8518-684">La selección de una ruta telefónica se determina en función de dos elementos: el atributo de uso asignado a la ruta telefónica y los atributos de uso de directivas permitidos por la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="e8518-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="e8518-685">Se selecciona la primera ruta del teléfono con un atributo de uso que coincida con el uso permitido de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="e8518-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="e8518-686">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-687">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-688">msRTCSIP-RouteUsageLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-689">Este atributo de nombre distintivo (DN) multivalor contiene una lista de nombres completos de uso de ruta.</span><span class="sxs-lookup"><span data-stu-id="e8518-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="e8518-690">Vínculo hacia adelante: <strong>identificador de vínculo 11032</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="e8518-691">Este atributo es un vínculo hacia adelante al vínculo atrás correspondiente <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-692">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="e8518-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="e8518-694">Este atributo contiene el DN que apunta al grupo al que debe pasar todo el tráfico SIP dirigido a este servicio MCU o de confianza.</span><span class="sxs-lookup"><span data-stu-id="e8518-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="e8518-695">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-696">msRTCSIP-RuleName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-697">Este atributo de cadena Unicode de valor único especifica el nombre descriptivo de la regla de normalización, de modo que un administrador puede hacer referencia a ella fácilmente.</span><span class="sxs-lookup"><span data-stu-id="e8518-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="e8518-698">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-699">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="e8518-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="e8518-701">Este atributo representa la versión del esquema implementada actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="e8518-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-702">msRTCSIP-SearchMaxRequests (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-703">Este atributo limita el número de resultados de búsqueda que se devolverán desde una búsqueda de directorio cuando un usuario busca un contacto con Communicator.</span><span class="sxs-lookup"><span data-stu-id="e8518-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="e8518-704">Este atributo invalidará el valor proporcionado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="e8518-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="e8518-705">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-706">msRTCSIP-SearchMaxResults (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-707">Este atributo limita el número de solicitudes de búsqueda devuelto.</span><span class="sxs-lookup"><span data-stu-id="e8518-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="e8518-708">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="e8518-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="e8518-710">Este atributo de valor múltiple es un vínculo hacia atrás que contiene una lista de nombres completos (DN).</span><span class="sxs-lookup"><span data-stu-id="e8518-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="e8518-711">Este DNs apunta a un grupo o a un objeto <strong>TrustedService</strong> .</span><span class="sxs-lookup"><span data-stu-id="e8518-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="e8518-712">Este atributo corresponde al vínculo de reenvío <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-713">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="e8518-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="e8518-715">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-716">msRTCSIP-ServerReferenceBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-717">Este atributo de valor múltiple contiene una lista de nombres completos.</span><span class="sxs-lookup"><span data-stu-id="e8518-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="e8518-718">Estos nombres completos devuelven vínculos que hacen referencia a otros objetos de servidor a los que se puede asignar un perfil de ubicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e8518-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="e8518-719">Vínculo anterior: <strong>identificador de vínculo 11037</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="e8518-720">El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="e8518-721">Este atributo de vínculo de retroceso solo hace referencia a los grupos y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="e8518-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="e8518-722">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-723">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e8518-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="e8518-725">Este atributo define la información de versión del servidor.</span><span class="sxs-lookup"><span data-stu-id="e8518-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="e8518-726">Este número de versión se aplica a todos los roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="e8518-726">This version number applies to all server roles.</span></span> <span data-ttu-id="e8518-727">Es un monotonously que aumenta con cada versión oficial del producto.</span><span class="sxs-lookup"><span data-stu-id="e8518-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="e8518-728">Los posibles valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-729">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8518-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e8518-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e8518-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="e8518-731">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="e8518-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e8518-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8518-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e8518-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e8518-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e8518-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e8518-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="e8518-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8518-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-736">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="e8518-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="e8518-738">Este atributo de valor único de tipo entero especifica el tipo de objeto al que apunta <strong>MSDS-SourceObjectDN</strong> , de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e8518-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-739">null | 0x00000001: representa un objeto de usuario principal de Windows NT Server de un bosque diferente</span><span class="sxs-lookup"><span data-stu-id="e8518-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="e8518-740">Los siguientes atributos representan un tipo de grupo de un bosque diferente para la expansión de grupos de distribución:</span><span class="sxs-lookup"><span data-stu-id="e8518-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e8518-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e8518-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e8518-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e8518-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e8518-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e8518-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e8518-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e8518-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="e8518-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="e8518-746">0x90000000: representa un objeto de acceso de operador automático o de suscriptor del mismo bosque o de un bosque diferente</span><span class="sxs-lookup"><span data-stu-id="e8518-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="e8518-747">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-748">msRTCSIP-SubscriptionAuthRequired (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-749">Novedades de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e8518-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e8518-750">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="e8518-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="e8518-752">Este atributo le permite mover un usuario o un objeto de contacto de un grupo de servidores de Lync a otro.</span><span class="sxs-lookup"><span data-stu-id="e8518-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="e8518-753">Este atributo se agrega a la clase de contacto, porque en la topología del bosque central, los objetos de contacto, no los objetos de usuario, están habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="e8518-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="e8518-754">El valor válido es el nombre completo del servidor Standard Edition o del grupo de servidores front end al que se va a mover un usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="e8518-755">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-756">msRTCSIP-TargetPhoneNumber (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-757">Este atributo de cadena de valor único contiene un intervalo o un patrón de números de teléfono para enrutar a las puertas de enlace especificadas definidas en <strong>msRTCSIP-gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-758">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="e8518-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="e8518-760">Este atributo almacena pares de nombre y valor para las directivas de destino de los usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8518-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="e8518-761">Novedades de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="e8518-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="e8518-763">Este atributo almacena el identificador único para un inquilino.</span><span class="sxs-lookup"><span data-stu-id="e8518-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="e8518-764">Novedades de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-765">msRTCSIP-Translation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-766">Este atributo es utilizado por la característica de voz de Lync Server y contiene la cadena de traducción para aplicar en el número marcado, si se encuentra una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="e8518-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="e8518-767">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8518-768">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="e8518-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="e8518-770">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-771">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="e8518-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8518-773">Este atributo es un valor de cadena que contiene el FQDN del MCU.</span><span class="sxs-lookup"><span data-stu-id="e8518-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="e8518-774">Este es un atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="e8518-774">This is a single-valued attribute.</span></span> <span data-ttu-id="e8518-775">El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8518-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8518-776">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="e8518-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="e8518-778">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-779">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="e8518-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8518-781">Este atributo es un valor de cadena que contiene el nombre completo del servidor que ejecuta Proxy Server.</span><span class="sxs-lookup"><span data-stu-id="e8518-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="e8518-782">Este atributo tiene un único valor.</span><span class="sxs-lookup"><span data-stu-id="e8518-782">This attribute is single-valued.</span></span> <span data-ttu-id="e8518-783">El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8518-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8518-784">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="e8518-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="e8518-786">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="e8518-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8518-788">Este atributo es un atributo de valor único que representa el FQDN de un servidor de confianza.</span><span class="sxs-lookup"><span data-stu-id="e8518-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="e8518-789">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="e8518-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="e8518-791">Este atributo especifica el número de versión de un servidor en la lista de servidores de confianza.</span><span class="sxs-lookup"><span data-stu-id="e8518-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="e8518-792">Los posibles valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8518-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="e8518-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e8518-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="e8518-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8518-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e8518-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e8518-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e8518-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e8518-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="e8518-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8518-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-799">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="e8518-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="e8518-801">Este atributo define las opciones que están habilitadas para el servicio de confianza.</span><span class="sxs-lookup"><span data-stu-id="e8518-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="e8518-802">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="e8518-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="e8518-804">Este atributo de valor múltiple contiene una lista de nombres completos (DN) que hacen referencia a un objeto de servicio de confianza, como un servicio de autenticación de retransmisión multimedia.</span><span class="sxs-lookup"><span data-stu-id="e8518-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="e8518-805">Un servicio de autenticación de retransmisión multimedia (que se encuentra físicamente en el servidor perimetral que ejecuta el servicio de conferencia A/V) debe estar asociado a un grupo para admitir escenarios de audio para usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="e8518-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="e8518-806">El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-807">UC</span><span class="sxs-lookup"><span data-stu-id="e8518-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="e8518-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="e8518-809">Este atributo es un entero que define el número de puerto que se usa para conectarse a este servicio de GRUU.</span><span class="sxs-lookup"><span data-stu-id="e8518-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="e8518-810">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="e8518-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="e8518-812">Este atributo es un valor de cadena que define el tipo de servicio GRUU que representa.</span><span class="sxs-lookup"><span data-stu-id="e8518-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="e8518-813">Los tipos de servicio GRUU válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="e8518-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="e8518-815">Puerta</span><span class="sxs-lookup"><span data-stu-id="e8518-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="e8518-816">Servicio de autenticación de retransmisión de multimedia (MRAS)</span><span class="sxs-lookup"><span data-stu-id="e8518-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="e8518-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="e8518-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="e8518-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="e8518-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-819">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="e8518-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="e8518-821">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-822">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="e8518-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8518-824">Este atributo es un valor de cadena que contiene el FQDN de los servicios Web de Lync Server de IIS.</span><span class="sxs-lookup"><span data-stu-id="e8518-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="e8518-825">Este es un atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="e8518-825">This is a single-valued attribute.</span></span> <span data-ttu-id="e8518-826">El valor válido para cada segmento es de 63 caracteres; el valor válido para todo el FQDN es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8518-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8518-827">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-828">msRTCSIP-UCFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-829">Este atributo define diferentes opciones de UC que se habilitan globalmente para todos los objetos de usuario o contacto.</span><span class="sxs-lookup"><span data-stu-id="e8518-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="e8518-830">Este atributo es un valor de máscara de bits de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="e8518-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="e8518-831">Cada opción está representada por la presencia de un bit.</span><span class="sxs-lookup"><span data-stu-id="e8518-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="e8518-832">El posible valor válido (y la posición de bits asociada) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-833">4: UsePerUserUCPolicy (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="e8518-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="e8518-834">Cuando se establece este bit, se define la Directiva de UC por usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="e8518-835">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-836">msRTCSIP-UCPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-837">Este atributo de valor único contiene el nombre completo (DN) de la Directiva UC que el administrador ha asignado para este usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="e8518-838">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-839">msRTCSIP-UserDomainList (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8518-840">Este atributo proporciona una lista de todos los dominios de un bosque que hospedan usuarios habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="e8518-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="e8518-841">El valor predeterminado es una lista vacía, que indica que todos los dominios del bosque están habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="e8518-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="e8518-842">Los valores válidos son varias cadenas que representan los nombres de dominio de los dominios individuales.</span><span class="sxs-lookup"><span data-stu-id="e8518-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="e8518-843">Novedades de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8518-844">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="e8518-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="e8518-846">Este atributo determina si el usuario está actualmente habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8518-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="e8518-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="e8518-848">Este atributo de valor múltiple contiene una lista de pares de nombre y valor en el formato &quot;de name = value. &quot; Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="e8518-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="e8518-849">Novedades de Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="e8518-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="e8518-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="e8518-851">Este atributo contiene el nombre distintivo (DN) que apunta a un objeto de Perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e8518-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="e8518-852">Novedades de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8518-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="e8518-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="e8518-854">Este atributo almacena pares de nombre y valor para directivas de usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="e8518-855">Novedades de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8518-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="e8518-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="e8518-857">Este es un atributo de valor múltiple que contiene una lista de nombres completos con binario (DN_WITH_BINARY) que apunta a directivas de usuario globales de diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="e8518-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="e8518-858">El elemento binario indica el tipo de directiva a la que apunta la parte DN.</span><span class="sxs-lookup"><span data-stu-id="e8518-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="e8518-859">Los valores binarios válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8518-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-860">0x00000001: política de reuniones</span><span class="sxs-lookup"><span data-stu-id="e8518-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="e8518-861">0x00000002: Directiva UC</span><span class="sxs-lookup"><span data-stu-id="e8518-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="e8518-862">0x00000005: Directiva de presencia</span><span class="sxs-lookup"><span data-stu-id="e8518-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-863">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="e8518-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="e8518-865">Este es el identificador de grupo de enrutamiento SIP.</span><span class="sxs-lookup"><span data-stu-id="e8518-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="e8518-866">Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e8518-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="e8518-867">Novedades de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8518-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="e8518-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="e8518-869">Este es un atributo de valor múltiple.</span><span class="sxs-lookup"><span data-stu-id="e8518-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="e8518-870">Este atributo se reserva para usarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8518-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8518-871">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="e8518-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="e8518-873">Este atributo de valor único apunta al grupo de servidores o al servidor Standard Edition al que pertenecen los componentes Web.</span><span class="sxs-lookup"><span data-stu-id="e8518-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="e8518-874">Vínculo hacia adelante: <strong>identificador de vínculo 11028</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="e8518-875">El vínculo atrás correspondiente a este atributo de vínculo hacia adelante es <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-876">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="e8518-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="e8518-878">Este atributo es una lista con varios valores de nombres completos.</span><span class="sxs-lookup"><span data-stu-id="e8518-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="e8518-879">Este atributo contiene una lista de todos los servidores web asociados con este grupo.</span><span class="sxs-lookup"><span data-stu-id="e8518-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="e8518-880">Vínculo anterior: <strong>identificador de vínculo 11029</strong></span><span class="sxs-lookup"><span data-stu-id="e8518-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="e8518-881">El vínculo de reenvío correspondiente a este vínculo anterior es <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8518-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8518-882">Novedades de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8518-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-883">msRTCSIP-WMIInstanceId (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="e8518-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8518-884">Novedades de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e8518-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e8518-885">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8518-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="e8518-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="e8518-887">Este atributo de Active Directory existente es utilizado por telefonía para especificar la lista de direcciones TCP/IP alternativas para un teléfono.</span><span class="sxs-lookup"><span data-stu-id="e8518-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="e8518-888">Nuevo en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="e8518-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="e8518-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="e8518-890">Los componentes de voz de Lync Server usan este atributo de Active Directory existente, solo para objetos de contacto, con el fin de enrutar llamadas a los números de acceso de los suscriptores y el operador automático de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="e8518-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="e8518-891">La dirección de desvío de llamadas incondicionales se almacena en este atributo de valor múltiple.</span><span class="sxs-lookup"><span data-stu-id="e8518-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="e8518-892">Esta cuenta se crea para el propósito específico del acceso de operador automático y suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e8518-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="e8518-893">Los administradores no deben modificar los atributos de esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="e8518-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="e8518-894">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e8518-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8518-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e8518-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e8518-896">Este atributo de valor múltiple de Active Directory existente forma parte del esquema de Active Directory base introducido en Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e8518-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="e8518-897">Este atributo contiene las distintas direcciones de X400, X500 y SMTP del correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="e8518-898">En Live Communications Server 2003 y versiones posteriores, el URI del SIP del usuario se agrega a la lista con &quot;la etiqueta&quot; SIP:.</span><span class="sxs-lookup"><span data-stu-id="e8518-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="e8518-899">Las siguientes aplicaciones buscan el URI SIP del usuario desde este atributo:</span><span class="sxs-lookup"><span data-stu-id="e8518-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8518-900">Cliente de mensajería y colaboración 2003 de Microsoft Office Outlook</span><span class="sxs-lookup"><span data-stu-id="e8518-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="e8518-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8518-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8518-902">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e8518-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8518-903">NúmeroDeTeléfono</span><span class="sxs-lookup"><span data-stu-id="e8518-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="e8518-904">Este atributo de Active Directory existente contiene el número de teléfono para el usuario.</span><span class="sxs-lookup"><span data-stu-id="e8518-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="e8518-905">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e8518-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

