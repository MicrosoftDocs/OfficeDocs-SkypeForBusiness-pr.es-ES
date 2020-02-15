---
title: 'Lync Server 2013: atributos de esquema y descripciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc1d6f5041564c1b865e49ef73a539f3addb75dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="8ef6c-102">Atributos y descripciones de esquema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef6c-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ef6c-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="8ef6c-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="8ef6c-104">En esta sección se describen todos los atributos de esquema que usa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="8ef6c-105">Para las clases asociadas a los atributos, consulte [atributos de esquema por clase en Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="8ef6c-106">Para obtener una lista de las clases y atributos que son nuevos en Lync Server 2013, vea [cambios en el esquema en Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="8ef6c-p102">Los atributos que son pares vinculados se especifican como vínculos hacia delante o hacia atrás. Un atributo que hace referencia a otro objeto es un vínculo hacia delante; el atributo del otro objeto que hace referencia al primer objeto es un vínculo hacia atrás. Los vínculos hacia delante se pueden actualizar, mientras que los vínculos hacia atrás son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p102">Attributes that are linked pairs are specified as forward links or back links. An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link. Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="8ef6c-p103">Algunos atributos tienen un valor de máscara de bits. Para estos atributos, cada configuración se representa por un bit, y el valor decimal mostrado representa la posición del bit. Las posiciones de bit comienzan con el bit 0. Por ejemplo, 1 (binario) es el bit 0 definido y 10000 (binario) es el bit 4 definido. Cada bit representa una propiedad. A continuación, se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p103">Some attributes have a bit-mask value. For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position. Bit positions start with bit 0. For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set. Each bit represents a property. The following are some examples:</span></span>

  - <span data-ttu-id="8ef6c-116">10000 (binario) tiene un valor decimal de 16 (es decir, se establece el bit 4).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="8ef6c-117">100000000 (binario) tiene un valor decimal de 256 (es decir, se establece el bit 8).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="8ef6c-118">1100 (binario) tienen un valor decimal de 12 (es decir, se establecen los bits 2 y 3; se habilitan las propiedades representadas por ambos bits).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="8ef6c-119">1111000001 (binario) tiene un valor decimal de 961 (es decir, se establecen los bits 0, 6, 7, 8 y 9; se habilitan las propiedades de cada uno de estos bits).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="8ef6c-120">Atributos de esquema para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef6c-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ef6c-121">Atributo</span><span class="sxs-lookup"><span data-stu-id="8ef6c-121">Attribute</span></span></th>
