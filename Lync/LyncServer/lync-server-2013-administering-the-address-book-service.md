---
title: 'Lync Server 2013: administración del servicio de libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ea7a68d77acd7bbaf3de43fce38c0e85c02dad4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="52c53-102">Administración del servicio de libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52c53-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52c53-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="52c53-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="52c53-104">Como parte de la implementación de Lync Server, Enterprise Edition o Standard Edition Server, el servicio de libreta de direcciones está instalado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="52c53-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="52c53-105">La base de datos usada por el servicio de libreta de direcciones – RTCab – se crea en SQL Server (para Enterprise Edition, que es el servidor back-end de SQL Server; para el servidor Standard Edition, el servidor SQL Server).</span><span class="sxs-lookup"><span data-stu-id="52c53-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52c53-106">Para obtener información acerca del uso del editor <STRONG>ADSI</STRONG> para editar atributos de objeto de servicios de dominio de Active Directory, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330427">edición de ADSI</A>.</span><span class="sxs-lookup"><span data-stu-id="52c53-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="52c53-107">Para obtener información sobre una herramienta del kit de recursos específica para el servicio de libreta de direcciones, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330429">las herramientas del kit de recursos de Microsoft Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="52c53-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="52c53-108">Normalización del número de teléfono del servidor de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="52c53-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="52c53-109">Lync Server requiere números de teléfono estándar RFC 3966/E. 164.</span><span class="sxs-lookup"><span data-stu-id="52c53-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="52c53-110">Para usar números de teléfono que no están estructurados o que tienen un formato incoherente, Lync Server se basa en el servidor de la libreta de direcciones para preprocesar los números de teléfono antes de que se entreguen a las reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="52c53-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="52c53-111">Cuando se usa un número de teléfono desde la libreta de direcciones y se aplica la regla de normalización, los clientes, como Lync Phone Edition y Lync Mobile, pueden usar estos números normalizados.</span><span class="sxs-lookup"><span data-stu-id="52c53-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="52c53-p104">Las reglas de normalización que se usaron en versiones anteriores no funcionen debidamente si no se realizan algunos ajustes. Dado que se quitan los espacios en blanco y los caracteres no obligatorios que preceden a las reglas de normalización, si la expresión regex busca específicamente un guion u otro carácter que se quitó, es posible que la regla de normalización produzca un error. Debe comprobar las reglas de normalización para asegurarse de que no van a buscar estos caracteres que no son obligatorios o de que la regla pueda provocar un error pero continuar en caso de que el carácter no esté presente en el lugar donde la regla prevé que va a estar.</span><span class="sxs-lookup"><span data-stu-id="52c53-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="52c53-115">Replicador de usuarios y servidor de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="52c53-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="52c53-116">El servidor de libreta de direcciones usa datos que aporta el Replicador de usuarios para actualizar la información que obtiene inicialmente de la lista global de direcciones (LDG).</span><span class="sxs-lookup"><span data-stu-id="52c53-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="52c53-117">El replicador de usuarios escribe los atributos de servicios de dominio de Active Directory para cada usuario, contacto y grupo en la tabla AbUserEntry de la base de datos y el servidor de la libreta de direcciones sincroniza los datos de usuario de la base de datos en archivos del almacén de archivos del servidor de la libreta de direcciones y en la base de datos de la libreta de direcciones RTCab.</span><span class="sxs-lookup"><span data-stu-id="52c53-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="52c53-118">En el esquema de la tabla AbUserEntry se usan dos columnas, **UserGuid** y **UserData**.</span><span class="sxs-lookup"><span data-stu-id="52c53-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="52c53-119">**UserGuid** es la columna de índice y contiene el GUID de 16 bytes del objeto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52c53-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="52c53-120">**UserData** es una columna de imagen que contiene todos los atributos de servicios de dominio de Active Directory mencionados anteriormente para ese contacto.</span><span class="sxs-lookup"><span data-stu-id="52c53-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="52c53-121">El replicador de usuarios determina qué atributos de Active Directory se deben escribir mediante la lectura de una tabla de configuración ubicada en la misma instancia basada en SQL Server que la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="52c53-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="52c53-122">La tabla ABAttribute contiene tres columnas, **ID**, **Name**, **Flags**y **enable**.</span><span class="sxs-lookup"><span data-stu-id="52c53-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="52c53-123">La tabla se crea durante la configuración de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52c53-123">The table is created during database setup.</span></span> <span data-ttu-id="52c53-124">Si la tabla ABAttribute está vacía, el replicador de usuarios omite su lógica de procesamiento de la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="52c53-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="52c53-125">Los atributos del servidor de libreta de direcciones son dinámicos y se recuperan de la tabla ABAttribute, que inicialmente escribe el servidor de la libreta de direcciones cuando se activa el servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="52c53-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="52c53-126">La activación del servidor de la libreta de direcciones rellena la tabla ABAttribute con los valores que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="52c53-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52c53-127">ID</span><span class="sxs-lookup"><span data-stu-id="52c53-127">ID</span></span></th>
<th><span data-ttu-id="52c53-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="52c53-128">Name</span></span></th>
<th><span data-ttu-id="52c53-129">Flags</span><span class="sxs-lookup"><span data-stu-id="52c53-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52c53-130">1</span><span class="sxs-lookup"><span data-stu-id="52c53-130">1</span></span></p></td>
<td><p><span data-ttu-id="52c53-131">givenName</span><span class="sxs-lookup"><span data-stu-id="52c53-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="52c53-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="52c53-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-133">segundo</span><span class="sxs-lookup"><span data-stu-id="52c53-133">2</span></span></p></td>
<td><p><span data-ttu-id="52c53-134">Utilidad</span><span class="sxs-lookup"><span data-stu-id="52c53-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="52c53-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="52c53-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-136">3</span><span class="sxs-lookup"><span data-stu-id="52c53-136">3</span></span></p></td>
<td><p><span data-ttu-id="52c53-137">displayName</span><span class="sxs-lookup"><span data-stu-id="52c53-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="52c53-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="52c53-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-139">4 </span><span class="sxs-lookup"><span data-stu-id="52c53-139">4</span></span></p></td>
<td><p><span data-ttu-id="52c53-140">Título</span><span class="sxs-lookup"><span data-stu-id="52c53-140">Title</span></span></p></td>
<td><p><span data-ttu-id="52c53-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="52c53-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-142">5 </span><span class="sxs-lookup"><span data-stu-id="52c53-142">5</span></span></p></td>
<td><p><span data-ttu-id="52c53-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="52c53-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="52c53-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="52c53-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-145">6 </span><span class="sxs-lookup"><span data-stu-id="52c53-145">6</span></span></p></td>
<td><p><span data-ttu-id="52c53-146">Company</span><span class="sxs-lookup"><span data-stu-id="52c53-146">Company</span></span></p></td>
<td><p><span data-ttu-id="52c53-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="52c53-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-148">7 </span><span class="sxs-lookup"><span data-stu-id="52c53-148">7</span></span></p></td>
<td><p><span data-ttu-id="52c53-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="52c53-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="52c53-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="52c53-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-151">8 </span><span class="sxs-lookup"><span data-stu-id="52c53-151">8</span></span></p></td>
<td><p><span data-ttu-id="52c53-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="52c53-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="52c53-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="52c53-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-154">9 </span><span class="sxs-lookup"><span data-stu-id="52c53-154">9</span></span></p></td>
<td><p><span data-ttu-id="52c53-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="52c53-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="52c53-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="52c53-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-157">10 </span><span class="sxs-lookup"><span data-stu-id="52c53-157">10</span></span></p></td>
<td><p><span data-ttu-id="52c53-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="52c53-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="52c53-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="52c53-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-160">11 </span><span class="sxs-lookup"><span data-stu-id="52c53-160">11</span></span></p></td>
<td><p><span data-ttu-id="52c53-161">Mobile</span><span class="sxs-lookup"><span data-stu-id="52c53-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="52c53-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="52c53-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-163">12</span><span class="sxs-lookup"><span data-stu-id="52c53-163">12</span></span></p></td>
<td><p><span data-ttu-id="52c53-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="52c53-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="52c53-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="52c53-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-166">apartado</span><span class="sxs-lookup"><span data-stu-id="52c53-166">13</span></span></p></td>
<td><p><span data-ttu-id="52c53-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="52c53-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="52c53-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="52c53-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-169">14 </span><span class="sxs-lookup"><span data-stu-id="52c53-169">14</span></span></p></td>
<td><p><span data-ttu-id="52c53-170">Correo</span><span class="sxs-lookup"><span data-stu-id="52c53-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="52c53-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="52c53-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-172">15 </span><span class="sxs-lookup"><span data-stu-id="52c53-172">15</span></span></p></td>
<td><p><span data-ttu-id="52c53-173">groupType</span><span class="sxs-lookup"><span data-stu-id="52c53-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="52c53-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="52c53-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-175">16 </span><span class="sxs-lookup"><span data-stu-id="52c53-175">16</span></span></p></td>
<td><p><span data-ttu-id="52c53-176">Departamento</span><span class="sxs-lookup"><span data-stu-id="52c53-176">Department</span></span></p></td>
<td><p><span data-ttu-id="52c53-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="52c53-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-178">17 </span><span class="sxs-lookup"><span data-stu-id="52c53-178">17</span></span></p></td>
<td><p><span data-ttu-id="52c53-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="52c53-179">Description</span></span></p></td>
<td><p><span data-ttu-id="52c53-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="52c53-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-181">18 </span><span class="sxs-lookup"><span data-stu-id="52c53-181">18</span></span></p></td>
<td><p><span data-ttu-id="52c53-182">Manager</span><span class="sxs-lookup"><span data-stu-id="52c53-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="52c53-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="52c53-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-184">18</span><span class="sxs-lookup"><span data-stu-id="52c53-184">19</span></span></p></td>
<td><p><span data-ttu-id="52c53-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="52c53-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="52c53-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="52c53-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-187">20</span><span class="sxs-lookup"><span data-stu-id="52c53-187">20</span></span></p></td>
<td><p><span data-ttu-id="52c53-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="52c53-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="52c53-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="52c53-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-190">99</span><span class="sxs-lookup"><span data-stu-id="52c53-190">99</span></span></p></td>
<td><p><span data-ttu-id="52c53-191">entryID</span><span class="sxs-lookup"><span data-stu-id="52c53-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="52c53-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="52c53-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52c53-193">Los números de la columna **ID** deben ser únicos y nunca se deben volver a usar.</span><span class="sxs-lookup"><span data-stu-id="52c53-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="52c53-194">Además, mantener los valores de ID en 256 ahorra espacio en los archivos de salida escritos por el servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="52c53-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="52c53-195">Sin embargo, el valor de ID máximo es 65535.</span><span class="sxs-lookup"><span data-stu-id="52c53-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="52c53-196">La columna **nombre** corresponde al nombre de atributo de Active Directory que el replicador de usuarios debe colocar en la tabla AbUserEntry para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="52c53-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="52c53-197">El valor de la columna **Flags** se usa para definir el tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="52c53-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="52c53-198">El replicador de usuarios reconoce los siguientes tipos de atributos del servidor de la libreta de direcciones, indicados por el byte bajo del valor de la columna **indicadores** .</span><span class="sxs-lookup"><span data-stu-id="52c53-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52c53-199">Atributo</span><span class="sxs-lookup"><span data-stu-id="52c53-199">Attribute</span></span></th>
<th><span data-ttu-id="52c53-200">Descripción</span><span class="sxs-lookup"><span data-stu-id="52c53-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52c53-201">0x0</span><span class="sxs-lookup"><span data-stu-id="52c53-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="52c53-p108">Un atributo de cadena. El Replicador de usuarios convierte este tipo a UTF-8 antes de almacenarlo en la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="52c53-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-204">0x1</span><span class="sxs-lookup"><span data-stu-id="52c53-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="52c53-p109">Un atributo binario. El Replicador de usuarios lo almacena en el objeto binario grande sin conversión alguna.</span><span class="sxs-lookup"><span data-stu-id="52c53-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-207">0x2</span><span class="sxs-lookup"><span data-stu-id="52c53-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="52c53-208">Un atributo de cadena, pero se incluye solo si el valor del atributo &quot;empieza por&quot;Tel:.</span><span class="sxs-lookup"><span data-stu-id="52c53-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="52c53-209">Es principalmente para atributos de cadena con varios valores, específicamente <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="52c53-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="52c53-210">En este caso, el servidor de libreta de direcciones sólo <strong></strong> está interesado en las entradas &quot;de proxyAddresses&quot;que comienzan por Tel:.</span><span class="sxs-lookup"><span data-stu-id="52c53-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="52c53-211">Por lo tanto, para ahorrar espacio, el replicador de usuarios solo almacena las entradas que &quot;comienzan por&quot;Tel:.</span><span class="sxs-lookup"><span data-stu-id="52c53-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-212">0X3</span><span class="sxs-lookup"><span data-stu-id="52c53-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="52c53-p111">Un atributo de cadena booleano, que si es TRUE hace que el Replicador de usuarios no incluya este contacto en la tabla AbUserEntry. Si es FALSE, hace que el Replicador de usuarios incluya los atributos de este contacto en la tabla AbUserEntry, pero no el atributo particular con este indicador. Este es otro tipo de caso especial que es básicamente para el atributo <strong>msExchHideFromAddressLists</strong>.</span><span class="sxs-lookup"><span data-stu-id="52c53-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-216">0x4</span><span class="sxs-lookup"><span data-stu-id="52c53-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="52c53-217">Un atributo de cadena, pero se incluye solo si el valor del atributo &quot;empieza por&quot; SMTP: e &quot; @ &quot; incluye el símbolo.</span><span class="sxs-lookup"><span data-stu-id="52c53-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-218">0X5</span><span class="sxs-lookup"><span data-stu-id="52c53-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="52c53-219">Un atributo de cadena, pero se incluye solo si el valor del atributo comienza &quot;por Tel&quot; : &quot;o SMTP&quot; : e incluye &quot; @ &quot; el símbolo.</span><span class="sxs-lookup"><span data-stu-id="52c53-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-220">0x100</span><span class="sxs-lookup"><span data-stu-id="52c53-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="52c53-221">Si se ha establecido, es un atributo de varios valores que pueden aparecer más de una vez para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="52c53-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-222">0x400</span><span class="sxs-lookup"><span data-stu-id="52c53-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="52c53-p112">Si se ha establecido, identifica el atributo del nombre de la cuenta de usuario de correo electrónico para un contacto. El servidor de libreta de direcciones usa este indicador para identificar el valor de atributo que se va a mostrar en la entrada de registro de eventos de normalización del teléfono.</span><span class="sxs-lookup"><span data-stu-id="52c53-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-225">0x800</span><span class="sxs-lookup"><span data-stu-id="52c53-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="52c53-p113">Si se ha establecido, identifica un atributo necesario para un contacto. El servidor de libreta de direcciones incluye un usuario en la tabla AbUserEntry únicamente si existe un valor para este atributo en Active Directory. Si hay más de un atributo obligatorio, solamente se requerirá uno de ellos para tener un valor que incluya al usuario en la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="52c53-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="52c53-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="52c53-230">Si se ha establecido, el servidor de libreta de direcciones siempre normaliza el valor de este atributo.</span><span class="sxs-lookup"><span data-stu-id="52c53-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="52c53-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="52c53-232">Si se ha establecido, el servidor de libreta de direcciones usa el número normalizado en <strong>proxyAddresses</strong>, en caso de que la configuración del CMS de <strong>UseNormalizationRules</strong> tenga el valor FALSE; de lo contrario, se comporta de la misma forma que cuando el bit del indicador es 0x1000.</span><span class="sxs-lookup"><span data-stu-id="52c53-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="52c53-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="52c53-p114">Si se ha establecido, el servidor de libreta de direcciones no incluye objetos en la tabla AbUserEntry que tengan este valor para el atributo especificado. Por ejemplo, si el atributo <strong>msRTCSIP-PrimaryUserAddress</strong> tiene establecido este bit del indicador, los contactos con este atributo no se escribirán en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52c53-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="52c53-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="52c53-p115">Si se ha establecido, el servidor de libreta de direcciones no incluye objetos en la tabla AbUserEntry que no tengan este valor para el atributo especificado. Si los bits del indicador 0x4000 y 0x8000 no se han establecido en un objeto, el atributo con el valor de bit del indicador establecido en 0x4000 tendrá prioridad y el objeto se excluye de la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="52c53-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="52c53-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="52c53-p116">Si se ha establecido, representa un objeto de grupo. El Replicador de usuarios se sirve de este bit de indicador para incluir contactos con el atributo <strong>groupType</strong>, cuya presencia indica que se trata de un grupo (por ejemplo, una lista de distribución o un grupo de seguridad).</span><span class="sxs-lookup"><span data-stu-id="52c53-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="52c53-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="52c53-243">Si se ha establecido, el Replicador de usuarios se sirve de este bit de indicador para incluir este atributo en archivos de servidor de libreta de direcciones específicas de un dispositivo (es decir, archivos con una extensión .dabs).</span><span class="sxs-lookup"><span data-stu-id="52c53-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52c53-244">En versiones anteriores de Lync Server, al aplicar un cambio en Active Directory, se necesitaría que el administrador ejecutara los cmdlets **Update-CSUserDatabase** y **Update – CSAddressBook** de Windows PowerShell para conservar el cambio en la base de datos de usuario de Lync Server y la base de datos de RTCab inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="52c53-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="52c53-245">En Lync Server 2013, el replicador de usuarios de Lync Server tomará los cambios de Active Directory y actualizará la base de datos de usuarios de Lync Server en función de un intervalo configurado.</span><span class="sxs-lookup"><span data-stu-id="52c53-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="52c53-246">El replicador de usuarios de Lync Server también propagará los cambios rápidamente a la base de datos de RTCab sin que el Administrador tenga que ejecutar Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="52c53-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="52c53-247">Si la consulta Web de la libreta de direcciones está habilitada, los clientes de Lync reflejarán los cambios en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="52c53-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="52c53-248">Los administradores solo tendrán que ejecutar Update-CSAddressBook si está habilitada la descarga del archivo de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="52c53-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52c53-249">De forma predeterminada, el replicador de usuarios de Lync Server se ejecuta automáticamente cada 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="52c53-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="52c53-250">Puede configurar este intervalo mediante Set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.</span><span class="sxs-lookup"><span data-stu-id="52c53-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="52c53-251">Filtrado de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="52c53-251">Filtering the Address Book</span></span>

