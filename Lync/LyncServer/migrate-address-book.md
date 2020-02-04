---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="e9680-102">Migrar la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="e9680-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9680-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e9680-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e9680-104">En general, la libreta de direcciones de Lync Server 2010 se migra junto con el resto de la topología.</span><span class="sxs-lookup"><span data-stu-id="e9680-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="e9680-105">Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno de Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="e9680-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="e9680-106">Establezca la propiedad WMI **PartitionbyOU** en agrupar las entradas de la libreta de direcciones por unidad organizativa (OU).</span><span class="sxs-lookup"><span data-stu-id="e9680-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="e9680-107">Personalizar las reglas de normalización de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e9680-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="e9680-108">Cambió el valor predeterminado del parámetro **UseNormalizationRules** a false.</span><span class="sxs-lookup"><span data-stu-id="e9680-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="e9680-109">**Entradas de la libreta de direcciones agrupadas**</span><span class="sxs-lookup"><span data-stu-id="e9680-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="e9680-110">Si establece la propiedad WMI de **PartitionbyOU** en true para crear libretas de direcciones para cada ou, tendrá que establecer el atributo **msRTCSIP-GroupingId** de Active Directory en usuarios y contactos si desea continuar agrupando las entradas de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e9680-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="e9680-111">Es posible que desee agrupar las entradas de la libreta de direcciones para limitar el ámbito de las búsquedas en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e9680-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="e9680-112">Para usar el atributo **msRTCSIP-GroupingId** , escriba un script para rellenar el atributo y asigne el mismo valor a todos los usuarios que desee agrupar.</span><span class="sxs-lookup"><span data-stu-id="e9680-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="e9680-113">Por ejemplo, asigne un único valor para todos los usuarios de una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="e9680-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="e9680-114">**Reglas de normalización de libreta de direcciones**</span><span class="sxs-lookup"><span data-stu-id="e9680-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="e9680-115">Si ha personalizado las reglas de normalización de la libreta de direcciones en el entorno de Lync Server 2010, debe migrar las reglas personalizadas a su grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="e9680-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="e9680-116">Si no ha personalizado las reglas de normalización de la libreta de direcciones, no tiene nada que migrar para el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e9680-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="e9680-117">Las reglas de normalización predeterminadas para Lync Server 2013 son las mismas que las reglas predeterminadas para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e9680-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="e9680-118">Siga el procedimiento más adelante en esta sección para migrar reglas de normalización personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e9680-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9680-119">Si su organización usa el control remoto de llamadas y ha personalizado las reglas de normalización de la libreta de direcciones, debe realizar el procedimiento de este tema antes de poder usar el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e9680-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="e9680-120">El procedimiento requiere ser miembro del grupo RTCUniversalServerAdmins o derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="e9680-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="e9680-121">**UseNormalizationRules establecido en falso**</span><span class="sxs-lookup"><span data-stu-id="e9680-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="e9680-122">Si establece el valor de **UseNormalizationRules** en false para que los usuarios puedan usar números de teléfono a medida que se definen en servicios de dominio de Active Directory sin que Lync Server 2013 aplique reglas de normalización, debe establecer los parámetros **UseNormalizationRules** y **IgnoreGenericRules** en true.</span><span class="sxs-lookup"><span data-stu-id="e9680-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="e9680-123">Siga el procedimiento más adelante en esta sección para establecer estos parámetros en true.</span><span class="sxs-lookup"><span data-stu-id="e9680-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="e9680-124">Para migrar reglas de normalización personalizadas de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="e9680-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="e9680-125">Busque el archivo\_.\_txt\_de\_la normalización de números de teléfono de la empresa en la raíz de la carpeta compartida de la libreta de direcciones y cópiela en la raíz de la carpeta compartida de la libreta de direcciones del grupo de pruebas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9680-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9680-126">Las reglas de normalización de libreta de direcciones de muestra se han instalado en el directorio de archivos de ABS web Component.</span><span class="sxs-lookup"><span data-stu-id="e9680-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="e9680-127">La ruta de acceso es <STRONG>$installedDriveLetter: \Archivos de Programa\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e9680-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="e9680-128">Este archivo se puede copiar y cambiar de &nbsp;nombre como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;al directorio raíz de la carpeta compartida de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e9680-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="e9680-129">Por ejemplo, la libreta de direcciones compartida <STRONG></STRONG>en $serverX&nbsp;, la ruta de acceso será similar a: <STRONG> \\$serverX \LyncFileShare\2-webservices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e9680-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="e9680-130">Use un editor de texto, como el Bloc de notas, para\_abrir\_el\_archivo\_rules. txt de la normalización de números de teléfono de la empresa.</span><span class="sxs-lookup"><span data-stu-id="e9680-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="e9680-131">Algunos tipos de entradas no funcionarán correctamente en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9680-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="e9680-132">Busque en el archivo los tipos de entradas que se describen en este paso, edítelo según sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones del grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="e9680-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="e9680-133">Las cadenas que incluyen el espacio en blanco o la puntuación obligatorios producen errores en las reglas de normalización, ya que estos caracteres se eliminan de la cadena introducida en las reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="e9680-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="e9680-134">Si tiene cadenas que incluyen el espacio en blanco o la puntuación necesarios, debe modificar las cadenas.</span><span class="sxs-lookup"><span data-stu-id="e9680-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="e9680-135">Por ejemplo, la siguiente cadena haría que la regla de normalra fallara:</span><span class="sxs-lookup"><span data-stu-id="e9680-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="e9680-136">La cadena siguiente no provocará errores en la regla de normalización:</span><span class="sxs-lookup"><span data-stu-id="e9680-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="e9680-137">Para establecer UseNormalizationRules y IgnoreGenericRules en true</span><span class="sxs-lookup"><span data-stu-id="e9680-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="e9680-138">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e9680-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9680-139">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e9680-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="e9680-140">Si su implementación solo incluye Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** y **IgnoreGenericRules** a true:</span><span class="sxs-lookup"><span data-stu-id="e9680-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="e9680-141">Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores de Lync Server 2013 en la topología:</span><span class="sxs-lookup"><span data-stu-id="e9680-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="e9680-142">Espere a que se produzca la replicación del almacén central de administración en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="e9680-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="e9680-143">Modifique el archivo de reglas de normalización de\_teléfono\_,\_"\_reglas de normalización de número de teléfono de la empresa. txt", para que la implementación borre el contenido.</span><span class="sxs-lookup"><span data-stu-id="e9680-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="e9680-144">El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9680-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="e9680-145">Si el archivo no está presente, cree un archivo vacío con el nombre "\_regla\_de\_normalización\_de números de teléfono de la empresa. txt".</span><span class="sxs-lookup"><span data-stu-id="e9680-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="e9680-146">Espere unos minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.</span><span class="sxs-lookup"><span data-stu-id="e9680-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="e9680-147">Ejecute el siguiente cmdlet en cada grupo de servidores de Lync Server 2013 de su implementación:</span><span class="sxs-lookup"><span data-stu-id="e9680-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

