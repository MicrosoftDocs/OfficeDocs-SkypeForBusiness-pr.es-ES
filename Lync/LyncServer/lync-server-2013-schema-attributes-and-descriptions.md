---
title: 'Lync Server 2013: atributos de esquema y descripciones'
description: 'Lync Server 2013: atributos de esquema y descripciones.'
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
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557196"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="a7623-103">Atributos y descripciones de esquema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7623-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7623-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a7623-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a7623-105">En esta sección se describen todos los atributos de esquema que usa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7623-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="a7623-106">Para las clases asociadas a los atributos, consulte [atributos de esquema por clase en Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="a7623-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="a7623-107">Para obtener una lista de las clases y atributos que son nuevos en Lync Server 2013, vea [cambios en el esquema en Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="a7623-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="a7623-p102">Los atributos que son pares vinculados se especifican como vínculos hacia delante o hacia atrás. Un atributo que hace referencia a otro objeto es un vínculo hacia delante; el atributo del otro objeto que hace referencia al primer objeto es un vínculo hacia atrás. Los vínculos hacia delante se pueden actualizar, mientras que los vínculos hacia atrás son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a7623-p102">Attributes that are linked pairs are specified as forward links or back links. An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link. Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="a7623-p103">Algunos atributos tienen un valor de máscara de bits. Para estos atributos, cada configuración se representa por un bit, y el valor decimal mostrado representa la posición del bit. Las posiciones de bit comienzan con el bit 0. Por ejemplo, 1 (binario) es el bit 0 definido y 10000 (binario) es el bit 4 definido. Cada bit representa una propiedad. A continuación, se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a7623-p103">Some attributes have a bit-mask value. For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position. Bit positions start with bit 0. For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set. Each bit represents a property. The following are some examples:</span></span>

  - <span data-ttu-id="a7623-117">10000 (binario) tiene un valor decimal de 16 (es decir, se establece el bit 4).</span><span class="sxs-lookup"><span data-stu-id="a7623-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="a7623-118">100000000 (binario) tiene un valor decimal de 256 (es decir, se establece el bit 8).</span><span class="sxs-lookup"><span data-stu-id="a7623-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="a7623-119">1100 (binario) tienen un valor decimal de 12 (es decir, se establecen los bits 2 y 3; se habilitan las propiedades representadas por ambos bits).</span><span class="sxs-lookup"><span data-stu-id="a7623-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="a7623-120">1111000001 (binario) tiene un valor decimal de 961 (es decir, se establecen los bits 0, 6, 7, 8 y 9; se habilitan las propiedades de cada uno de estos bits).</span><span class="sxs-lookup"><span data-stu-id="a7623-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="a7623-121">Atributos de esquema para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7623-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7623-122">Atributo</span><span class="sxs-lookup"><span data-stu-id="a7623-122">Attribute</span></span></th>
<th><span data-ttu-id="a7623-123">Description</span><span class="sxs-lookup"><span data-stu-id="a7623-123">Description</span></span></th>
<th><span data-ttu-id="a7623-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7623-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7623-125">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="a7623-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="a7623-126">Un atributo existente en los servicios de dominio de Active Directory que ahora está asociado con las clases <strong>msRTCSIP-Pool</strong> y <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="a7623-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="a7623-127">Este atributo especifica el nombre de dominio completo (FQDN) de un grupo o servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a7623-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="a7623-128">Un valor válido para cada segmento es 63 caracteres; un valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a7623-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a7623-129">Nuevo en Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-130">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="a7623-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="a7623-p105">Este atributo contiene la representación de cadena del nombre distintivo (DN) del objeto en otro bosque que se corresponde con este objeto. Se usa para la expansión de grupos de distribución y la asistencia automática. Este atributo se define en el esquema predeterminado de Active Directory para Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-p105">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object. This attribute is used for distribution group expansion and auto attendance. This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="a7623-134">Para que no sea necesaria una actualización de AD DS a Windows 2003 R2, la preparación del esquema de Active Directory extiende el esquema de Windows Server 2003 con esta definición de atributos.</span><span class="sxs-lookup"><span data-stu-id="a7623-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="a7623-135">Nuevo en Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-136">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="a7623-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="a7623-137">Este atributo de varios valores contiene la configuración del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="a7623-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="a7623-138">Este atributo se comparte con mensajería unificada de Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="a7623-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="a7623-139">Nuevo en Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a7623-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="a7623-141">Este atributo de varios valores contiene los identificadores de las directivas de retención que se aplican al usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="a7623-142">Las directivas de retención conservan los elementos del buzón del usuario durante toda la retención.</span><span class="sxs-lookup"><span data-stu-id="a7623-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="a7623-143">Este atributo se comparte con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a7623-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="a7623-144">Nuevo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7623-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-145">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="a7623-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="a7623-146">Este atributo almacena información sobre el proveedor de servicios de audioconferencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="a7623-147">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-148">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="a7623-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="a7623-149">Este atributo apunta a la entrada de servicio de confianza del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="a7623-150">Novedad en Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-151">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="a7623-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="a7623-152">Este atributo contiene una lista de aplicaciones hospedadas en el servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a7623-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="a7623-153">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-154">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="a7623-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="a7623-155">Este atributo especifica las opciones del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="a7623-156">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-157">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="a7623-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="a7623-158">Este atributo contiene el idioma principal del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="a7623-159">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-160">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="a7623-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="a7623-161">Este atributo de varios valores contiene los idiomas secundarios del contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="a7623-162">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-163">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="a7623-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="a7623-p108">Este atributo contiene una lista de los servidores de aplicaciones que pertenecen a este grupo de servidores. El vínculo hacia delante correspondiente a este atributo de vínculo hacia atrás es <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-p108">This attribute contains a list of application servers that belong to this pool. The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-166">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-167">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="a7623-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="a7623-168">Este atributo apunta al grupo al que pertenece este servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a7623-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="a7623-169">Es el vínculo hacia delante.</span><span class="sxs-lookup"><span data-stu-id="a7623-169">This is the forward link.</span></span> <span data-ttu-id="a7623-170">El vínculo hacia atrás correspondiente es <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-171">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-172">msRTCSIP-ArchiveDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-173">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-174">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-175">msRTCSIP-ArchiveDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p110">Este atributo especifica el valor predeterminado global dentro del límite del bosque para archivar todas las comunicaciones del usuario. Lo aplica la capa del agente de archivado. El intervalo de valores de este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7623-p110">This attribute specifies the global default within the forest boundary for archiving all user communications. This is enforced by the archiving agent layer. The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-179"><strong>TRUE</strong>: se archivan todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="a7623-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="a7623-180"><strong>FALSE</strong>: no se archivan todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="a7623-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="a7623-181">Este atributo controla, dentro del límite del bosque y de manera global, cómo se archivan las comunicaciones de los usuarios en una red interna.</span><span class="sxs-lookup"><span data-stu-id="a7623-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="a7623-182"><strong>Comportamiento de Live Communications Server 2005 (ahora retirado)</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="a7623-183">El intervalo de valores de este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7623-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-184">0: se archiva el cuerpo del mensaje [bit 0]</span><span class="sxs-lookup"><span data-stu-id="a7623-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="a7623-185">1: no se archiva el cuerpo del mensaje [bit 0]</span><span class="sxs-lookup"><span data-stu-id="a7623-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="a7623-186"><strong>Comportamiento de Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="a7623-187">El intervalo de valores de este atributo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7623-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-188">0: ArchiveFederationDefaultWithoutBody (retirado)</span><span class="sxs-lookup"><span data-stu-id="a7623-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="a7623-189">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="a7623-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="a7623-190">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="a7623-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="a7623-191">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="a7623-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="a7623-192">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="a7623-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a7623-193">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="a7623-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a7623-194">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="a7623-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="a7623-195">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="a7623-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a7623-196">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="a7623-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a7623-197">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="a7623-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="a7623-198">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="a7623-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="a7623-199">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="a7623-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="a7623-200">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="a7623-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="a7623-201">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="a7623-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="a7623-202">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="a7623-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-203">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-204">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-205">msRTCSIP-ArchiveFederationDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-206">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-207">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-208">msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-209">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-210">Obsoleto en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-211">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="a7623-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="a7623-p111">Este atributo es un entero que se usa como un campo de bits para controlar si se archivan las comunicaciones de un usuario. Este control lo aplica la capa del agente de archivado. Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="a7623-p111">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived. This control is enforced by the archiving agent layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a7623-215">El ámbito de este atributo es específico de un único usuario o contacto.</span><span class="sxs-lookup"><span data-stu-id="a7623-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="a7623-216">Los valores válidos (y las posiciones de bits asociadas) en Lync Server son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-217">0: No archivar (ningún bit establecido)</span><span class="sxs-lookup"><span data-stu-id="a7623-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="a7623-218">1: Retirado (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="a7623-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="a7623-219">2: Retirado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="a7623-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="a7623-220">4: Archivar comunicaciones internas (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="a7623-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a7623-221">8: Archivar comunicaciones federadas (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="a7623-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="a7623-222">Los valores válidos anteriormente en Live Communications Server 2005 son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-223">0: Usar el valor predeterminado definido por <strong>msRTCSIP-ArchiveDefault</strong> y <strong>msRTCSIP-ArchiveFederation</strong>, por este orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="a7623-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-224">1: Archivar</span><span class="sxs-lookup"><span data-stu-id="a7623-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="a7623-225">2: No archivar</span><span class="sxs-lookup"><span data-stu-id="a7623-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="a7623-226">3: Archivar sin el cuerpo del mensaje</span><span class="sxs-lookup"><span data-stu-id="a7623-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="a7623-227">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-228">msRTCSIP-ArchivingServerData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-229">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-230">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-231">msRTCSIP-ArchivingServerVersion (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p113">Este atributo define la versión del servicio de archivado. Este atributo es un tipo entero que se incrementa con cada versión del producto oficial. Los valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="a7623-p113">This attribute defines the version of the Archiving service. This attribute is a monotonously increasing integer type that increments with each official product release. The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-235">Sin definir: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a7623-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="a7623-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="a7623-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="a7623-237">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a7623-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="a7623-238">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a7623-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="a7623-239">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a7623-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-240">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-241">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-242">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="a7623-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="a7623-p114">Este atributo especifica el FQDN del servidor back-end del grupo de servidores. Como solamente puede haber un servidor back-end por cada grupo de servidores, este atributo tiene un solo valor.</span><span class="sxs-lookup"><span data-stu-id="a7623-p114">This attribute specifies the FQDN of the Back End Server of the pool. Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="a7623-245">El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a7623-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a7623-246">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-247">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="a7623-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="a7623-248">Este atributo contiene el identificador del grupo de servidores que hospeda el directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a7623-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="a7623-249">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-250">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="a7623-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="a7623-251">Este atributo contiene el identificador de un directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a7623-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="a7623-252">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-253">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="a7623-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="a7623-254">Este atributo contiene el identificador del grupo de servidores al que se va a mover el directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a7623-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="a7623-255">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-256">msRTCSIP-default</span><span class="sxs-lookup"><span data-stu-id="a7623-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="a7623-257">Este atributo booleano define si el uso del teléfono es un uso predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a7623-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="a7623-258">Si este atributo está establecido en <strong>TRUE</strong>, el uso del teléfono es un uso predeterminado y el administrador no puede eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="a7623-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="a7623-259">Si este atributo está establecido en <strong>FALSE</strong>, el uso se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="a7623-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="a7623-260">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-261">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="a7623-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="a7623-262">Este atributo identifica la dirección URL de Communicator Web Access para los usuarios que están fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7623-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="a7623-263">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-264">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="a7623-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="a7623-265">Este atributo identifica la dirección URL de Communicator Web Access para los usuarios que están dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7623-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="a7623-266">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-267">msRTCSIP-DefaultLocationProfileLink (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-268">Este atributo de un solo valor contiene el nombre distintivo (DN) de un objeto de clase de perfil de ubicación asignado a él.</span><span class="sxs-lookup"><span data-stu-id="a7623-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="a7623-269">Vínculo hacia delante: <strong>identificador de vínculo 11036</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="a7623-270">El vínculo hacia atrás correspondiente es <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-271">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-272">msRTCSIP-DefaultPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-273">Este atributo booleano especifica si la directiva es una directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a7623-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="a7623-274">La directiva es una directiva predeterminada cuando está establecida en <strong>TRUE</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-275">Nuevo en Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a7623-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="a7623-276">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-277">msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-278">Este atributo especifica el FQDN del servidor perimetral que ejecuta el servicio perimetral de acceso, si se puede tener acceso a él directamente o del equilibrador de carga de hardware para un grupo de servidores que ejecutan el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="a7623-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="a7623-279">Si a los servidores que ejecutan el servicio perimetral de acceso solo se puede obtener acceso a través de uno o varios directores, este atributo especifica el FQDN y, opcionalmente, el número de puerto del director o del equilibrador de carga de hardware que atiende a un grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="a7623-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="a7623-280">El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a7623-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a7623-281">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-282">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-284">Este atributo representa el número de puerto que se debe usar para conectar con el servidor que ejecuta el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="a7623-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="a7623-285">El valor válido es un entero que especifica el puerto que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="a7623-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="a7623-286">El valor predeterminado es 5061.</span><span class="sxs-lookup"><span data-stu-id="a7623-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="a7623-287">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-288">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-290">Este atributo representa el período de tiempo de espera de suscripción de presencia predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a7623-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="a7623-291">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-292">msRTCSIP-DefRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-293">Este atributo representa el período de tiempo de espera de registro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a7623-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a7623-294">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-296">Este atributo representa el período de tiempo de espera de suscripción de datos móviles predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a7623-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a7623-297">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-298">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="a7623-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="a7623-299">Este atributo se usa en una topología de dominio dividido y contiene un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a7623-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="a7623-300">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-301">msRTCSIP-Description (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-302">Este atributo de cadena UNICODE de un solo valor contiene una descripción sencilla de esta ruta de teléfono o regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="a7623-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="a7623-303">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-304">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-305">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="a7623-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="a7623-306">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-307">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="a7623-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="a7623-308">Este atributo representa un dominio configurado para el registrador.</span><span class="sxs-lookup"><span data-stu-id="a7623-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-309">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="a7623-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="a7623-310">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-311">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-312">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="a7623-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="a7623-313">Este atributo especifica el FQDN del servidor que ejecuta el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="a7623-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="a7623-314">El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a7623-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a7623-315">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-316">msRTCSIP-EnableBestEffortNotify (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p119">Este atributo controla si un servidor genera una solicitud Best Effort NOTIFY (BENOTIFY), o NOTIFY de "mejor esfuerzo", en lugar de una solicitud NOTIFY, en respuesta a una solicitud SUBSCRIBE de un cliente. BENOTIFY es una extensión que mejora el rendimiento para el protocolo de enlace de notificaciones de suscripción mediante la cual el servidor genera solicitudes BENOTIFY en lugar de las solicitudes NOTIFY normales. La ventaja desde el punto de vista del rendimiento consiste en que una solicitud BENOTIFY no requiere una respuesta 200 OK del cliente, a diferencia de la solicitud NOTIFY.</span><span class="sxs-lookup"><span data-stu-id="a7623-p119">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client. BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests. The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="a7623-320">Los valores válidos son <strong>TRUE</strong> o <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a7623-321">Live Communications Server 2003 no admite solicitudes BENOTIFY.</span><span class="sxs-lookup"><span data-stu-id="a7623-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="a7623-322">Para interactuar con las aplicaciones de servidor escritas con la API de servidor de Live Communications Server 2003 que se ejecuta en servidores de Live Communications Server 2005 y de terceros, las solicitudes BENOTIFY se pueden deshabilitar estableciendo su valor en <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a7623-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="a7623-323">Actualmente, BENOTIFY no forma parte del proceso de normalización del SIP del Grupo de trabajo de ingeniería de Internet (IETF).</span><span class="sxs-lookup"><span data-stu-id="a7623-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="a7623-324">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-325">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-326">msRTCSIP-EnableFederation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p121">Este atributo es un modificador global que los administradores de TI usan para configurar si los usuarios pueden comunicarse con usuarios de otras organizaciones. Permite al administrador invalidar el atributo <strong>FederationEnabled</strong> de un usuario concreto. Este atributo puede ser útil para ayudar a proteger la red interna de ataques procedentes de Internet producidos por gusanos o virus, o ataques concretos dirigidos a la compañía.</span><span class="sxs-lookup"><span data-stu-id="a7623-p121">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations. It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute. This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="a7623-330">Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-331">1: Habilitado para la conectividad de mensajería instantánea pública (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="a7623-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="a7623-332">2: Reservado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="a7623-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="a7623-333">4: Reservado (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="a7623-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a7623-334">8: Reservado (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="a7623-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="a7623-335">16: Habilitado para el control remoto de llamadas [Telefonía] (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="a7623-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="a7623-336">64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (posición de bit 6)</span><span class="sxs-lookup"><span data-stu-id="a7623-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="a7623-337">128: UCEnabled (habilitar a los usuarios para las comunicaciones unificadas) (posición de bit 7)</span><span class="sxs-lookup"><span data-stu-id="a7623-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="a7623-338">256: EnabledForEnhancedPresence (habilitar a los usuarios para la conectividad de mensajería instantánea pública) (posición de bit 8)</span><span class="sxs-lookup"><span data-stu-id="a7623-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="a7623-339">512: RemoteCallControlDualMode (posición de bit 9)</span><span class="sxs-lookup"><span data-stu-id="a7623-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-340">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-341">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-342">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="a7623-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="a7623-343">Este atributo indica si los Enterprise Services se cargan en el servidor determinado.</span><span class="sxs-lookup"><span data-stu-id="a7623-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-344">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="a7623-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="a7623-345">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-346">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="a7623-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="a7623-347">Este atributo contiene el código de marcado para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="a7623-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="a7623-348">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-349">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="a7623-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="a7623-p122">Este atributo controla si un usuario está habilitado para la federación. Lo aplica la capa de los Enterprise Services. Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="a7623-p122">This attribute controls whether a single user is enabled for federation. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a7623-353">Los valores válidos son <strong>TRUE</strong> o <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-354">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-355">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="a7623-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="a7623-356">Este atributo es una lista de varios valores que contiene los nombres de dominio de todos los servidores Enterprise Edition asociados a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7623-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="a7623-357">Vínculo hacia atrás: <strong>identificador de vínculo 11023</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="a7623-358">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-359">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-360">msRTCSIP-Gateways (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-361">Este atributo de cadena de varios valores contiene una lista de puertas de enlace y puertos (por puerta de enlace).</span><span class="sxs-lookup"><span data-stu-id="a7623-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="a7623-362">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-363">msRTCSIP-GlobalSettingsData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p123">Este atributo almacena los pares de nombre:valor. El par nombre:valor ya definido corresponde al valor para <strong>permitir la consulta de la información de presencia</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-p123">This attribute stores name:value pairs. The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="a7623-366">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-367">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="a7623-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="a7623-368">Este atributo es un identificador único de un grupo que se usa para agrupar entradas de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="a7623-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="a7623-369">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-370">msRTCSIP-HomeServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-371">Nuevo en Live Communications Server 2003 (no usado).</span><span class="sxs-lookup"><span data-stu-id="a7623-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="a7623-372">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-373">msRTCSIP-HomeServerString (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-374">Nuevo en Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="a7623-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="a7623-375">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-376">msRTCSIP-HomeUsers (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-377">Nuevo en Live Communications Server 2003 (no usado).</span><span class="sxs-lookup"><span data-stu-id="a7623-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="a7623-378">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-379">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="a7623-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="a7623-p124">Este atributo controla si un usuario está habilitado para el acceso de usuarios externos. Lo aplica la capa de los Enterprise Services. Se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="a7623-p124">This attribute controls whether a single user is enabled for outside user access. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a7623-383">Los valores válidos son <strong>TRUE</strong> o <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-384">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-385">msRTCSIP-IsMaster (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-386">Nuevo en Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a7623-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="a7623-387">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-388">msRTCSIP-line</span><span class="sxs-lookup"><span data-stu-id="a7623-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="a7623-389">Este atributo de un solo valor contiene el identificador del dispositivo (el URI del SIP o el URI de TEL? o del teléfono que el usuario controla) que usa Lync para la telefonía.</span><span class="sxs-lookup"><span data-stu-id="a7623-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="a7623-390">Este atributo se marca para la replicación del catálogo global y se indiza.</span><span class="sxs-lookup"><span data-stu-id="a7623-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="a7623-391">Si un usuario se habilita para Telefonía IP empresarial, este atributo almacena la versión normalizada E.164 del número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="a7623-392">Novedad en Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a7623-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-393">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="a7623-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="a7623-p126">Este atributo de un solo valor contiene el URI del SIP del servidor de puerta de enlace CSTA-SIP. Este atributo se marca para la replicación del catálogo global, pero no se indiza.</span><span class="sxs-lookup"><span data-stu-id="a7623-p126">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server. This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="a7623-396">Novedad en Microsoft Office Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a7623-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-397">msRTCSIP-LocalNormalizationData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-398">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-399">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-400">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-401">msRTCSIP-LocalNormalizationLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p127">Este atributo de varios valores contiene una lista de nombres distintivos (DN) de normalización local asociados a este perfil de ubicación. El tipo de este atributo es un binario DN. Existe una relación uno a varios entre el perfil de ubicación y las reglas de normalización locales. El orden de la lista de DN de normalización local se debe mantener en el orden que especifica el administrador. La conservación del orden la mantiene la parte binaria del DN binario, que especifica el índice de orden.</span><span class="sxs-lookup"><span data-stu-id="a7623-p127">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile. The type of this attribute is a DN binary. There is a one-to-many relationship between location profile and local normalization rules. The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator. The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="a7623-407">Vínculo hacia delante: <strong>identificador de vínculo 11034</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="a7623-408">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-409">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-410">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-411">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="a7623-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="a7623-412">Este atributo contiene una lista de opciones para la regla de normalización.</span><span class="sxs-lookup"><span data-stu-id="a7623-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="a7623-413">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-414">msRTCSIP-LocationName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p128">Este atributo de un solo valor contiene un nombre descriptivo para el perfil de ubicación que indica la ubicación que representa este perfil. Dado que puede haber varios perfiles de ubicación, el administrador necesita una forma de distinguir los diferentes perfiles.</span><span class="sxs-lookup"><span data-stu-id="a7623-p128">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents. Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="a7623-417">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-418">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-419">msRTCSIP-locationProfileBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p129">Este atributo de varios valores contiene una lista de nombres distintivos de perfil de ubicación. Este atributo especifica el vínculo hacia atrás a uno o más perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-p129">This multi-valued attribute contains a list of location profile distinguished names. This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="a7623-422">Vínculo hacia atrás: <strong>identificador de vínculo 11035</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="a7623-423">Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-424">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-425">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-426">msRTCSIP-LocationProfileData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-427">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-428">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-429">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-430">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="a7623-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="a7623-431">Este atributo contiene las opciones del perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="a7623-432">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-433">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="a7623-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="a7623-434">Este atributo de varios valores contiene una lista de contactos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="a7623-435">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-436">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="a7623-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="a7623-437">Este atributo de varios valores contiene una lista de perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="a7623-438">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-440">Este atributo representa el número máximo de solicitudes de búsqueda pendientes por servidor.</span><span class="sxs-lookup"><span data-stu-id="a7623-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="a7623-441">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-443">El atributo representa el número máximo de suscripciones por usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="a7623-444">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-446">Este atributo representa el período de tiempo de espera de suscripción máximo.</span><span class="sxs-lookup"><span data-stu-id="a7623-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a7623-447">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-448">msRTCSIP-MaxRegistrationsTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-449">Este atributo representa el período de tiempo de espera de registros máximo.</span><span class="sxs-lookup"><span data-stu-id="a7623-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a7623-450">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-452">Este atributo representa el período de tiempo de espera de suscripciones de datos móviles máximo.</span><span class="sxs-lookup"><span data-stu-id="a7623-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a7623-453">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-454">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="a7623-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="a7623-455">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-456">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-457">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="a7623-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="a7623-p130">Este atributo es un atributo de punto de control de servicio en la clase de equipo que especifica un vínculo hacia atrás a la fábrica de MCU a la que pertenece. Este punto de control de servicio y el atributo se crean para cada MCU de Microsoft. Cada MCU de Microsoft debe buscar el servidor back-end del grupo de servidores al que pertenece para recuperar la configuración en el nivel de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7623-p130">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs. This service control point and attribute is created for every Microsoft MCU. Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="a7623-p131">El valor de este atributo es el nombre distintivo (DN) de la fábrica de MCU. Este es un atributo de un solo valor y está marcado para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="a7623-p131">The value of this attribute is the distinguished name (DN) of the MCU Factory. This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a7623-463">Vínculo hacia delante: <strong>identificador de vínculo 11026</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="a7623-464">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-465">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-466">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="a7623-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="a7623-p132">Este es un atributo reservado de varias cadenas. La configuración almacenada en este atributo se representa como pares nombre=valor. Los pares nombre=valor actualmente definidos son:</span><span class="sxs-lookup"><span data-stu-id="a7623-p132">This is a multi-string reserved attribute. Settings stored in this attribute are represented as name=value pairs. Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-470">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="a7623-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-471">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-472">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="a7623-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="a7623-473">Este es un atributo de un solo valor que contiene el nombre distintivo (DN) de una sola fábrica de MCU asociada a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7623-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="a7623-474">Vínculo hacia delante: <strong>identificador de vínculo 11024</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="a7623-475">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-476">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-477">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="a7623-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="a7623-478">Este atributo es una cadena de un solo valor que especifica el GUID del proveedor de la fábrica de MCU.</span><span class="sxs-lookup"><span data-stu-id="a7623-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="a7623-479">En función del valor de GUID, el proceso de la fábrica de MCU determina si se presta servicio a este tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="a7623-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="a7623-480">Si el valor de GUID es <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, el proceso de factoría de MCU (disponible de forma predeterminada en Lync Server) lo procesará.</span><span class="sxs-lookup"><span data-stu-id="a7623-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="a7623-481">Para cualquier otro valor de GUID, el proceso de la fábrica de MCU no prestará servicio al tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="a7623-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="a7623-482">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-483">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="a7623-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="a7623-p134">Este atributo es una lista de varios valores que contiene nombres distintivos (DN). Este atributo contiene una lista de todos los servidores de MCU del mismo tipo y proveedor asociados a esta fábrica de MCU. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a7623-p134">This attribute is a multi-valued list of distinguished names (DN). This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="a7623-487">Vínculo hacia atrás: identificador de vínculo 11027</span><span class="sxs-lookup"><span data-stu-id="a7623-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="a7623-488">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-489">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-490">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="a7623-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="a7623-491">Este atributo es una cadena de un solo valor que especifica el medio que la MCU puede administrar.</span><span class="sxs-lookup"><span data-stu-id="a7623-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="a7623-492">Los tipos válidos compatibles son:</span><span class="sxs-lookup"><span data-stu-id="a7623-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-493">misma</span><span class="sxs-lookup"><span data-stu-id="a7623-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="a7623-494">audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="a7623-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="a7623-495">chat</span><span class="sxs-lookup"><span data-stu-id="a7623-495">chat</span></span></p></li>
<li><p><span data-ttu-id="a7623-496">conf de teléfono</span><span class="sxs-lookup"><span data-stu-id="a7623-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-497">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-498">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="a7623-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="a7623-p135">Este atributo es una cadena de un solo valor que especifica el nombre de un proveedor de MCU. Todas las MCU de Microsoft especificarán que este atributo sea <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-p135">This attribute is a single-valued string that specifies an MCU vendor’s name. All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-501">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-502">msRTCSIP-MeetingFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p136">Este atributo define opciones de reunión diferentes que están habilitadas globalmente para todos los objetos de usuarios o de contacto. Este atributo es un valor de máscara de bits de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="a7623-p136">This attribute defines different meeting options that are enabled globally for all users or contact objects. This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="a7623-505">Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-506">0: el valor de AllowOrganizeMeetingWithAnonymousParticipants es None (no permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (no se establece ningún bit)</span><span class="sxs-lookup"><span data-stu-id="a7623-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="a7623-507">4: AllowOrganizeMeetingWithAnonymousParticipants es todos (permitir a todos los usuarios invitar a usuarios anónimos a las reuniones) (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="a7623-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a7623-508">8: el valor de AllowOrganizeMeetingWithAnonymousParticipants es UsePerUserSetting (permitir a los usuarios que inviten a usuarios anónimos a las reuniones según la configuración de cada usuario) (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="a7623-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="a7623-509">16: UserPerUserMeetingPolicy (la directiva de reunión se define por usuario) (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="a7623-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-510">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-511">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-512">msRTCSIP-MeetingPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-513">Este atributo especifica el nombre distintivo (DN) de la directiva que el administrador ha asignado a este usuario como un atributo de un solo valor.</span><span class="sxs-lookup"><span data-stu-id="a7623-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="a7623-514">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-515">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-517">Este atributo representa el período de tiempo de espera de suscripción de presencia mínimo.</span><span class="sxs-lookup"><span data-stu-id="a7623-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a7623-518">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-519">msRTCSIP-MinRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-520">Este atributo representa el período de tiempo de espera de registro mínimo.</span><span class="sxs-lookup"><span data-stu-id="a7623-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a7623-521">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-522">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-524">Este atributo representa el período de tiempo de espera de la suscripción de datos móviles mínimo.</span><span class="sxs-lookup"><span data-stu-id="a7623-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="a7623-525">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-526">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-527">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a7623-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="a7623-528">Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a7623-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="a7623-529">Nuevo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7623-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-530">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="a7623-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="a7623-531">Este atributo contiene opciones y marcadores que definen la configuración de movilidad.</span><span class="sxs-lookup"><span data-stu-id="a7623-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="a7623-532">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-533">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="a7623-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="a7623-534">Este atributo contiene el DN de un objeto de directiva de movilidad.</span><span class="sxs-lookup"><span data-stu-id="a7623-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="a7623-535">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-536">msRTCSIP-NumDevicesPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-537">Este atributo representa el número permitido de dispositivos en los que un usuario se puede registrar para las comunicaciones SIP y suscribirse a presencia.</span><span class="sxs-lookup"><span data-stu-id="a7623-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="a7623-538">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-539">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-540">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="a7623-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="a7623-p137">Este atributo especifica las opciones que están habilitadas para el objeto User o Contact. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por un bit. Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="a7623-p137">This attribute specifies the options that are enabled for the user or contact object. This attribute is a bit-mask value of type integer. Each option is represented by a bit. This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a7623-545">Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-546">1: Habilitado para la conectividad de la mensajería instantánea pública (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="a7623-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="a7623-547">2: Reservado (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="a7623-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="a7623-548">4: Reservado (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="a7623-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a7623-549">8: Reservado (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="a7623-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="a7623-550">16: Habilitado para el control remoto de llamadas [Telefonía] (posición de bit 4)</span><span class="sxs-lookup"><span data-stu-id="a7623-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="a7623-551">64: AllowOrganizeMeetingWithAnonymousParticipants (permitir a los usuarios que inviten a usuarios anónimos a las reuniones) (posición de bit 6)</span><span class="sxs-lookup"><span data-stu-id="a7623-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="a7623-552">128: UCEnabled (habilitar a los usuarios para las UC) (posición de bit 7)</span><span class="sxs-lookup"><span data-stu-id="a7623-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="a7623-553">256: EnabledForEnhancedPresence (habilitar a los usuarios para la conectividad de mensajería instantánea pública) (posición de bit 8)</span><span class="sxs-lookup"><span data-stu-id="a7623-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="a7623-554">512: RemoteCallControlDualMode (posición de bit 9)</span><span class="sxs-lookup"><span data-stu-id="a7623-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-555">Nuevo en Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="a7623-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-556">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="a7623-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="a7623-557">Este atributo se usa en topologías de bosque de recursos y bosque central para habilitar el inicio de sesión único cuando el objeto ObjectSID de un usuario de la cuenta de entidad de seguridad de Windows NT Server se copia en este atributo del objeto User o Contact correspondiente en el bosque de recursos o bosque central.</span><span class="sxs-lookup"><span data-stu-id="a7623-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="a7623-558">Communicator Web Access busca un usuario en AD DS con este atributo o con el ObjectSID del usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="a7623-559">Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="a7623-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-560">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="a7623-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="a7623-561">Este atributo es el Nombre de recursos uniforme (URN) del propietario para un contacto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="a7623-562">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-563">msRTCSIP-Pattern (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p139">Este atributo de cadena de un solo valor contiene un modelo que se usa para comparar los números marcados con el formato E.164. Si el número marcado coincide con este modelo, se aplica la traducción al número marcado.</span><span class="sxs-lookup"><span data-stu-id="a7623-p139">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format. If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="a7623-566">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-567">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-568">msRTCSIP-PhoneRouteBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p140">Este atributo de varios valores contiene una lista de nombres distintivos (DN) de ruta de teléfono. Este atributo especifica el vínculo hacia atrás a una o más rutas de teléfono.</span><span class="sxs-lookup"><span data-stu-id="a7623-p140">This multi-valued attribute contains a list of phone route distinguished names (DN). This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="a7623-571">Vínculo hacia atrás: <strong>identificador de vínculo 11033</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="a7623-572">Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-573">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-574">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-575">msRTCSIP-PhoneRouteData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-576">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-577">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-578">msRTCSIP-PhoneRouteName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-579">Este atributo de cadena UNICODE de un solo valor especifica el nombre descriptivo de la ruta de teléfono, de forma que un administrador pueda hacer fácilmente referencia a ella.</span><span class="sxs-lookup"><span data-stu-id="a7623-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="a7623-580">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-581">msRTCSIP-PhoneUsageData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-582">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-583">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-584">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-585">msRTCSIP-PolicyContent (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p141">Este atributo es una cadena Unicode de un solo valor. Este atributo de cadena contiene la definición de la directiva en formato XML. La definición del esquema XML es común en todos los diferentes tipos de directiva, solo la configuración es diferente para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="a7623-p141">This attribute is a single-valued Unicode string. This string attribute contains the policy definition in XML format. The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="a7623-589">Esta es la definición del esquema XML (XSD):</span><span class="sxs-lookup"><span data-stu-id="a7623-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="a7623-590">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-591">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-592">msRTCSIP-PolicyData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-593">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-594">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-595">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-596">msRTCSIP-PolicyType (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p142">Este atributo de cadena Unicode de un solo valor contiene el tipo de directiva. Los tipos de directiva válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-p142">This single-valued Unicode string attribute contains the policy type. Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-599">misma</span><span class="sxs-lookup"><span data-stu-id="a7623-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="a7623-600">telefonía</span><span class="sxs-lookup"><span data-stu-id="a7623-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-601">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-602">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-603">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="a7623-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="a7623-604">Este atributo especifica un vínculo hacia atrás al grupo de servidores al que pertenece un equipo.</span><span class="sxs-lookup"><span data-stu-id="a7623-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="a7623-605">Este atributo se establece independientemente de si el equipo ejecuta la versión Standard Edition o Enterprise Edition de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7623-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="a7623-606">Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="a7623-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="a7623-607">El valor válido es el nombre de dominio del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7623-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="a7623-608">Vínculo hacia delante: <strong>identificador de vínculo 11022</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="a7623-609">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-610">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-611">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="a7623-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="a7623-612">Este es un atributo de varios valores que contiene una lista de los nombres distintivos (DN) de los grupos de servidores a los que está asociada la fábrica de MCU.</span><span class="sxs-lookup"><span data-stu-id="a7623-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="a7623-613">Vínculo hacia atrás: <strong>identificador de vínculo 11025</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="a7623-614">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-615">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-616">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="a7623-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="a7623-617">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-618">Nuevo en Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="a7623-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-619">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="a7623-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="a7623-p144">Este atributo especifica un nombre arbitrario de un grupo de servidores que se muestra en la consola de administración. El administrador puede cambiar este nombre.</span><span class="sxs-lookup"><span data-stu-id="a7623-p144">This attribute specifies an arbitrary name for a pool that is displayed by the management console. This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="a7623-622">El valor válido es una cadena que representa el nombre de un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7623-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="a7623-623">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-624">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="a7623-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="a7623-p145">Este atributo es un valor de cadena de un solo valor. El valor de este atributo, cuando está presente, representa el FQDN del dominio del grupo de servidores si el administrador desea crear un grupo de servidores front-end con un FQDN que no sigue la estructura de dominios de Active Directory en la que se crea el grupo de servidores front-end [por ejemplo, un espacio de nombres SIP separado del espacio de nombres del sistema de nombres de dominio (DNS)].</span><span class="sxs-lookup"><span data-stu-id="a7623-p145">This attribute is a single-valued string value. The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="a7623-p146">Se recomienda asignar el FQDN del dominio del grupo de servidores front-end a la parte del nombre de dominio como el dominio de Active Directory en el que reside el grupo de servidores. Por consiguiente, cuando no haya ningún valor en este atributo, el FQDN del grupo de servidores front-end se establecerá de forma predeterminada en la estructura de nombres de dominio de Active Directory, tal y como indica el atributo <strong>dnsHostName</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-p146">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides. Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="a7623-629">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-630">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="a7623-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="a7623-631">Una lista de varios valores de los nombres de dominio de todos los servidores de Lync Server, Enterprise Edition asociados a un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7623-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="a7623-632">Este atributo de tipo entero define si el grupo de servidores puede usar las características de mensajería instantánea, presencia y reuniones.</span><span class="sxs-lookup"><span data-stu-id="a7623-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="a7623-633">Los tipos de valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="a7623-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-634">No definido: mensajería instantánea y presencia (Live Communications Server 2005 y 2003)</span><span class="sxs-lookup"><span data-stu-id="a7623-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="a7623-635">1: mensajería instantánea y servicio de presencia (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="a7623-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="a7623-636">2: mensajería instantánea y presencia y servicio de reuniones (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="a7623-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-637">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-638">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="a7623-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="a7623-p148">Este atributo especifica si un grupo de servidores ejecuta el servidor Standard Edition o Enterprise Edition. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por un bit.</span><span class="sxs-lookup"><span data-stu-id="a7623-p148">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server. This attribute is a bit-mask value of type integer. Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="a7623-642">Los valores válidos (y las posiciones de bit asociadas) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-643">1: servidor Standard Edition, hospeda usuarios (posición de bit 0)</span><span class="sxs-lookup"><span data-stu-id="a7623-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="a7623-644">2: servidor Enterprise Edition, hospeda usuarios (posición de bit 1)</span><span class="sxs-lookup"><span data-stu-id="a7623-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="a7623-645">4: servidor Standard Edition, hospeda aplicaciones (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="a7623-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="a7623-646">8: servidor Enterprise Edition, hospeda aplicaciones (posición de bit 3)</span><span class="sxs-lookup"><span data-stu-id="a7623-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="a7623-647">Dado que Lync Server no admite grupos que hospeden solo aplicaciones, los únicos valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-648">5: servidor Standard Edition, hospeda usuarios y aplicaciones (posiciones de bit 0 y 2)</span><span class="sxs-lookup"><span data-stu-id="a7623-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="a7623-649">10: servidor Enterprise Edition, hospeda usuarios y aplicaciones (posiciones de bit 1 y 3)</span><span class="sxs-lookup"><span data-stu-id="a7623-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-650">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-651">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="a7623-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="a7623-p149">Este atributo define la versión del grupo de servidores. Es un tipo entero que se incrementa con cada versión de producto principal.</span><span class="sxs-lookup"><span data-stu-id="a7623-p149">This attribute defines the pool version. It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="a7623-654">Los tipos de valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="a7623-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-655">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a7623-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="a7623-656">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="a7623-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="a7623-657">2: Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a7623-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="a7623-658">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a7623-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="a7623-659">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a7623-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="a7623-660">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a7623-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-661">Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="a7623-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-662">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="a7623-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="a7623-663">Este atributo contiene opciones y marcadores que definen la configuración de presencia.</span><span class="sxs-lookup"><span data-stu-id="a7623-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="a7623-664">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-665">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="a7623-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="a7623-666">Este atributo contiene el DN de un objeto de directiva de presencia.</span><span class="sxs-lookup"><span data-stu-id="a7623-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="a7623-667">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-668">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="a7623-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="a7623-p150">Este atributo habilita un usuario o contacto para la mensajería SIP. Se ha agregado a la clase de contacto porque, en la topología de bosque central, los objetos de contacto son los que están habilitados para SIP en lugar de los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-p150">This attribute enables a user or contact for SIP messaging. It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="a7623-671">El valor válido es el DN del servidor Standard Edition o grupo de servidores front-end Enterprise Edition donde se hospeda un usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="a7623-672">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-673">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="a7623-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="a7623-674">Este atributo contiene la dirección SIP de un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="a7623-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-675">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="a7623-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="a7623-676">Este atributo contiene el identificador de dispositivo del dispositivo de línea privada.</span><span class="sxs-lookup"><span data-stu-id="a7623-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="a7623-677">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-678">msRTCSIP-enrutable</span><span class="sxs-lookup"><span data-stu-id="a7623-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="a7623-679">Este atributo es un atributo booleano que se usa para determinar si Lync Server está autorizado a enrutar a este servicio mediante su dirección GRUU.</span><span class="sxs-lookup"><span data-stu-id="a7623-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="a7623-680">Si este valor se establece en <strong>true</strong>, Lync Server tiene autorización para enrutar a este servicio.</span><span class="sxs-lookup"><span data-stu-id="a7623-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="a7623-681">Si este valor se establece en <strong>false</strong>, Lync Server no tiene autorización para enrutar a este servicio.</span><span class="sxs-lookup"><span data-stu-id="a7623-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="a7623-682">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-683">msRTCSIP-RouteUsageAttribute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p152">Este atributo de cadena UNICODE de un solo valor define un atributo que certifica el uso de una ruta de teléfono. La selección de una ruta de teléfono se determina en función de dos elementos: el atributo de uso asignado a la ruta de teléfono y los atributos de uso de directiva permitidos del autor de la llamada. Se selecciona la primera ruta de teléfono con un atributo de uso que coincide con el uso permitido del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7623-p152">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route. Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes. The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="a7623-687">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-688">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-689">msRTCSIP-RouteUsageLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-690">Este atributo de nombre distintivo (DN) de varios valores contiene una lista de nombres distintivos de uso de ruta.</span><span class="sxs-lookup"><span data-stu-id="a7623-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="a7623-691">Vínculo hacia delante: <strong>identificador de vínculo 11032</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="a7623-692">Este atributo es un vínculo hacia delante que se corresponde con el vínculo hacia atrás <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-693">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-694">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="a7623-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="a7623-695">Este atributo contiene el DN que apunta al grupo de servidores por el que debe pasar todo el tráfico SIP enviado a este MCU o servicio de confianza.</span><span class="sxs-lookup"><span data-stu-id="a7623-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="a7623-696">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-697">msRTCSIP-RuleName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-698">Este atributo de cadena UNICODE de un solo valor especifica el nombre descriptivo de la regla de normalización, de forma que un administrador puede hacer fácilmente referencia a ella.</span><span class="sxs-lookup"><span data-stu-id="a7623-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="a7623-699">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-700">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-701">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="a7623-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="a7623-702">Este atributo representa la versión de esquema implementada actualmente en la organización.</span><span class="sxs-lookup"><span data-stu-id="a7623-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-703">msRTCSIP-SearchMaxRequests (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-704">Este atributo limita el número de resultados de búsqueda que se devolverán desde una búsqueda de directorio cuando un usuario busca un contacto mediante Communicator.</span><span class="sxs-lookup"><span data-stu-id="a7623-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="a7623-705">Este atributo invalidará el valor proporcionado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="a7623-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="a7623-706">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-707">msRTCSIP-SearchMaxResults (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-708">Este atributo limita el número de solicitudes de búsqueda devueltas.</span><span class="sxs-lookup"><span data-stu-id="a7623-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="a7623-709">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-710">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="a7623-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="a7623-p154">Este atributo de varios valores es un vínculo hacia atrás que contiene una lista de nombres distintivos (DN). Estos DN apuntan a un grupo de servidores u objeto <strong>TrustedService</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-p154">This multi-valued attribute is a back link that contains a list of distinguished names (DN). These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="a7623-713">Este atributo se corresponde con el vínculo hacia delante <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-714">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-715">msRTCSIP-Serverprotección</span><span class="sxs-lookup"><span data-stu-id="a7623-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="a7623-716">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-717">msRTCSIP-ServerReferenceBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p155">Este atributo de varios valores contiene una lista de nombres distintivos. Estos nombres distintivos son vínculos hacia atrás que hacen referencia a otros objetos de servidor que pueden estar asignados a un perfil de ubicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a7623-p155">This multi-valued attribute contains a list of distinguished names. These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="a7623-720">Vínculo hacia atrás: <strong>identificador de vínculo 11037</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="a7623-721">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="a7623-722">Este atributo de vínculo hacia atrás hace únicamente referencia a los grupos de servidores y a los servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="a7623-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="a7623-723">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-724">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-725">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="a7623-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="a7623-p156">Este atributo define la información de versión del servidor. Este número de versión se aplica a todos los roles del servidor. Es un entero que se incrementa con cada versión del producto oficial.</span><span class="sxs-lookup"><span data-stu-id="a7623-p156">This attribute defines the version information of the server. This version number applies to all server roles. It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="a7623-729">Los valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="a7623-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-730">Sin definir: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a7623-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="a7623-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="a7623-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="a7623-732">                 Live Communications Server 2005 con SP1</span><span class="sxs-lookup"><span data-stu-id="a7623-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="a7623-733">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a7623-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="a7623-734">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a7623-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="a7623-735">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a7623-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="a7623-736">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7623-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-737">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-738">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="a7623-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="a7623-739">Este atributo de un solo valor de tipo entero especifica el tipo de objeto al que apunta <strong>msDS-SourceObjectDN</strong>, de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="a7623-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-740">null | 0x00000001: representa un objeto de usuario de entidad de seguridad de Windows NT Server de un bosque diferente.</span><span class="sxs-lookup"><span data-stu-id="a7623-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="a7623-741">Los siguientes atributos representan un tipo de grupo de un bosque diferente para la expansión del grupo de distribución:</span><span class="sxs-lookup"><span data-stu-id="a7623-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="a7623-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="a7623-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="a7623-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="a7623-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="a7623-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="a7623-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="a7623-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="a7623-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="a7623-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="a7623-747">0x90000000: representa un objeto de acceso de suscriptor o de operador automático del mismo bosque o de un bosque diferente.</span><span class="sxs-lookup"><span data-stu-id="a7623-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="a7623-748">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-749">msRTCSIP-SubscriptionAuthRequired (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-750">Nuevo en Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="a7623-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="a7623-751">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-752">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="a7623-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="a7623-753">Este atributo permite mover un usuario o un objeto de contacto de un grupo de servidores de Lync Server a otro.</span><span class="sxs-lookup"><span data-stu-id="a7623-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="a7623-754">Este atributo se ha agregado a la clase de contacto porque, en la topología de bosque central, los objetos de contacto son los que están habilitados para SIP, y no los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="a7623-755">El valor válido es el DN del servidor Standard Edition o del grupo de servidores front-end de destino al que se va a mover un usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="a7623-756">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-757">msRTCSIP-TargetPhoneNumber (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-758">Este atributo de cadena de un solo valor contiene un modelo o intervalo de números de teléfono para el enrutamiento a las puertas de enlace especificadas en <strong>msRTCSIP-Gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-759">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-760">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="a7623-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="a7623-761">Este atributo almacena pares de nombre-valor para directivas de destino para los usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7623-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="a7623-762">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-763">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="a7623-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="a7623-764">Este atributo almacena el identificador único para un arrendatario.</span><span class="sxs-lookup"><span data-stu-id="a7623-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="a7623-765">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-766">msRTCSIP-Translation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-767">Este atributo se usa en la característica de voz de Lync Server y contiene la cadena de traducción que se va a aplicar en el número marcado si se encuentra una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="a7623-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="a7623-768">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="a7623-769">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-770">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="a7623-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="a7623-771">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-772">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-773">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="a7623-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="a7623-p158">Este atributo es un valor de cadena que contiene el FQDN de la MCU. Es un atributo de un solo valor. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a7623-p158">This attribute is a string value that contains the FQDN of the MCU. This is a single-valued attribute. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a7623-777">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-778">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="a7623-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="a7623-779">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-780">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-781">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="a7623-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="a7623-p159">Este atributo es un valor de cadena que contiene el FQDN del servidor que ejecuta el servidor proxy. Este atributo es de un solo valor. El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a7623-p159">This attribute is a string value that contains the FQDN of the server running Proxy Server. This attribute is single-valued. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a7623-785">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-786">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="a7623-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="a7623-787">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-788">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="a7623-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="a7623-789">Este atributo es un atributo de un solo valor que representa el FQDN de un servidor de confianza.</span><span class="sxs-lookup"><span data-stu-id="a7623-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="a7623-790">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-791">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="a7623-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="a7623-792">Este atributo especifica el número de versión de un servidor de la lista de servidores de confianza.</span><span class="sxs-lookup"><span data-stu-id="a7623-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="a7623-793">Los valores válidos posibles son:</span><span class="sxs-lookup"><span data-stu-id="a7623-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-794">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="a7623-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="a7623-795">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="a7623-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="a7623-796">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a7623-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="a7623-797">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a7623-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="a7623-798">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a7623-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="a7623-799">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7623-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-800">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-801">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="a7623-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="a7623-802">Este atributo define las opciones que están habilitadas para el servicio de confianza.</span><span class="sxs-lookup"><span data-stu-id="a7623-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="a7623-803">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-804">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="a7623-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="a7623-805">Este atributo de varios valores contiene una lista de nombres distintivos (DN) que hacen referencia a un objeto de servicio de confianza, como un servicio de autenticación relé multimedia.</span><span class="sxs-lookup"><span data-stu-id="a7623-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="a7623-806">Un servicio de autenticación de retransmisión multimedia (que se ubica físicamente en el servidor perimetral que ejecuta el servicio de conferencia A/V) debe asociarse con un grupo para admitir escenarios de audio para usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="a7623-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="a7623-807">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-808">UC</span><span class="sxs-lookup"><span data-stu-id="a7623-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-809">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="a7623-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="a7623-810">Este atributo es un entero que define el número de puerto que se usa para conectarse con este servicio GRUU.</span><span class="sxs-lookup"><span data-stu-id="a7623-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="a7623-811">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-812">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="a7623-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="a7623-813">Este atributo es un valor de cadena que define el tipo de servicio GRUU que representa.</span><span class="sxs-lookup"><span data-stu-id="a7623-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="a7623-814">Los tipos de servicios GRUU válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7623-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="a7623-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="a7623-816">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="a7623-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="a7623-817">Servicio de autenticación relé multimedia (MRAS)</span><span class="sxs-lookup"><span data-stu-id="a7623-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="a7623-818">QoSM</span><span class="sxs-lookup"><span data-stu-id="a7623-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="a7623-819">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="a7623-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-820">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-821">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="a7623-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="a7623-822">Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-823">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-824">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="a7623-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="a7623-825">Este atributo es un valor de cadena que contiene el FQDN del IIS que ejecuta los servicios Web de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7623-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="a7623-826">Es un atributo de un solo valor.</span><span class="sxs-lookup"><span data-stu-id="a7623-826">This is a single-valued attribute.</span></span> <span data-ttu-id="a7623-827">El valor válido para cada segmento es 63 caracteres; el valor válido para el FQDN completo es 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a7623-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="a7623-828">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-829">msRTCSIP-UCFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p162">Este atributo define diferentes opciones de UC que están habilitadas globalmente para todos los objetos de usuario o de contacto. Este atributo es un valor de máscara de bits de tipo entero. Cada opción está representada por la presencia de un bit.</span><span class="sxs-lookup"><span data-stu-id="a7623-p162">This attribute defines different UC options that are enabled globally to all user or contact objects. This attribute is a bit-mask value of integer type. Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="a7623-833">El posible valor válido (y la posición de bit asociada) es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7623-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-834">4: UsePerUserUCPolicy (posición de bit 2)</span><span class="sxs-lookup"><span data-stu-id="a7623-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="a7623-835">Cuando se establece este bit, la directiva de UC se define por usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="a7623-836">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-837">msRTCSIP-UCPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-838">Este atributo de un solo valor contiene el nombre distintivo (DN) de la directiva de UC que el administrador ha asignado a este usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="a7623-839">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-840">msRTCSIP-UserDomainList (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="a7623-p163">Este atributo proporciona una lista de todos los dominios de un bosque que hospedan usuarios habilitados para SIP. De manera predeterminada se ofrece una lista vacía, lo que indica que todos los dominios del bosque están habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="a7623-p163">This attribute provides a list of all the domains in a forest that host SIP-enabled users. The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="a7623-843">Como valor válido, se admiten cadenas que representen los nombres de dominio de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="a7623-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="a7623-844">Nuevo en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="a7623-845">Obsoleto en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-846">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="a7623-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="a7623-847">Este atributo determina si el usuario está actualmente habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7623-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-848">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="a7623-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="a7623-849">Este atributo de varios valores contiene una lista de pares nombre-valor en el formato de &quot; name = value. &quot; Este atributo se marca para la replicación del catálogo global.</span><span class="sxs-lookup"><span data-stu-id="a7623-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="a7623-850">Nuevo en Live Communications Server 2005 con SP1.</span><span class="sxs-lookup"><span data-stu-id="a7623-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-851">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="a7623-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="a7623-852">Este atributo contiene el nombre distintivo (DN) que apunta a un objeto de perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a7623-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="a7623-853">Nuevo en Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a7623-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-854">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="a7623-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="a7623-855">Este atributo almacena los pares de nombre-valor para directivas de usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="a7623-856">Nuevo en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7623-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-857">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="a7623-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="a7623-p164">Este es un atributo de varios valores que contiene una lista de nombres distintivos (DN) con binario (DN_WITH_BINARY) que apunta a las directivas de usuario global de tipos diferentes. La parte binaria indica el tipo de directiva a la que apunta la parte de DN.</span><span class="sxs-lookup"><span data-stu-id="a7623-p164">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types. The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="a7623-860">Los tipos de valores binarios válidos son:</span><span class="sxs-lookup"><span data-stu-id="a7623-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-861">0x00000001: Directiva de reunión</span><span class="sxs-lookup"><span data-stu-id="a7623-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="a7623-862">0x00000002: Directiva de UC</span><span class="sxs-lookup"><span data-stu-id="a7623-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="a7623-863">0x00000005: Directiva de presencia</span><span class="sxs-lookup"><span data-stu-id="a7623-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-864">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-865">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a7623-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="a7623-p165">Este es el identificador del grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a7623-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="a7623-868">Nuevo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7623-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-869">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="a7623-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="a7623-p166">Este es un atributo de varios valores. Este atributo se reserva para usarlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a7623-p166">This is a multi-valued attribute. This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="a7623-872">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-873">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="a7623-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="a7623-874">Este atributo de un solo valor apunta al grupo de servidores o al servidor Standard Edition al que pertenecen los componentes web.</span><span class="sxs-lookup"><span data-stu-id="a7623-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="a7623-875">Vínculo hacia delante: <strong>identificador de vínculo 11028</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="a7623-876">El vínculo hacia atrás correspondiente a este atributo de vínculo hacia delante es <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-877">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-878">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="a7623-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="a7623-p167">Este atributo es una lista de varios valores que contiene nombres distintivos. Contiene una lista de todos los servidores web asociados a este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7623-p167">This attribute is a multi-valued list of distinguished names. This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="a7623-881">Vínculo hacia atrás: <strong>identificador de vínculo 11029</strong></span><span class="sxs-lookup"><span data-stu-id="a7623-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="a7623-882">El vínculo hacia delante correspondiente a este vínculo hacia atrás es <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="a7623-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="a7623-883">Nuevo en Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a7623-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-884">msRTCSIP-WMIInstanceId (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="a7623-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a7623-885">Nuevo en Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="a7623-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="a7623-886">Obsoleto en Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="a7623-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="a7623-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="a7623-888">El atributo existente de Active Directory lo usa la telefonía para especificar la lista de direcciones TCP/IP alternativas para teléfonos.</span><span class="sxs-lookup"><span data-stu-id="a7623-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="a7623-889">Nuevo en el sistema operativo Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a7623-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-890">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="a7623-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="a7623-891">Los componentes de voz de Lync Server usan este atributo existente de Active Directory, solo para objetos de contacto, con el fin de enrutar llamadas al operador automático de mensajería unificada y a los números de acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="a7623-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="a7623-892">La dirección de transferencia de llamadas incondicional se almacena en este atributo de varios valores.</span><span class="sxs-lookup"><span data-stu-id="a7623-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="a7623-893">Esta cuenta se crea para el propósito concreto de acceso de suscriptor y operador automático.</span><span class="sxs-lookup"><span data-stu-id="a7623-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="a7623-894">Los administradores no deben modificar los atributos de esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="a7623-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="a7623-895">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a7623-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7623-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a7623-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a7623-897">Este atributo de varios valores existente de Active Directory forma parte del esquema base de Active Directory introducido en Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a7623-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="a7623-898">Este atributo contiene las diferentes direcciones X400, X500 y SMTP del correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="a7623-899">En Live Communications Server 2003 y versiones posteriores, el URI del SIP del usuario se agrega a esta lista mediante la &quot; etiqueta SIP: &quot; .</span><span class="sxs-lookup"><span data-stu-id="a7623-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="a7623-900">Las siguientes aplicaciones buscan el URI del SIP del usuario en este atributo:</span><span class="sxs-lookup"><span data-stu-id="a7623-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7623-901">Cliente de mensajería y colaboración de Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="a7623-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="a7623-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="a7623-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a7623-903">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a7623-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7623-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="a7623-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="a7623-905">Este atributo existente de Active Directory contiene el número de teléfono del usuario.</span><span class="sxs-lookup"><span data-stu-id="a7623-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="a7623-906">Nuevo en el sistema operativo Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a7623-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