<span data-ttu-id="52c53-252">Los usuarios rellenados en los archivos del servidor de la libreta de direcciones pueden controlarse en función de determinados atributos de servicios de dominio de Active Directory enumerados en la tabla ABAttribute.</span><span class="sxs-lookup"><span data-stu-id="52c53-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="52c53-253">Uno de estos atributos que se usa para el filtrado es el atributo **msExchangeHideFromAddressBook**.</span><span class="sxs-lookup"><span data-stu-id="52c53-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="52c53-254">Se trata de un atributo de usuario que agrega el esquema de Exchange.</span><span class="sxs-lookup"><span data-stu-id="52c53-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="52c53-255">Si el valor de este atributo es TRUE, Exchange Server lo usa para ocultar el contacto de la lista global de direcciones (LGD) de Outlook.</span><span class="sxs-lookup"><span data-stu-id="52c53-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="52c53-256">De forma similar, si el valor de este atributo es TRUE, User Replicator no incluye a ese usuario en la tabla AbUserEntry y no estará en los archivos del servidor de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="52c53-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="52c53-p120">Puede usar ciertos bits de indicador para definir un filtro que se vaya a usar en los atributos del servidor de libreta de direcciones. Por ejemplo, la presencia de ciertos bits de indicador pueden identificar un atributo como un atributo de inclusión o un atributo de exclusión. El Replicador de usuarios deja fuera a los contactos que contienen un atributo de exclusión y a los contactos que no contienen un atributo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="52c53-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="52c53-260">Para obtener más información acerca de cómo filtrar la libreta de direcciones, consulte <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">cmdlets del servidor de libreta de direcciones en Lync Server 2013</A>y <A href="http://go.microsoft.com/fwlink/?linkid=330430">filtrar la libreta de direcciones de Lync 2013</A></span><span class="sxs-lookup"><span data-stu-id="52c53-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="52c53-p121">En estos momentos, existen tres tipos diferentes de filtros. En la tabla siguiente se enumeran estos filtros.</span><span class="sxs-lookup"><span data-stu-id="52c53-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52c53-263">Atributo</span><span class="sxs-lookup"><span data-stu-id="52c53-263">Attribute</span></span></th>
<th><span data-ttu-id="52c53-264">Descripción</span><span class="sxs-lookup"><span data-stu-id="52c53-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52c53-265">0x800</span><span class="sxs-lookup"><span data-stu-id="52c53-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="52c53-p122">Si se ha establecido, identifica un atributo necesario para un contacto. El Replicador de usuarios usa este bit de indicador para dejar fuera los contactos que no contienen al menos uno de los atributos obligatorios. OuPathId es un atributo obligatorio, que está siempre establecido. De forma que se debe establecer al menos uno de los otros atributos obligatorios. De lo contrario, el contacto (es decir, con el valor del atributo OuPathId obligatorio) no se escribirá en la base de datos. Por ejemplo, si <strong>telephoneNumber</strong> y <strong>homePhone</strong> se definen como atributos obligatorios, únicamente los contactos que tengan al menos uno de estos atributos se escribirán en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52c53-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c53-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="52c53-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="52c53-p123">Si se ha establecido, identifica a un atributo de exclusión. El Replicador de usuarios se sirve de este bit de indicador para filtrar contactos que contienen este atributo. Por ejemplo, si se definió <strong>msRTCSIP-PrimaryUserAddress</strong> como un atributo de exclusión, los contactos que tengan este atributo no se escribirán en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52c53-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c53-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="52c53-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="52c53-p124">Si se ha establecido, identifica a un atributo de inclusión. El Replicador de usuarios se sirve de este bit de indicador para filtrar contactos que no contienen este atributo. Por ejemplo, si se definió <strong>msRTCSIP-PrimaryUserAddress</strong> como un atributo de inclusión, únicamente se escribirán en la base de datos los contactos que tengan este atributo.</span><span class="sxs-lookup"><span data-stu-id="52c53-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="52c53-280">Si se establecieron los bits de indicador 0x4000 (atributo de exclusión) y 0x8000 (atributo de inclusión), el bit 0x4000 sobrescribe el bit 0x8000 y el contacto se excluirá.</span><span class="sxs-lookup"><span data-stu-id="52c53-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="52c53-p125">Pese a que puede filtrar la libreta de direcciones para que incluya exclusivamente a ciertos usuarios, cuando se restringen entradas no se limita la capacidad de otros usuarios para ponerse en contacto con los usuarios filtrados o para ver su estado de presencia. los usuarios siempre pueden buscar usuarios y enviar manualmente mensajes instantáneos o iniciar llamadas manualmente a usuarios que no estén en la libreta de direcciones si especifican el nombre de inicio de sesión completo del usuario. Asimismo, la información de contacto para un usuario se puede encontrar en Outlook.</span><span class="sxs-lookup"><span data-stu-id="52c53-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="52c53-284">Aunque tener registros de contactos completos en los archivos de la libreta de direcciones permite usar Lync Server para iniciar el correo electrónico, el teléfono o las llamadas de telefonía IP empresarial (es decir, si la telefonía IP empresarial está habilitada en el servidor) con los usuarios que no están configurados para el inicio de sesión Protocol (SIP), algunas organizaciones prefieren incluir sólo usuarios con SIP habilitado en sus entradas del servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="52c53-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="52c53-285">Puede filtrar la libreta de direcciones para que incluya solamente a usuarios habilitados para SIP si borra el bit 0x800 en la columna **Indicadores** de los siguientes atributos obligatorios: **mailNickname**, **telephoneNumber**, **homePhone** y **mobile**.</span><span class="sxs-lookup"><span data-stu-id="52c53-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="52c53-286">También puede filtrar la libreta de direcciones para que incluya solamente a usuarios habilitados para SIP; para ello establezca un bit 0x8000 (atributo de inclusión) en la columna **Indicadores** del atributo **msRTCSIP-PrimaryUserAddress**.</span><span class="sxs-lookup"><span data-stu-id="52c53-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="52c53-287">Esto sirve también de ayuda para excluir cuentas del servicio de los archivos de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="52c53-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="52c53-288">Una vez haya modificado la tabla AbAttribute, puede actualizar los datos en la tabla AbUserEntry mediante la ejecución del comando**Update-CsUserDatabase** del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="52c53-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="52c53-289">Cuando se haya completado la replicación, puede actualizar el archivo en el almacén de archivos del servidor de la libreta de direcciones ejecutando manualmente el comando **UpdateCsAddressBook** del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="52c53-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52c53-290">El servidor front-end en el que se coloca el servidor de la libreta de direcciones no se puede configurar de forma administrativa.</span><span class="sxs-lookup"><span data-stu-id="52c53-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="52c53-291">Uno se elige durante la implementación (normalmente, el primer servidor front-end que se implementó).</span><span class="sxs-lookup"><span data-stu-id="52c53-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="52c53-292">En caso de error, el servicio de libreta de direcciones se desplazará a otro servidor front-end y no necesitará atención administrativa.</span><span class="sxs-lookup"><span data-stu-id="52c53-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52c53-293">Si ha consolidado o modificado de otra manera su infraestructura desde una implementación de varios bosques o una implementación principal/secundaria (como la consolidación de la infraestructura antes de pasar a Lync Server), es posible que la descarga del servicio de libreta de direcciones y la consulta Web de la libreta de direcciones no funcionen para algunos usuarios.</span><span class="sxs-lookup"><span data-stu-id="52c53-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="52c53-294">Cuando se encuentra en una implementación con varios dominios o bosques, el atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> se rellena en los objetos de usuario que presentan el problema.</span><span class="sxs-lookup"><span data-stu-id="52c53-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="52c53-295">El atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> debe establecerse en null en estos objetos para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="52c53-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

