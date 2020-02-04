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
ms.openlocfilehash: 5d12b904cbb679b66579c7c669ba46e0d732034b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="aff81-102">Administrar el servicio de libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aff81-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aff81-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="aff81-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="aff81-104">Como parte de la implementación de Lync Server, Enterprise Edition o Standard Edition Server, el servicio de libreta de direcciones se instala de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aff81-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="aff81-105">La base de datos que usa el servicio de libreta de direcciones, RTCab, se crea en el servidor SQL (para Enterprise Edition, que es el servidor SQL Server de servicios de fondo; en el servidor Standard Edition, el servidor SQL Server en el que se proviene).</span><span class="sxs-lookup"><span data-stu-id="aff81-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aff81-106">Para obtener información sobre el uso de <STRONG>ADSI Edit</STRONG> para editar atributos de objetos de Active Directory Domain Services, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span><span class="sxs-lookup"><span data-stu-id="aff81-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="aff81-107">Para obtener información sobre una herramienta del kit de recursos específicamente para el servicio de libreta de direcciones, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330429">herramientas del kit de recursos de Microsoft Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aff81-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="aff81-108">Normalización del número de teléfono del servidor de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="aff81-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="aff81-109">Lync Server requiere el estándar RFC 3966/E. 164 números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="aff81-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="aff81-110">Para usar números de teléfono que no se hayan estructurado o que tengan un formato incoherente, Lync Server depende del servidor de la libreta de direcciones para preprocesar los números de teléfono antes de que se entreguen a las reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="aff81-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="aff81-111">Cuando se usa un número de teléfono de la libreta de direcciones y se aplica la regla de normalización, los clientes, como Lync Phone Edition y Lync Mobile, pueden usar estos números normalizados.</span><span class="sxs-lookup"><span data-stu-id="aff81-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="aff81-112">Es posible que las reglas de normalización que se usaron en versiones anteriores no funcionen correctamente sin algunos ajustes.</span><span class="sxs-lookup"><span data-stu-id="aff81-112">The normalization rules that were used in previous versions may not work properly without some adjustments.</span></span> <span data-ttu-id="aff81-113">Dado que los espacios en blanco y los caracteres no obligatorios se quitan antes de las reglas de normalización, si la expresión de Regex está buscando específicamente un guión u otro carácter que se ha quitado, es posible que la regla de normalización no se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="aff81-113">Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail.</span></span> <span data-ttu-id="aff81-114">Debe revisar las reglas de normalización para asegurarse de que no busquen estos caracteres no obligatorios o de que la regla puede dar error y continuar en el caso de que el carácter no se presente donde la regla se anticipe.</span><span class="sxs-lookup"><span data-stu-id="aff81-114">You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="aff81-115">Duplicador de usuarios y servidor de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="aff81-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="aff81-116">El servidor de la libreta de direcciones utiliza los datos proporcionados por el replicador de usuarios para actualizar la información que obtiene inicialmente de la lista global de direcciones (GAL).</span><span class="sxs-lookup"><span data-stu-id="aff81-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="aff81-117">El replicador de usuarios escribe los atributos de los servicios de dominio de Active Directory para cada usuario, contacto y grupo en la tabla AbUserEntry de la base de datos y el servidor de la libreta de direcciones sincroniza los datos de usuario de la base de datos en los archivos del almacén de archivos del servidor de la libreta de direcciones y en el RTCab de base de datos de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="aff81-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="aff81-118">El esquema de la tabla AbUserEntry usa dos columnas: **UserGuid** y **UserData**.</span><span class="sxs-lookup"><span data-stu-id="aff81-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="aff81-119">**UserGuid** es la columna de índice y contiene el GUID de 16 bytes del objeto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aff81-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="aff81-120">**UserData** es una columna de imagen que contiene todos los atributos de servicios de dominio de Active Directory mencionados anteriormente para ese contacto.</span><span class="sxs-lookup"><span data-stu-id="aff81-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="aff81-121">El replicador de usuarios determina qué atributos de Active Directory se escribirán leyendo una tabla de configuración que se encuentra en la misma instancia basada en SQL Server que la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="aff81-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="aff81-122">La tabla ABAttribute contiene tres columnas: **ID**, **Name**, **Flags**y **enable**.</span><span class="sxs-lookup"><span data-stu-id="aff81-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="aff81-123">La tabla se crea durante la configuración de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff81-123">The table is created during database setup.</span></span> <span data-ttu-id="aff81-124">Si la tabla ABAttribute está vacía, User Replicator omite su lógica de procesamiento de la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="aff81-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="aff81-125">Los atributos del servidor de la libreta de direcciones son dinámicos y se recuperan de la tabla ABAttribute, que inicialmente escribe el servidor de la libreta de direcciones cuando se activa el servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="aff81-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="aff81-126">La activación del servidor de la libreta de direcciones rellena la tabla abattributes con los valores que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="aff81-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aff81-127">ID</span><span class="sxs-lookup"><span data-stu-id="aff81-127">ID</span></span></th>
<th><span data-ttu-id="aff81-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="aff81-128">Name</span></span></th>
<th><span data-ttu-id="aff81-129">Marcas</span><span class="sxs-lookup"><span data-stu-id="aff81-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff81-130">1</span><span class="sxs-lookup"><span data-stu-id="aff81-130">1</span></span></p></td>
<td><p><span data-ttu-id="aff81-131">givenName</span><span class="sxs-lookup"><span data-stu-id="aff81-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="aff81-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="aff81-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-133">1</span><span class="sxs-lookup"><span data-stu-id="aff81-133">2</span></span></p></td>
<td><p><span data-ttu-id="aff81-134">Utilidad</span><span class="sxs-lookup"><span data-stu-id="aff81-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="aff81-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="aff81-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-136">3</span><span class="sxs-lookup"><span data-stu-id="aff81-136">3</span></span></p></td>
<td><p><span data-ttu-id="aff81-137">Nunca</span><span class="sxs-lookup"><span data-stu-id="aff81-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="aff81-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="aff81-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-139">4</span><span class="sxs-lookup"><span data-stu-id="aff81-139">4</span></span></p></td>
<td><p><span data-ttu-id="aff81-140">Título</span><span class="sxs-lookup"><span data-stu-id="aff81-140">Title</span></span></p></td>
<td><p><span data-ttu-id="aff81-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="aff81-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-142">5</span><span class="sxs-lookup"><span data-stu-id="aff81-142">5</span></span></p></td>
<td><p><span data-ttu-id="aff81-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="aff81-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="aff81-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="aff81-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-145">6</span><span class="sxs-lookup"><span data-stu-id="aff81-145">6</span></span></p></td>
<td><p><span data-ttu-id="aff81-146">Compañía</span><span class="sxs-lookup"><span data-stu-id="aff81-146">Company</span></span></p></td>
<td><p><span data-ttu-id="aff81-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="aff81-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-148">7</span><span class="sxs-lookup"><span data-stu-id="aff81-148">7</span></span></p></td>
<td><p><span data-ttu-id="aff81-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="aff81-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="aff81-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="aff81-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-151">4,8</span><span class="sxs-lookup"><span data-stu-id="aff81-151">8</span></span></p></td>
<td><p><span data-ttu-id="aff81-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="aff81-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="aff81-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="aff81-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-154">99,999</span><span class="sxs-lookup"><span data-stu-id="aff81-154">9</span></span></p></td>
<td><p><span data-ttu-id="aff81-155">NúmeroDeTeléfono</span><span class="sxs-lookup"><span data-stu-id="aff81-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="aff81-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="aff81-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-157">base10</span><span class="sxs-lookup"><span data-stu-id="aff81-157">10</span></span></p></td>
<td><p><span data-ttu-id="aff81-158">Teléfono particular</span><span class="sxs-lookup"><span data-stu-id="aff81-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="aff81-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="aff81-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-160">once</span><span class="sxs-lookup"><span data-stu-id="aff81-160">11</span></span></p></td>
<td><p><span data-ttu-id="aff81-161">Móvil</span><span class="sxs-lookup"><span data-stu-id="aff81-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="aff81-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="aff81-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-163">2007</span><span class="sxs-lookup"><span data-stu-id="aff81-163">12</span></span></p></td>
<td><p><span data-ttu-id="aff81-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="aff81-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="aff81-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="aff81-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-166">13</span><span class="sxs-lookup"><span data-stu-id="aff81-166">13</span></span></p></td>
<td><p><span data-ttu-id="aff81-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="aff81-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="aff81-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="aff81-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-169">14</span><span class="sxs-lookup"><span data-stu-id="aff81-169">14</span></span></p></td>
<td><p><span data-ttu-id="aff81-170">Tales</span><span class="sxs-lookup"><span data-stu-id="aff81-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="aff81-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="aff81-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-172">4,5</span><span class="sxs-lookup"><span data-stu-id="aff81-172">15</span></span></p></td>
<td><p><span data-ttu-id="aff81-173">groupType</span><span class="sxs-lookup"><span data-stu-id="aff81-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="aff81-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="aff81-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-175">apartado</span><span class="sxs-lookup"><span data-stu-id="aff81-175">16</span></span></p></td>
<td><p><span data-ttu-id="aff81-176">Grandes</span><span class="sxs-lookup"><span data-stu-id="aff81-176">Department</span></span></p></td>
<td><p><span data-ttu-id="aff81-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="aff81-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-178">apartado</span><span class="sxs-lookup"><span data-stu-id="aff81-178">17</span></span></p></td>
<td><p><span data-ttu-id="aff81-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="aff81-179">Description</span></span></p></td>
<td><p><span data-ttu-id="aff81-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="aff81-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-181">18</span><span class="sxs-lookup"><span data-stu-id="aff81-181">18</span></span></p></td>
<td><p><span data-ttu-id="aff81-182">Administrador</span><span class="sxs-lookup"><span data-stu-id="aff81-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="aff81-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="aff81-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-184">19</span><span class="sxs-lookup"><span data-stu-id="aff81-184">19</span></span></p></td>
<td><p><span data-ttu-id="aff81-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="aff81-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="aff81-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="aff81-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-187">veinte</span><span class="sxs-lookup"><span data-stu-id="aff81-187">20</span></span></p></td>
<td><p><span data-ttu-id="aff81-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="aff81-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="aff81-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="aff81-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-190">99</span><span class="sxs-lookup"><span data-stu-id="aff81-190">99</span></span></p></td>
<td><p><span data-ttu-id="aff81-191">entryID</span><span class="sxs-lookup"><span data-stu-id="aff81-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="aff81-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="aff81-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aff81-193">Los números de la columna **identificador** deben ser únicos y nunca se deben volver a usar.</span><span class="sxs-lookup"><span data-stu-id="aff81-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="aff81-194">Además, mantener los valores de identificador en 256 ahorra espacio en los archivos de salida escritos por el servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="aff81-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="aff81-195">Sin embargo, el valor del identificador máximo es 65535.</span><span class="sxs-lookup"><span data-stu-id="aff81-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="aff81-196">La columna **nombre** corresponde al nombre del atributo de Active Directory que el replicador de usuarios debe incluir en la tabla AbUserEntry por cada contacto.</span><span class="sxs-lookup"><span data-stu-id="aff81-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="aff81-197">El valor de la columna **Flags** se usa para definir el tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="aff81-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="aff81-198">Los siguientes tipos de atributos del servidor de la libreta de direcciones son reconocidos por el replicador de usuarios, indicado por el byte bajo del valor de la columna **marcas** .</span><span class="sxs-lookup"><span data-stu-id="aff81-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aff81-199">Atributo</span><span class="sxs-lookup"><span data-stu-id="aff81-199">Attribute</span></span></th>
<th><span data-ttu-id="aff81-200">Descripción</span><span class="sxs-lookup"><span data-stu-id="aff81-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff81-201">0X0</span><span class="sxs-lookup"><span data-stu-id="aff81-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="aff81-202">Un atributo de cadena.</span><span class="sxs-lookup"><span data-stu-id="aff81-202">A string attribute.</span></span> <span data-ttu-id="aff81-203">El replicador de usuarios convierte este tipo en UTF-8 antes de almacenarlo en la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="aff81-203">User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-204">0x1</span><span class="sxs-lookup"><span data-stu-id="aff81-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="aff81-205">Un atributo binario.</span><span class="sxs-lookup"><span data-stu-id="aff81-205">A binary attribute.</span></span> <span data-ttu-id="aff81-206">El replicador de usuarios almacena este objeto en el BLOB sin ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="aff81-206">User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-207">0X2</span><span class="sxs-lookup"><span data-stu-id="aff81-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="aff81-208">Un atributo de cadena, pero se incluye solo si el valor del atributo &quot;comienza por&quot;Tel:.</span><span class="sxs-lookup"><span data-stu-id="aff81-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="aff81-209">Esto se redestina principalmente a los atributos de cadena de valor múltiple, en concreto <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="aff81-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="aff81-210">En este caso, el servidor de la libreta de direcciones solo está interesado en las &quot;entradas de&quot; <strong>proxyAddresses</strong> que comienzan con Tel:.</span><span class="sxs-lookup"><span data-stu-id="aff81-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="aff81-211">Por lo tanto, en interés de ahorrar espacio, User Replicator almacena solo las entradas que comienzan &quot;con Tel&quot;:.</span><span class="sxs-lookup"><span data-stu-id="aff81-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-212">0X3</span><span class="sxs-lookup"><span data-stu-id="aff81-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="aff81-213">Un atributo de cadena booleana, que si es verdadero hace que el replicador de usuarios no incluya este contacto en la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="aff81-213">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table.</span></span> <span data-ttu-id="aff81-214">Si es falso, hace que el replicador de usuarios incluya los atributos de este contacto en la tabla AbUserEntry, pero no en el atributo concreto con este indicador.</span><span class="sxs-lookup"><span data-stu-id="aff81-214">If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag.</span></span> <span data-ttu-id="aff81-215">Este es otro tipo especial de caso que es principalmente para el atributo <strong>msExchHideFromAddressLists</strong> .</span><span class="sxs-lookup"><span data-stu-id="aff81-215">This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-216">0x4</span><span class="sxs-lookup"><span data-stu-id="aff81-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="aff81-217">Un atributo de cadena, pero se incluye solo si el valor del atributo &quot;comienza por&quot; SMTP: e &quot; @ &quot; incluye el símbolo.</span><span class="sxs-lookup"><span data-stu-id="aff81-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-218">0X5</span><span class="sxs-lookup"><span data-stu-id="aff81-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="aff81-219">Un atributo de cadena, pero se incluye solo si el valor del atributo comienza &quot;por Tel&quot; : &quot;o SMTP&quot; : e incluye &quot; @ &quot; el símbolo.</span><span class="sxs-lookup"><span data-stu-id="aff81-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-220">0x100</span><span class="sxs-lookup"><span data-stu-id="aff81-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="aff81-221">Si se establece, se trata de un atributo de valor múltiple que puede aparecer más de una vez para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="aff81-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-222">0x400</span><span class="sxs-lookup"><span data-stu-id="aff81-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="aff81-223">Si se establece, se identifica el atributo de nombre de cuenta de usuario de correo electrónico de un contacto.</span><span class="sxs-lookup"><span data-stu-id="aff81-223">If set, this identifies the email user account name attribute for a contact.</span></span> <span data-ttu-id="aff81-224">El servidor de la libreta de direcciones usa esta marca para identificar qué valor de atributo se muestra en la entrada del registro de eventos de normalización del teléfono.</span><span class="sxs-lookup"><span data-stu-id="aff81-224">Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-225">0x800</span><span class="sxs-lookup"><span data-stu-id="aff81-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="aff81-226">Si se establece, identifica un atributo obligatorio para un contacto.</span><span class="sxs-lookup"><span data-stu-id="aff81-226">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="aff81-227">El servidor de la libreta de direcciones incluye un usuario en la tabla AbUserEntry solo si hay un valor para este atributo en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aff81-227">Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory.</span></span> <span data-ttu-id="aff81-228">Si hay más de un atributo obligatorio, solo uno de ellos necesita tener un valor para incluir al usuario en la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="aff81-228">If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-229">ó</span><span class="sxs-lookup"><span data-stu-id="aff81-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="aff81-230">Si se establece, el servidor de la libreta de direcciones siempre normaliza el valor de este atributo.</span><span class="sxs-lookup"><span data-stu-id="aff81-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="aff81-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="aff81-232">Si se establece, el servidor de la libreta de direcciones usa el número normalizado de <strong>proxyAddresses</strong>, si la configuración de <strong>USENORMALIZATIONRULES</strong> CMS es falsa. de lo contrario, se comporta igual que cuando el bit de la marca es 0x1000.</span><span class="sxs-lookup"><span data-stu-id="aff81-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="aff81-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="aff81-234">Si se establece, el servidor de la libreta de direcciones no incluye los objetos de la tabla AbUserEntry que tienen este valor para el atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="aff81-234">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute.</span></span> <span data-ttu-id="aff81-235">Por ejemplo, si el atributo <strong>msRTCSIP-PrimaryUserAddress</strong> tiene este bit de marca establecido, los contactos que tienen este atributo no se escriben en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff81-235">For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="aff81-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="aff81-237">Si se establece, el servidor de la libreta de direcciones no incluye los objetos de la tabla AbUserEntry que no tienen este valor para el atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="aff81-237">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute.</span></span> <span data-ttu-id="aff81-238">Si se establecen los bits de indicador 0x4000 y 0x8000 en un objeto, el atributo con el valor de bit de indicador establecido en 0x4000 tiene prioridad y el objeto se excluye de la tabla AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="aff81-238">If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="aff81-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="aff81-240">Si se establece, representa un objeto de grupo.</span><span class="sxs-lookup"><span data-stu-id="aff81-240">If set, this represents a group object.</span></span> <span data-ttu-id="aff81-241">Replicador de usuarios usa este bit de marca para incluir contactos con el atributo <strong>GroupType</strong> cuya presencia indica un grupo (por ejemplo, una lista de distribución o un grupo de seguridad).</span><span class="sxs-lookup"><span data-stu-id="aff81-241">User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="aff81-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="aff81-243">Si se establece, User Replicator usa este bit de marca para incluir este atributo en los archivos del servidor de la libreta de direcciones específicos del dispositivo (es decir, los archivos con la extensión. DABS).</span><span class="sxs-lookup"><span data-stu-id="aff81-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aff81-244">En versiones anteriores de Lync Server, al aplicar un cambio en Active Directory, el administrador tendría que ejecutar **Update-CSUserDatabase** y **Update – CSAddressBook** cmdlets de Windows PowerShell para conservar el cambio en la base de datos de usuario de Lync Server y RTCab de inmediato.</span><span class="sxs-lookup"><span data-stu-id="aff81-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="aff81-245">En Lync Server 2013, el replicador de usuarios de Lync Server atenderá los cambios de Active Directory y actualizará la base de datos de usuarios de Lync Server en función de un intervalo configurado.</span><span class="sxs-lookup"><span data-stu-id="aff81-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="aff81-246">El replicador de usuarios de Lync Server también propagará los cambios a la base de datos de RTCab rápidamente sin que el Administrador tenga que ejecutar Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="aff81-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="aff81-247">Si la consulta Web de libreta de direcciones está habilitada, los cambios se reflejarán en los resultados de búsqueda de los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="aff81-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="aff81-248">Los administradores solo tendrán que ejecutar Update-CSAddressBook si está habilitada la descarga del archivo de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="aff81-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aff81-249">De forma predeterminada, el replicador de usuarios de Lync Server se ejecuta automáticamente cada 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="aff81-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="aff81-250">Puede configurar este intervalo mediante Set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.</span><span class="sxs-lookup"><span data-stu-id="aff81-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="aff81-251">Filtrar la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="aff81-251">Filtering the Address Book</span></span>