<th><span data-ttu-id="8ef6c-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ef6c-122">Description</span></span></th>
<th><span data-ttu-id="8ef6c-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ef6c-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="8ef6c-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-125">Un atributo existente en los servicios de dominio de Active Directory que ahora está asociado con las clases <strong>msRTCSIP-Pool</strong> y <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="8ef6c-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="8ef6c-126">Este atributo especifica el nombre de dominio completo (FQDN) de un grupo o servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="8ef6c-127">Un valor válido para cada segmento es 63 caracteres; un valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-128">Nuevo en Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="8ef6c-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p105">Este atributo contiene la representación de cadena del nombre distintivo (DN) del objeto en otro bosque que se corresponde con este objeto. Se usa para la expansión de grupos de distribución y la asistencia automática. Este atributo se define en el esquema predeterminado de Active Directory para Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p105">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object. This attribute is used for distribution group expansion and auto attendance. This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="8ef6c-133">Para que no sea necesaria una actualización de AD DS a Windows 2003 R2, la preparación del esquema de Active Directory extiende el esquema de Windows Server 2003 con esta definición de atributos.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-134">Nuevo en Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="8ef6c-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-136">Este atributo de varios valores contiene la configuración del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="8ef6c-137">Este atributo se comparte con mensajería unificada de Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-138">Nuevo en Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="8ef6c-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-140">Este atributo de varios valores contiene los identificadores de las directivas de retención que se aplican al usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="8ef6c-141">Las directivas de retención conservan los elementos del buzón del usuario durante toda la retención.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="8ef6c-142">Este atributo se comparte con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-143">Nuevo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="8ef6c-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-145">Este atributo almacena información sobre el proveedor de servicios de audioconferencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-146">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="8ef6c-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-148">Este atributo apunta a la entrada de servicio de confianza del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-149">Novedad en Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="8ef6c-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-151">Este atributo contiene una lista de aplicaciones hospedadas en el servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-152">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="8ef6c-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-154">Este atributo especifica las opciones del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-155">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="8ef6c-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-157">Este atributo contiene el idioma principal del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-158">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="8ef6c-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-160">Este atributo de varios valores contiene los idiomas secundarios del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-161">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="8ef6c-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p108">Este atributo contiene una lista de los servidores de aplicaciones que pertenecen a este grupo de servidores. El vínculo hacia delante correspondiente a este atributo de vínculo hacia atrás es <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p108">This attribute contains a list of application servers that belong to this pool. The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-165">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="8ef6c-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-167">Este atributo apunta al grupo al que pertenece este servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="8ef6c-168">Es el vínculo hacia delante.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-168">This is the forward link.</span></span> <span data-ttu-id="8ef6c-169">El vínculo hacia atrás correspondiente es <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-170">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-171">msRTCSIP-ArchiveDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-172">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-173">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-174">msRTCSIP-ArchiveDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p110">Este atributo especifica el valor predeterminado global dentro del límite del bosque para archivar todas las comunicaciones del usuario. Lo aplica la capa del agente de archivado. El intervalo de valores de este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p110">This attribute specifies the global default within the forest boundary for archiving all user communications. This is enforced by the archiving agent layer. The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-178"><strong>TRUE</strong>: se archivan todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="8ef6c-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-179"><strong>FALSE</strong>: no se archivan todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="8ef6c-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="8ef6c-180">Este atributo controla, dentro del límite del bosque y de manera global, cómo se archivan las comunicaciones de los usuarios en una red interna.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="8ef6c-181"><strong>Comportamiento de Live Communications Server 2005 (ahora retirado)</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="8ef6c-182">El intervalo de valores de este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-183">0: se archiva el cuerpo del mensaje [bit 0]</span><span class="sxs-lookup"><span data-stu-id="8ef6c-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-184">1: no se archiva el cuerpo del mensaje [bit 0]</span><span class="sxs-lookup"><span data-stu-id="8ef6c-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="8ef6c-185"><strong>Comportamiento de Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="8ef6c-186">El intervalo de valores de este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-187">0: ArchiveFederationDefaultWithoutBody (retirado)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="8ef6c-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="8ef6c-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="8ef6c-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="8ef6c-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="8ef6c-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="8ef6c-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="8ef6c-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="8ef6c-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="8ef6c-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="8ef6c-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="8ef6c-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="8ef6c-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="8ef6c-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="8ef6c-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-202">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-203">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-204">msRTCSIP-ArchiveFederationDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-205">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-206">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-207">msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-208">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-209">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="8ef6c-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p111">Este atributo es un entero que se usa como un campo de bits para controlar si se archivan las comunicaciones de un usuario. Este control lo aplica la capa del agente de archivado. Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p111">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived. This control is enforced by the archiving agent layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="8ef6c-214">El ámbito de este atributo es específico de un único usuario o contacto.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="8ef6c-215">Los valores válidos (y las posiciones de bits asociadas) en Lync Server son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-216">0: No archivar (ningún bit establecido)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-217">1: Retirado (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-218">2: Retirado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-219">4: Archivar comunicaciones internas (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-220">8: Archivar comunicaciones federadas (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="8ef6c-221">Los valores válidos anteriormente en Live Communications Server 2005 son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-222">0: Usar el valor predeterminado definido por <strong>msRTCSIP-ArchiveDefault</strong> y <strong>msRTCSIP-ArchiveFederation</strong>, por este orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-223">1: Archivar</span><span class="sxs-lookup"><span data-stu-id="8ef6c-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-224">2: No archivar</span><span class="sxs-lookup"><span data-stu-id="8ef6c-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-225">3: Archivar sin el cuerpo del mensaje</span><span class="sxs-lookup"><span data-stu-id="8ef6c-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-226">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-227">msRTCSIP-ArchivingServerData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-228">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-229">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-230">msRTCSIP-ArchivingServerVersion (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p113">Este atributo define la versión del servicio de archivado. Este atributo es un tipo entero que se incrementa con cada versión del producto oficial. Los valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p113">This attribute defines the version of the Archiving service. This attribute is a monotonously increasing integer type that increments with each official product release. The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-234">Sin definir: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="8ef6c-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="8ef6c-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="8ef6c-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="8ef6c-236">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="8ef6c-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8ef6c-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8ef6c-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-239">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-240">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="8ef6c-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p114">Este atributo especifica el FQDN del servidor back-end del grupo de servidores. Como solamente puede haber un servidor back-end por cada grupo de servidores, este atributo tiene un solo valor.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p114">This attribute specifies the FQDN of the Back End Server of the pool. Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="8ef6c-244">El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-245">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="8ef6c-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-247">Este atributo contiene el identificador del grupo de servidores que hospeda el directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-248">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="8ef6c-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-250">Este atributo contiene el identificador de un directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-251">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="8ef6c-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-253">Este atributo contiene el identificador del grupo de servidores al que se va a mover el directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-254">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-255">msRTCSIP-default</span><span class="sxs-lookup"><span data-stu-id="8ef6c-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-256">Este atributo booleano define si el uso del teléfono es un uso predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="8ef6c-257">Si este atributo está establecido en <strong>TRUE</strong>, el uso del teléfono es un uso predeterminado y el administrador no puede eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="8ef6c-258">Si este atributo está establecido en <strong>FALSE</strong>, el uso se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-259">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="8ef6c-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-261">Este atributo identifica la dirección URL de Communicator Web Access para los usuarios que están fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-262">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="8ef6c-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-264">Este atributo identifica la dirección URL de Communicator Web Access para los usuarios que están dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-265">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-266">msRTCSIP-DefaultLocationProfileLink (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-267">Este atributo de un solo valor contiene el nombre distintivo (DN) de un objeto de clase de perfil de ubicación asignado a él.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="8ef6c-268">Vínculo hacia delante: <strong>identificador de vínculo 11036</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="8ef6c-269">El vínculo hacia atrás correspondiente es <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-270">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-271">msRTCSIP-DefaultPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-272">Este atributo booleano especifica si la directiva es una directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="8ef6c-273">La directiva es una directiva predeterminada cuando está establecida en <strong>TRUE</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-274">Nuevo en Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8ef6c-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="8ef6c-275">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-276">msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-277">Este atributo especifica el FQDN del servidor perimetral que ejecuta el servicio perimetral de acceso, si se puede tener acceso a él directamente o del equilibrador de carga de hardware para un grupo de servidores que ejecutan el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="8ef6c-278">Si a los servidores que ejecutan el servicio perimetral de acceso solo se puede obtener acceso a través de uno o varios directores, este atributo especifica el FQDN y, opcionalmente, el número de puerto del director o del equilibrador de carga de hardware que atiende a un grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="8ef6c-279">El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-280">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-281">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-283">Este atributo representa el número de puerto que se debe usar para conectar con el servidor que ejecuta el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="8ef6c-284">El valor válido es un entero que especifica el puerto que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="8ef6c-285">El valor predeterminado es 5061.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-286">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-287">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-289">Este atributo representa el período de tiempo de espera de suscripción de presencia predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-290">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-291">msRTCSIP-DefRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-292">Este atributo representa el período de tiempo de espera de registro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-293">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-295">Este atributo representa el período de tiempo de espera de suscripción de datos móviles predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-296">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="8ef6c-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-298">Este atributo se usa en una topología de dominio dividido y contiene un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-299">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-300">msRTCSIP-Description (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-301">Este atributo de cadena UNICODE de un solo valor contiene una descripción sencilla de esta ruta de teléfono o regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-302">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-303">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-305">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="8ef6c-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-307">Este atributo representa un dominio configurado para el registrador.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-309">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-310">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="8ef6c-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-312">Este atributo especifica el FQDN del servidor que ejecuta el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="8ef6c-313">El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-314">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-315">msRTCSIP-EnableBestEffortNotify (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p119">Este atributo controla si un servidor genera una solicitud Best Effort NOTIFY (BENOTIFY), o NOTIFY de "mejor esfuerzo", en lugar de una solicitud NOTIFY, en respuesta a una solicitud SUBSCRIBE de un cliente. BENOTIFY es una extensión que mejora el rendimiento para el protocolo de enlace de notificaciones de suscripción mediante la cual el servidor genera solicitudes BENOTIFY en lugar de las solicitudes NOTIFY normales. La ventaja desde el punto de vista del rendimiento consiste en que una solicitud BENOTIFY no requiere una respuesta 200 OK del cliente, a diferencia de la solicitud NOTIFY.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p119">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client. BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests. The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="8ef6c-319">Los valores válidos son <strong>TRUE</strong> o <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8ef6c-320">Live Communications Server 2003 no admite solicitudes BENOTIFY.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="8ef6c-321">Para interactuar con las aplicaciones de servidor escritas con la API de servidor de Live Communications Server 2003 que se ejecuta en servidores de Live Communications Server 2005 y de terceros, las solicitudes BENOTIFY se pueden deshabilitar estableciendo su valor en <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="8ef6c-322">Actualmente, BENOTIFY no forma parte del proceso de normalización del SIP del Grupo de trabajo de ingeniería de Internet (IETF).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="8ef6c-323">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-324">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-325">msRTCSIP-EnableFederation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p121">Este atributo es un modificador global que los administradores de TI usan para configurar si los usuarios pueden comunicarse con usuarios de otras organizaciones. Permite al administrador invalidar el atributo <strong>FederationEnabled</strong> de un usuario concreto. Este atributo puede ser útil para ayudar a proteger la red interna de ataques procedentes de Internet producidos por gusanos o virus, o ataques concretos dirigidos a la compañía.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p121">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations. It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute. This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="8ef6c-329">Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-330">1: Habilitado para la conectividad de mensajería instantánea pública (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-331">2: Reservado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-332">4: Reservado (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-333">8: Reservado (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-334">16: Habilitado para el control remoto de llamadas [Telefonía] (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-335">64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (posición de bit 6)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-336">128: UCEnabled (habilitar a los usuarios para las comunicaciones unificadas) (posición de bit 7)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-337">256: EnabledForEnhancedPresence (habilitar a los usuarios para la conectividad de mensajería instantánea pública) (posición de bit 8)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-338">512: RemoteCallControlDualMode (posición de bit 9)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-339">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-340">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="8ef6c-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-342">Este atributo indica si los Enterprise Services se cargan en el servidor determinado.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-344">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="8ef6c-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-346">Este atributo contiene el código de marcado para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-347">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="8ef6c-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p122">Este atributo controla si un usuario está habilitado para la federación. Lo aplica la capa de los Enterprise Services. Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p122">This attribute controls whether a single user is enabled for federation. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="8ef6c-352">Los valores válidos son <strong>true</strong> o <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-353">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="8ef6c-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-355">Este atributo es una lista de varios valores que contiene los nombres de dominio de todos los servidores Enterprise Edition asociados a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="8ef6c-356">Vínculo hacia atrás: <strong>identificador de vínculo 11023</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="8ef6c-357">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-358">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-359">msRTCSIP-Gateways (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-360">Este atributo de cadena de varios valores contiene una lista de puertas de enlace y puertos (por puerta de enlace).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-361">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-362">msRTCSIP-GlobalSettingsData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p123">Este atributo almacena los pares de nombre:valor. El par nombre:valor ya definido corresponde al valor para <strong>permitir la consulta de la información de presencia</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p123">This attribute stores name:value pairs. The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-365">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="8ef6c-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-367">Este atributo es un identificador único de un grupo que se usa para agrupar entradas de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-368">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-369">msRTCSIP-HomeServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-370">Nuevo en Live Communications Server 2003 (no usado).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="8ef6c-371">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-372">msRTCSIP-HomeServerString (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-373">Nuevo en Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="8ef6c-374">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-375">msRTCSIP-HomeUsers (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-376">Nuevo en Live Communications Server 2003 (no usado).</span><span class="sxs-lookup"><span data-stu-id="8ef6c-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="8ef6c-377">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="8ef6c-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p124">Este atributo controla si un usuario está habilitado para el acceso de usuarios externos. Lo aplica la capa de los Enterprise Services. Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p124">This attribute controls whether a single user is enabled for outside user access. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="8ef6c-382">Los valores válidos son <strong>TRUE</strong> o <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-383">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-384">msRTCSIP-IsMaster (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-385">Nuevo en Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="8ef6c-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="8ef6c-386">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-387">msRTCSIP-line</span><span class="sxs-lookup"><span data-stu-id="8ef6c-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-388">Este atributo de un solo valor contiene el identificador del dispositivo (el URI del SIP o el URI de TEL? o del teléfono que el usuario controla) que usa Lync para la telefonía.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="8ef6c-389">Este atributo se marca para la replicación del catálogo global y se indiza.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="8ef6c-390">Si un usuario se habilita para Telefonía IP empresarial, este atributo almacena la versión normalizada E.164 del número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-391">Novedad en Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="8ef6c-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="8ef6c-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p126">Este atributo de un solo valor contiene el URI del SIP del servidor de puerta de enlace CSTA-SIP. Este atributo se marca para la replicación del catálogo global, pero no se indiza.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p126">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server. This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-395">Novedad en Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="8ef6c-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-396">msRTCSIP-LocalNormalizationData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-397">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-398">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-399">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-400">msRTCSIP-LocalNormalizationLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p127">Este atributo de varios valores contiene una lista de nombres distintivos (DN) de normalización local asociados a este perfil de ubicación. El tipo de este atributo es un binario DN. Existe una relación uno a varios entre el perfil de ubicación y las reglas de normalización locales. El orden de la lista de DN de normalización local se debe mantener en el orden que especifica el administrador. La conservación del orden la mantiene la parte binaria del DN binario, que especifica el índice de orden.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p127">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile. The type of this attribute is a DN binary. There is a one-to-many relationship between location profile and local normalization rules. The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator. The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="8ef6c-406">Vínculo hacia delante: <strong>identificador de vínculo 11034</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="8ef6c-407">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-408">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-409">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="8ef6c-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-411">Este atributo contiene una lista de opciones para la regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-412">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-413">msRTCSIP-LocationName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p128">Este atributo de un solo valor contiene un nombre descriptivo para el perfil de ubicación que indica la ubicación que representa este perfil. Dado que puede haber varios perfiles de ubicación, el administrador necesita una forma de distinguir los diferentes perfiles.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p128">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents. Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-416">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-417">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-418">msRTCSIP-locationProfileBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p129">Este atributo de varios valores contiene una lista de nombres distintivos de perfil de ubicación. Este atributo especifica el vínculo hacia atrás a uno o más perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p129">This multi-valued attribute contains a list of location profile distinguished names. This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="8ef6c-421">Vínculo hacia atrás: <strong>identificador de vínculo 11035</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="8ef6c-422">Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-423">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-424">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-425">msRTCSIP-LocationProfileData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-426">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-427">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-428">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="8ef6c-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-430">Este atributo contiene las opciones del perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-431">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="8ef6c-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-433">Este atributo de varios valores contiene una lista de contactos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-434">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="8ef6c-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-436">Este atributo de varios valores contiene una lista de perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-437">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-439">Este atributo representa el número máximo de solicitudes de búsqueda pendientes por servidor.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-440">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-442">El atributo representa el número máximo de suscripciones por usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-443">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-445">Este atributo representa el período de tiempo de espera de suscripción máximo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-446">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-447">msRTCSIP-MaxRegistrationsTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-448">Este atributo representa el período de tiempo de espera de registros máximo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-449">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-451">Este atributo representa el período de tiempo de espera de suscripciones de datos móviles máximo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-452">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-454">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-455">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="8ef6c-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p130">Este atributo es un atributo de punto de control de servicio en la clase de equipo que especifica un vínculo hacia atrás a la fábrica de MCU a la que pertenece. Este punto de control de servicio y el atributo se crean para cada MCU de Microsoft. Cada MCU de Microsoft debe buscar el servidor back-end del grupo de servidores al que pertenece para recuperar la configuración en el nivel de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p130">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs. This service control point and attribute is created for every Microsoft MCU. Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="8ef6c-p131">El valor de este atributo es el nombre distintivo (DN) de la fábrica de MCU. Este es un atributo de un solo valor y está marcado para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p131">The value of this attribute is the distinguished name (DN) of the MCU Factory. This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="8ef6c-462">Vínculo hacia delante: <strong>identificador de vínculo 11026</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="8ef6c-463">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-464">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p132">Este es un atributo reservado de varias cadenas. La configuración almacenada en este atributo se representa como pares nombre=valor. Los pares nombre=valor actualmente definidos son:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p132">This is a multi-string reserved attribute. Settings stored in this attribute are represented as name=value pairs. Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="8ef6c-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-470">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="8ef6c-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-472">Este es un atributo de un solo valor que contiene el nombre distintivo (DN) de una sola fábrica de MCU asociada a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="8ef6c-473">Vínculo hacia delante: <strong>identificador de vínculo 11024</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="8ef6c-474">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-475">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="8ef6c-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-477">Este atributo es una cadena de un solo valor que especifica el GUID del proveedor de la fábrica de MCU.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="8ef6c-478">En función del valor de GUID, el proceso de la fábrica de MCU determina si se presta servicio a este tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="8ef6c-479">Si el valor de GUID es <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, el proceso de factoría de MCU (disponible de forma predeterminada en Lync Server) lo procesará.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="8ef6c-480">Para cualquier otro valor de GUID, el proceso de la fábrica de MCU no prestará servicio al tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-481">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="8ef6c-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p134">Este atributo es una lista de varios valores que contiene nombres distintivos (DN). Este atributo contiene una lista de todos los servidores de MCU del mismo tipo y proveedor asociados a esta fábrica de MCU. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p134">This attribute is a multi-valued list of distinguished names (DN). This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="8ef6c-486">Vínculo hacia atrás: identificador de vínculo 11027</span><span class="sxs-lookup"><span data-stu-id="8ef6c-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="8ef6c-487">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-488">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="8ef6c-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-490">Este atributo es una cadena de un solo valor que especifica el medio que la MCU puede administrar.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="8ef6c-491">Los tipos válidos compatibles son:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-492">misma</span><span class="sxs-lookup"><span data-stu-id="8ef6c-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-493">audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="8ef6c-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-494">chat</span><span class="sxs-lookup"><span data-stu-id="8ef6c-494">chat</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-495">conf de teléfono</span><span class="sxs-lookup"><span data-stu-id="8ef6c-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-496">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="8ef6c-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p135">Este atributo es una cadena de un solo valor que especifica el nombre de un proveedor de MCU. Todas las MCU de Microsoft especificarán que este atributo sea <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p135">This attribute is a single-valued string that specifies an MCU vendor’s name. All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-500">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-501">msRTCSIP-MeetingFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p136">Este atributo define opciones de reunión diferentes que están habilitadas globalmente para todos los objetos de usuarios o de contacto. Este atributo es un valor de máscara de bits de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p136">This attribute defines different meeting options that are enabled globally for all users or contact objects. This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="8ef6c-504">Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-505">0: el valor de AllowOrganizeMeetingWithAnonymousParticipants es None (no permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (no se establece ningún bit)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-506">4: AllowOrganizeMeetingWithAnonymousParticipants es todos (permitir a todos los usuarios invitar a usuarios anónimos a las reuniones) (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-507">8: el valor de AllowOrganizeMeetingWithAnonymousParticipants es UsePerUserSetting (permitir a los usuarios que inviten a usuarios anónimos a las reuniones según la configuración de cada usuario) (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-508">16: UserPerUserMeetingPolicy (la directiva de reunión se define por usuario) (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-509">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-510">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-511">msRTCSIP-MeetingPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-512">Este atributo especifica el nombre distintivo (DN) de la directiva que el administrador ha asignado a este usuario como un atributo de un solo valor.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-513">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-514">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-516">Este atributo representa el período de tiempo de espera de suscripción de presencia mínimo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-517">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-518">msRTCSIP-MinRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-519">Este atributo representa el período de tiempo de espera de registro mínimo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-520">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-521">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-523">Este atributo representa el período de tiempo de espera de la suscripción de datos móviles mínimo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-524">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-525">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="8ef6c-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-527">Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-528">Nuevo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="8ef6c-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-530">Este atributo contiene opciones y marcadores que definen la configuración de movilidad.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-531">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="8ef6c-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-533">Este atributo contiene el DN de un objeto de directiva de movilidad.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-534">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-535">msRTCSIP-NumDevicesPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-536">Este atributo representa el número permitido de dispositivos en los que un usuario se puede registrar para las comunicaciones SIP y suscribirse a presencia.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-537">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-538">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="8ef6c-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p137">Este atributo especifica las opciones que están habilitadas para el objeto User o Contact. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por un bit. Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p137">This attribute specifies the options that are enabled for the user or contact object. This attribute is a bit-mask value of type integer. Each option is represented by a bit. This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="8ef6c-544">Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-545">1: Habilitado para la conectividad de la mensajería instantánea pública (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-546">2: Reservado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-547">4: Reservado (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-548">8: Reservado (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-549">16: Habilitado para el control remoto de llamadas [Telefonía] (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-550">64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (posición de bit 6)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-551">128: UCEnabled (habilitar a los usuarios para las UC) (posición de bit 7)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-552">256: EnabledForEnhancedPresence (habilitar a los usuarios para la conectividad de mensajería instantánea pública) (posición de bit 8)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-553">512: RemoteCallControlDualMode (posición de bit 9)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-554">Nuevo en Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="8ef6c-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-556">Este atributo se usa en topologías de bosque de recursos y bosque central para habilitar el inicio de sesión único cuando el objeto ObjectSID de un usuario de la cuenta de entidad de seguridad de Windows NT Server se copia en este atributo del objeto User o Contact correspondiente en el bosque de recursos o bosque central.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="8ef6c-557">Communicator Web Access busca un usuario en AD DS con este atributo o con el ObjectSID del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="8ef6c-558">Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="8ef6c-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-560">Este atributo es el Nombre de recursos uniforme (URN) del propietario para un contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-561">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-562">msRTCSIP-Pattern (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p139">Este atributo de cadena de un solo valor contiene un modelo que se usa para comparar los números marcados con el formato E.164. Si el número marcado coincide con este modelo, se aplica la traducción al número marcado.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p139">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format. If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-565">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-566">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-567">msRTCSIP-PhoneRouteBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p140">Este atributo de varios valores contiene una lista de nombres distintivos (DN) de ruta de teléfono. Este atributo especifica el vínculo hacia atrás a una o más rutas de teléfono.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p140">This multi-valued attribute contains a list of phone route distinguished names (DN). This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="8ef6c-570">Vínculo hacia atrás: <strong>identificador de vínculo 11033</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="8ef6c-571">Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-572">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-573">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-574">msRTCSIP-PhoneRouteData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-575">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-576">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-577">msRTCSIP-PhoneRouteName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-578">Este atributo de cadena UNICODE de un solo valor especifica el nombre descriptivo de la ruta de teléfono, de forma que un administrador pueda hacer fácilmente referencia a ella.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-579">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-580">msRTCSIP-PhoneUsageData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-581">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-582">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-583">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-584">msRTCSIP-PolicyContent (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p141">Este atributo es una cadena Unicode de un solo valor. Este atributo de cadena contiene la definición de la directiva en formato XML. La definición del esquema XML es común en todos los diferentes tipos de directiva, solo la configuración es diferente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p141">This attribute is a single-valued Unicode string. This string attribute contains the policy definition in XML format. The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="8ef6c-588">Esta es la definición del esquema XML (XSD):</span><span class="sxs-lookup"><span data-stu-id="8ef6c-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="8ef6c-589">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-590">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-591">msRTCSIP-PolicyData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-592">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-593">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-594">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-595">msRTCSIP-PolicyType (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p142">Este atributo de cadena Unicode de un solo valor contiene el tipo de directiva. Los tipos de directiva válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p142">This single-valued Unicode string attribute contains the policy type. Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-598">misma</span><span class="sxs-lookup"><span data-stu-id="8ef6c-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-599">telefonía</span><span class="sxs-lookup"><span data-stu-id="8ef6c-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-600">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-601">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="8ef6c-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-603">Este atributo especifica un vínculo hacia atrás al grupo de servidores al que pertenece un equipo.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="8ef6c-604">Este atributo se establece independientemente de si el equipo ejecuta la versión Standard Edition o Enterprise Edition de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="8ef6c-605">Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="8ef6c-606">El valor válido es el nombre de dominio del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="8ef6c-607">Vínculo hacia delante: <strong>identificador de vínculo 11022</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="8ef6c-608">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-609">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="8ef6c-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-611">Este es un atributo de varios valores que contiene una lista de los nombres distintivos (DN) de los grupos de servidores a los que está asociada la fábrica de MCU.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="8ef6c-612">Vínculo hacia atrás: <strong>identificador de vínculo 11025</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="8ef6c-613">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-614">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-616">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-617">Nuevo en Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="8ef6c-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p144">Este atributo especifica un nombre arbitrario de un grupo de servidores que se muestra en la consola de administración. El administrador puede cambiar este nombre.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p144">This attribute specifies an arbitrary name for a pool that is displayed by the management console. This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="8ef6c-621">El valor válido es una cadena que representa el nombre de un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-622">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="8ef6c-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p145">Este atributo es un valor de cadena de un solo valor. El valor de este atributo, cuando está presente, representa el FQDN del dominio del grupo de servidores si el administrador desea crear un grupo de servidores front-end con un FQDN que no sigue la estructura de dominios de Active Directory en la que se crea el grupo de servidores front-end [por ejemplo, un espacio de nombres SIP separado del espacio de nombres del sistema de nombres de dominio (DNS)].</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p145">This attribute is a single-valued string value. The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="8ef6c-p146">Se recomienda asignar el FQDN del dominio del grupo de servidores front-end a la parte del nombre de dominio como el dominio de Active Directory en el que reside el grupo de servidores. Por consiguiente, cuando no haya ningún valor en este atributo, el FQDN del grupo de servidores front-end se establecerá de forma predeterminada en la estructura de nombres de dominio de Active Directory, tal y como indica el atributo <strong>dnsHostName</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p146">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides. Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-628">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="8ef6c-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-630">Una lista de varios valores de los nombres de dominio de todos los servidores de Lync Server, Enterprise Edition asociados a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="8ef6c-631">Este atributo de tipo entero define si el grupo de servidores puede usar las características de mensajería instantánea, presencia y reuniones.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="8ef6c-632">Los tipos de valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-633">No definido: mensajería instantánea y presencia (Live Communications Server 2005 y 2003)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-634">1: mensajería instantánea y servicio de presencia (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-635">2: mensajería instantánea y presencia y servicio de reuniones (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-636">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="8ef6c-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p148">Este atributo especifica si un grupo de servidores ejecuta el servidor Standard Edition o Enterprise Edition. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por un bit.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p148">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server. This attribute is a bit-mask value of type integer. Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="8ef6c-641">Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-642">1: servidor Standard Edition, hospeda usuarios (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-643">2: servidor Enterprise Edition, hospeda usuarios (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-644">4: servidor Standard Edition, hospeda aplicaciones (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-645">8: servidor Enterprise Edition, hospeda aplicaciones (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="8ef6c-646">Dado que Lync Server no admite grupos que hospeden solo aplicaciones, los únicos valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-647">5: servidor Standard Edition, hospeda usuarios y aplicaciones (posiciones de bit 0 y 2)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-648">10: servidor Enterprise Edition, hospeda usuarios y aplicaciones (posiciones de bit 1 y 3)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-649">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="8ef6c-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p149">Este atributo define la versión del grupo de servidores. Es un tipo entero que se incrementa con cada versión de producto principal.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p149">This attribute defines the pool version. It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="8ef6c-653">Los tipos de valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="8ef6c-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="8ef6c-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-656">2: Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="8ef6c-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8ef6c-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8ef6c-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8ef6c-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-660">Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="8ef6c-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-662">Este atributo contiene opciones y marcadores que definen la configuración de presencia.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-663">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="8ef6c-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-665">Este atributo contiene el DN de un objeto de directiva de presencia.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-666">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="8ef6c-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p150">Este atributo habilita un usuario o contacto para la mensajería SIP. Se ha agregado a la clase de contacto porque, en la topología de bosque central, los objetos de contacto son los que están habilitados para SIP en lugar de los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p150">This attribute enables a user or contact for SIP messaging. It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="8ef6c-670">El valor válido es el DN del servidor Standard Edition o grupo de servidores front-end Enterprise Edition donde se hospeda un usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-671">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="8ef6c-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-673">Este atributo contiene la dirección SIP de un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="8ef6c-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-675">Este atributo contiene el identificador de dispositivo del dispositivo de línea privada.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-676">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-677">msRTCSIP-enrutable</span><span class="sxs-lookup"><span data-stu-id="8ef6c-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-678">Este atributo es un atributo booleano que se usa para determinar si Lync Server está autorizado a enrutar a este servicio mediante su dirección GRUU.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="8ef6c-679">Si este valor se establece en <strong>true</strong>, Lync Server tiene autorización para enrutar a este servicio.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="8ef6c-680">Si este valor se establece en <strong>false</strong>, Lync Server no tiene autorización para enrutar a este servicio.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-681">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-682">msRTCSIP-RouteUsageAttribute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p152">Este atributo de cadena UNICODE de un solo valor define un atributo que certifica el uso de una ruta de teléfono. La selección de una ruta de teléfono se determina en función de dos elementos: el atributo de uso asignado a la ruta de teléfono y los atributos de uso de directiva permitidos del autor de la llamada. Se selecciona la primera ruta de teléfono con un atributo de uso que coincide con el uso permitido del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p152">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route. Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes. The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-686">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-687">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-688">msRTCSIP-RouteUsageLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-689">Este atributo de nombre distintivo (DN) de varios valores contiene una lista de nombres distintivos de uso de ruta.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="8ef6c-690">Vínculo hacia delante: <strong>identificador de vínculo 11032</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="8ef6c-691">Este atributo es un vínculo hacia delante que se corresponde con el vínculo hacia atrás <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-692">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="8ef6c-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-694">Este atributo contiene el DN que apunta al grupo de servidores por el que debe pasar todo el tráfico SIP enviado a este MCU o servicio de confianza.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-695">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-696">msRTCSIP-RuleName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-697">Este atributo de cadena UNICODE de un solo valor especifica el nombre descriptivo de la regla de normalización, de forma que un administrador puede hacer fácilmente referencia a ella.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-698">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-699">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="8ef6c-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-701">Este atributo representa la versión de esquema implementada actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-702">msRTCSIP-SearchMaxRequests (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-703">Este atributo limita el número de resultados de búsqueda que se devolverán desde una búsqueda de directorio cuando un usuario busca un contacto mediante Communicator.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="8ef6c-704">Este atributo invalidará el valor proporcionado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-705">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-706">msRTCSIP-SearchMaxResults (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-707">Este atributo limita el número de solicitudes de búsqueda devueltas.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-708">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="8ef6c-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p154">Este atributo de varios valores es un vínculo hacia atrás que contiene una lista de nombres distintivos (DN). Estos DN apuntan a un grupo de servidores u objeto <strong>TrustedService</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p154">This multi-valued attribute is a back link that contains a list of distinguished names (DN). These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="8ef6c-712">Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-713">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-714">msRTCSIP-Serverprotección</span><span class="sxs-lookup"><span data-stu-id="8ef6c-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-715">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-716">msRTCSIP-ServerReferenceBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p155">Este atributo de varios valores contiene una lista de nombres distintivos. Estos nombres distintivos son vínculos hacia atrás que hacen referencia a otros objetos de servidor que pueden estar asignados a un perfil de ubicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p155">This multi-valued attribute contains a list of distinguished names. These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="8ef6c-719">Vínculo hacia atrás: <strong>identificador de vínculo 11037</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="8ef6c-720">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="8ef6c-721">Este atributo de vínculo hacia atrás hace únicamente referencia a los grupos de servidores y a los servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-722">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-723">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8ef6c-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p156">Este atributo define la información de versión del servidor. Este número de versión se aplica a todos los roles del servidor. Es un entero que se incrementa con cada versión del producto oficial.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p156">This attribute defines the version information of the server. This version number applies to all server roles. It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="8ef6c-728">Los valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-729">Sin definir: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="8ef6c-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="8ef6c-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="8ef6c-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="8ef6c-731">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="8ef6c-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8ef6c-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8ef6c-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8ef6c-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef6c-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-736">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="8ef6c-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-738">Este atributo de un solo valor de tipo entero especifica el tipo de objeto al que apunta <strong>msDS-SourceObjectDN</strong>, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-739">null | 0x00000001: representa un objeto de usuario de entidad de seguridad de Windows NT Server de un bosque diferente.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-740">Los siguientes atributos representan un tipo de grupo de un bosque diferente para la expansión del grupo de distribución:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="8ef6c-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="8ef6c-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="8ef6c-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="8ef6c-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="8ef6c-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-746">0x90000000: representa un objeto de acceso de suscriptor o de operador automático del mismo bosque o de un bosque diferente.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-747">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-748">msRTCSIP-SubscriptionAuthRequired (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-749">Nuevo en Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="8ef6c-750">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="8ef6c-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-752">Este atributo permite mover un usuario o un objeto de contacto de un grupo de servidores de Lync Server a otro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="8ef6c-753">Este atributo se ha agregado a la clase de contacto porque, en la topología de bosque central, los objetos de contacto son los que están habilitados para SIP, y no los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="8ef6c-754">El valor válido es el DN del servidor Standard Edition o del grupo de servidores front-end de destino al que se va a mover un usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-755">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-756">msRTCSIP-TargetPhoneNumber (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-757">Este atributo de cadena de un solo valor contiene un modelo o intervalo de números de teléfono para el enrutamiento a las puertas de enlace especificadas en <strong>msRTCSIP-Gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-758">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="8ef6c-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-760">Este atributo almacena pares de nombre-valor para directivas de destino para los usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-761">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="8ef6c-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-763">Este atributo almacena el identificador único para un arrendatario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-764">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-765">msRTCSIP-Translation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-766">Este atributo se usa en la característica de voz de Lync Server y contiene la cadena de traducción que se va a aplicar en el número marcado si se encuentra una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-767">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="8ef6c-768">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-770">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-771">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="8ef6c-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p158">Este atributo es un valor de cadena que contiene el FQDN de la MCU. Es un atributo de un solo valor. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p158">This attribute is a string value that contains the FQDN of the MCU. This is a single-valued attribute. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-776">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-778">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-779">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="8ef6c-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p159">Este atributo es un valor de cadena que contiene el FQDN del servidor que ejecuta el servidor proxy. Este atributo es de un solo valor. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p159">This attribute is a string value that contains the FQDN of the server running Proxy Server. This attribute is single-valued. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-784">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-786">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="8ef6c-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-788">Este atributo es un atributo de un solo valor que representa el FQDN de un servidor de confianza.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-789">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="8ef6c-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-791">Este atributo especifica el número de versión de un servidor de la lista de servidores de confianza.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="8ef6c-792">Los valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="8ef6c-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="8ef6c-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8ef6c-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8ef6c-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8ef6c-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef6c-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-799">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="8ef6c-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-801">Este atributo define las opciones que están habilitadas para el servicio de confianza.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-802">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="8ef6c-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-804">Este atributo de varios valores contiene una lista de nombres distintivos (DN) que hacen referencia a un objeto de servicio de confianza, como un servicio de autenticación relé multimedia.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="8ef6c-805">Un servicio de autenticación de retransmisión multimedia (que se ubica físicamente en el servidor perimetral que ejecuta el servicio de conferencia A/V) debe asociarse con un grupo para admitir escenarios de audio para usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="8ef6c-806">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-807">UC</span><span class="sxs-lookup"><span data-stu-id="8ef6c-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="8ef6c-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-809">Este atributo es un entero que define el número de puerto que se usa para conectarse con este servicio GRUU.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-810">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="8ef6c-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-812">Este atributo es un valor de cadena que define el tipo de servicio GRUU que representa.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="8ef6c-813">Los tipos de servicios GRUU válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="8ef6c-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-815">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="8ef6c-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-816">Servicio de autenticación relé multimedia (MRAS)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="8ef6c-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="8ef6c-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-819">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-821">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-822">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="8ef6c-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-824">Este atributo es un valor de cadena que contiene el FQDN del IIS que ejecuta los servicios Web de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="8ef6c-825">Es un atributo de un solo valor.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-825">This is a single-valued attribute.</span></span> <span data-ttu-id="8ef6c-826">El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-827">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-828">msRTCSIP-UCFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p162">Este atributo define diferentes opciones de UC que están habilitadas globalmente para todos los objetos de usuario o de contacto. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por la presencia de un bit.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p162">This attribute defines different UC options that are enabled globally to all user or contact objects. This attribute is a bit-mask value of integer type. Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="8ef6c-832">El posible valor válido (y la posición de bit asociada) es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-833">4: UsePerUserUCPolicy (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="8ef6c-834">Cuando se establece este bit, la directiva de UC se define por usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-835">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-836">msRTCSIP-UCPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-837">Este atributo de un solo valor contiene el nombre distintivo (DN) de la directiva de UC que el administrador ha asignado a este usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-838">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-839">msRTCSIP-UserDomainList (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p163">Este atributo proporciona una lista de todos los dominios de un bosque que hospedan usuarios habilitados para SIP. De manera predeterminada se ofrece una lista vacía, lo que indica que todos los dominios del bosque están habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p163">This attribute provides a list of all the domains in a forest that host SIP-enabled users. The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="8ef6c-842">Como valor válido, se admiten cadenas que representen los nombres de dominio de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-843">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="8ef6c-844">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="8ef6c-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-846">Este atributo determina si el usuario está actualmente habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="8ef6c-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-848">Este atributo de varios valores contiene una lista de pares nombre-valor en el formato de &quot;name = value. &quot; Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-849">Nuevo en Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="8ef6c-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-851">Este atributo contiene el nombre distintivo (DN) que apunta a un objeto de perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-852">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="8ef6c-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-854">Este atributo almacena los pares de nombre-valor para directivas de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-855">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="8ef6c-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p164">Este es un atributo de varios valores que contiene una lista de nombres distintivos (DN) con binario (DN_WITH_BINARY) que apunta a las directivas de usuario global de tipos diferentes. La parte binaria indica el tipo de directiva a la que apunta la parte de DN.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p164">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types. The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="8ef6c-859">Los tipos de valores binarios válidos son:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-860">0x00000001: Directiva de reunión</span><span class="sxs-lookup"><span data-stu-id="8ef6c-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-861">0x00000002: Directiva de UC</span><span class="sxs-lookup"><span data-stu-id="8ef6c-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-862">0x00000005: Directiva de presencia</span><span class="sxs-lookup"><span data-stu-id="8ef6c-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-863">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="8ef6c-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p165">Este es el identificador del grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-867">Nuevo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="8ef6c-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p166">Este es un atributo de varios valores. Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p166">This is a multi-valued attribute. This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-871">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="8ef6c-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-873">Este atributo de un solo valor apunta al grupo de servidores o al servidor Standard Edition al que pertenecen los componentes web.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="8ef6c-874">Vínculo hacia delante: <strong>identificador de vínculo 11028</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="8ef6c-875">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-876">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="8ef6c-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-p167">Este atributo es una lista de varios valores que contiene nombres distintivos. Contiene una lista de todos los servidores web asociados a este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-p167">This attribute is a multi-valued list of distinguished names. This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="8ef6c-880">Vínculo hacia atrás: <strong>identificador de vínculo 11029</strong></span><span class="sxs-lookup"><span data-stu-id="8ef6c-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="8ef6c-881">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-882">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-883">msRTCSIP-WMIInstanceId (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="8ef6c-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8ef6c-884">Nuevo en Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="8ef6c-885">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="8ef6c-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-887">El atributo existente de Active Directory lo usa la telefonía para especificar la lista de direcciones TCP/IP alternativas para teléfonos.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-888">Nuevo en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="8ef6c-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-890">Los componentes de voz de Lync Server usan este atributo existente de Active Directory, solo para objetos de contacto, con el fin de enrutar llamadas al operador automático de mensajería unificada y a los números de acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="8ef6c-891">La dirección de transferencia de llamadas incondicional se almacena en este atributo de varios valores.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="8ef6c-892">Esta cuenta se crea para el propósito concreto de acceso de suscriptor y operador automático.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="8ef6c-893">Los administradores no deben modificar los atributos de esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-894">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef6c-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8ef6c-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-896">Este atributo de varios valores existente de Active Directory forma parte del esquema base de Active Directory introducido en Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="8ef6c-897">Este atributo contiene las diferentes direcciones X400, X500 y SMTP del correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="8ef6c-898">En Live Communications Server 2003 y versiones posteriores, el URI del SIP del usuario se agrega a esta lista mediante &quot;la etiqueta&quot; SIP:.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="8ef6c-899">Las siguientes aplicaciones buscan el URI del SIP del usuario en este atributo:</span><span class="sxs-lookup"><span data-stu-id="8ef6c-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ef6c-900">Cliente de mensajería y colaboración de Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="8ef6c-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="8ef6c-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="8ef6c-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8ef6c-902">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef6c-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="8ef6c-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-904">Este atributo existente de Active Directory contiene el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="8ef6c-905">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="8ef6c-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