<span data-ttu-id="aff81-252">Los usuarios rellenados en los archivos del servidor de la libreta de direcciones se pueden controlar en función de determinados atributos de servicios de dominio de Active Directory enumerados en la tabla ABAttribute.</span><span class="sxs-lookup"><span data-stu-id="aff81-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="aff81-253">Un atributo de este tipo utilizado para filtrar es el atributo **msExchangeHideFromAddressBook** .</span><span class="sxs-lookup"><span data-stu-id="aff81-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="aff81-254">Este es un atributo de usuario agregado por el esquema de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aff81-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="aff81-255">Si el valor de este atributo es verdadero, Exchange Server usa este atributo para ocultar el contacto de la lista global de direcciones (GAL) de Outlook.</span><span class="sxs-lookup"><span data-stu-id="aff81-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="aff81-256">De forma similar, si el valor de este atributo es TRUE, User Replicator no incluye a ese usuario en la tabla AbUserEntry y este usuario no estará en los archivos del servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="aff81-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="aff81-257">Puede usar algunos bits de la bandera para definir un filtro que se usará en los atributos del servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="aff81-257">You can use some flag bits to define a filter to use on Address Book Server attributes.</span></span> <span data-ttu-id="aff81-258">Por ejemplo, la presencia de ciertos bits de indicador puede identificar un atributo como un atributo Include o un atributo exclude.</span><span class="sxs-lookup"><span data-stu-id="aff81-258">For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute.</span></span> <span data-ttu-id="aff81-259">El duplicador de usuarios filtra los contactos que contienen un atributo de exclusión y filtra los contiene que no contienen un atributo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="aff81-259">User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="aff81-260">Para obtener más información sobre cómo filtrar la libreta de direcciones, consulte <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">cmdlets del servidor de la libreta de direcciones en Lync Server 2013</A>y <A href="http://go.microsoft.com/fwlink/?linkid=330430">filtrar la libreta de direcciones de Lync 2013</A></span><span class="sxs-lookup"><span data-stu-id="aff81-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="aff81-261">Actualmente, hay tres filtros diferentes.</span><span class="sxs-lookup"><span data-stu-id="aff81-261">Currently, there are three different filters.</span></span> <span data-ttu-id="aff81-262">En la tabla siguiente se enumeran estos filtros.</span><span class="sxs-lookup"><span data-stu-id="aff81-262">The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aff81-263">Atributo</span><span class="sxs-lookup"><span data-stu-id="aff81-263">Attribute</span></span></th>
<th><span data-ttu-id="aff81-264">Descripción</span><span class="sxs-lookup"><span data-stu-id="aff81-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff81-265">0x800</span><span class="sxs-lookup"><span data-stu-id="aff81-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="aff81-266">Si se establece, identifica un atributo obligatorio para un contacto.</span><span class="sxs-lookup"><span data-stu-id="aff81-266">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="aff81-267">Replicador de usuarios usa este bit de marca para filtrar los contactos que no contienen al menos un atributo requerido.</span><span class="sxs-lookup"><span data-stu-id="aff81-267">User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute.</span></span> <span data-ttu-id="aff81-268">El OuPathId es un atributo obligatorio, que siempre se establece.</span><span class="sxs-lookup"><span data-stu-id="aff81-268">The OuPathId is a required attribute, which is always set.</span></span> <span data-ttu-id="aff81-269">Por lo tanto, se debe establecer al menos uno de los atributos obligatorios.</span><span class="sxs-lookup"><span data-stu-id="aff81-269">So at least one of other required attributes should be set.</span></span> <span data-ttu-id="aff81-270">De lo contrario, el valor de Contact (es decir, con el valor de atributo requerido OuPathId) aún no se escribirá en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff81-270">Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database.</span></span> <span data-ttu-id="aff81-271">Por ejemplo, si <strong>telephoneNumber</strong> y <strong>teléfono particular</strong> se definen como atributos necesarios, solo los contactos que tengan al menos uno de estos atributos se escribirán en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff81-271">For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff81-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="aff81-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="aff81-273">Si se establece, esto identifica un atributo exclude.</span><span class="sxs-lookup"><span data-stu-id="aff81-273">If set, this identifies an exclude attribute.</span></span> <span data-ttu-id="aff81-274">Replicador de usuarios usa este bit de marca para filtrar los contactos que contienen este atributo.</span><span class="sxs-lookup"><span data-stu-id="aff81-274">User Replicator uses this flag bit to filter out contacts that contain this attribute.</span></span> <span data-ttu-id="aff81-275">Por ejemplo, si <strong>msRTCSIP-PrimaryUserAddress</strong> se define como un atributo Exclude, los contactos que tienen este atributo no se escriben en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff81-275">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff81-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="aff81-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="aff81-277">Si se establece, esto identifica un atributo Include.</span><span class="sxs-lookup"><span data-stu-id="aff81-277">If set, this identifies an include attribute.</span></span> <span data-ttu-id="aff81-278">Replicador de usuarios usa este bit de marca para filtrar los contactos que no contienen este atributo.</span><span class="sxs-lookup"><span data-stu-id="aff81-278">User Replicator uses this flag bit to filter out contacts that do not contain this attribute.</span></span> <span data-ttu-id="aff81-279">Por ejemplo, si <strong>msRTCSIP-PrimaryUserAddress</strong> se define como un atributo Include, solo los contactos que tienen este atributo se escriben en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aff81-279">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="aff81-280">Si se establecen los bits de indicador 0x4000 (atributo Exclude) y 0x8000 (include Attribute), el bit 0x4000 reemplaza el valor de 0x8000 bit y se excluye el contacto.</span><span class="sxs-lookup"><span data-stu-id="aff81-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="aff81-281">Aunque puede filtrar la libreta de direcciones para incluir solo algunos usuarios, la limitación de las entradas no limita la capacidad de otros usuarios de ponerse en contacto con los usuarios filtrados ni de ver su estado de presencia.</span><span class="sxs-lookup"><span data-stu-id="aff81-281">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status.</span></span> <span data-ttu-id="aff81-282">Los usuarios siempre pueden encontrarse, enviar mensajes instantáneos manualmente o iniciar llamadas manualmente a usuarios que no estén en la libreta de direcciones escribiendo el nombre de inicio de sesión completo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="aff81-282">Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name.</span></span> <span data-ttu-id="aff81-283">Además, la información de contacto de un usuario también podría encontrarse en Outlook.</span><span class="sxs-lookup"><span data-stu-id="aff81-283">Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="aff81-284">Aunque la opción de registros de contactos completos en los archivos de la libreta de direcciones permite usar Lync Server para iniciar el correo electrónico, el teléfono o las llamadas de telefonía empresariales (es decir, si la telefonía IP empresarial está habilitada en el servidor) con usuarios que no están configurados para iniciar sesión Protocolo (SIP), algunas organizaciones prefieren incluir solo los usuarios con SIP habilitado en las entradas del servidor de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="aff81-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="aff81-285">Puede filtrar la libreta de direcciones para incluir solo usuarios habilitados para SIP si desactiva la bit de 0x800 en la columna **Flags** de los siguientes atributos obligatorios: **mailNickname**, **telephoneNumber**, **teléfono particular**y **Mobile**.</span><span class="sxs-lookup"><span data-stu-id="aff81-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="aff81-286">También puede filtrar la libreta de direcciones para incluir solo los usuarios habilitados para SIP mediante la configuración de 0x8000 (include Attribute) en la columna **Flags** del atributo **msRTCSIP-PrimaryUserAddress** .</span><span class="sxs-lookup"><span data-stu-id="aff81-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="aff81-287">Esto también ayuda a excluir cuentas de servicio de los archivos de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="aff81-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="aff81-288">Después de modificar la tabla ABAttribute, puede actualizar los datos de la tabla AbUserEntry ejecutando el cmdlet **Update-CsUserDatabase** comando.</span><span class="sxs-lookup"><span data-stu-id="aff81-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="aff81-289">Después de que se complete la replicación de UR, puede actualizar el archivo en el almacén de archivos del servidor de la libreta de direcciones ejecutando manualmente el cmdlet **UpdateCsAddressBook** .</span><span class="sxs-lookup"><span data-stu-id="aff81-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aff81-290">El servidor front-end en el que se encuentra el servidor de la libreta de direcciones no se puede configurar de forma administrativa.</span><span class="sxs-lookup"><span data-stu-id="aff81-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="aff81-291">Uno se elige durante la implementación (normalmente, el primer servidor front-end implementado).</span><span class="sxs-lookup"><span data-stu-id="aff81-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="aff81-292">En el caso de que se produzca un error, el servicio de libreta de direcciones se moverá a otro servidor front-end y no requiere ninguna atención administrativa.</span><span class="sxs-lookup"><span data-stu-id="aff81-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aff81-293">Si ha consolidado o modificado de otra manera su infraestructura desde una implementación de varios bosques o de una implementación de principal/secundario (como consolidar su infraestructura antes de migrar a Lync Server), es posible que se produzcan errores en la descarga del servicio de libreta de direcciones y la consulta Web de la libreta de direcciones para algunos usuarios.</span><span class="sxs-lookup"><span data-stu-id="aff81-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="aff81-294">Cuando se encuentra en una implementación que tiene varios dominios o bosques, el atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> se rellena en los objetos de usuario que presentan el problema.</span><span class="sxs-lookup"><span data-stu-id="aff81-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="aff81-295">El atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> debe establecerse en null en estos objetos para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="aff81-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

