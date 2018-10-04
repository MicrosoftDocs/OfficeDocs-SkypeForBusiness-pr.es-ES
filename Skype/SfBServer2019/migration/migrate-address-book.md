---
title: Migrar la libreta de direcciones
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que necesite realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno heredado:'
ms.openlocfilehash: 01279284086499b112028644ea0e1ca2fc708dd0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370772"
---
# <a name="migrate-address-book"></a><span data-ttu-id="f1bae-104">Migrar la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="f1bae-104">Migrate Address Book</span></span>

<span data-ttu-id="f1bae-105">En general, la libreta de direcciones se migra junto con el resto de la topología.</span><span class="sxs-lookup"><span data-stu-id="f1bae-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="f1bae-106">Sin embargo, es posible que necesite realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno heredado:</span><span class="sxs-lookup"><span data-stu-id="f1bae-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="f1bae-107">Establecer la propiedad WMI **PartitionbyOU** para agrupar entradas de la libreta de direcciones por unidad organizativa (OU).</span><span class="sxs-lookup"><span data-stu-id="f1bae-107">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span> 

- <span data-ttu-id="f1bae-108">Puede personalizar las reglas de normalización de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="f1bae-108">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="f1bae-109">Cambiar el valor predeterminado para el parámetro **UseNormalizationRules** en False.</span><span class="sxs-lookup"><span data-stu-id="f1bae-109">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 

  <span data-ttu-id="f1bae-110">**Entradas de la libreta de direcciones agrupadas**</span><span class="sxs-lookup"><span data-stu-id="f1bae-110">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="f1bae-111">Si establece la propiedad WMI **PartitionbyOU** en True para crear libretas de direcciones para cada unidad organizativa, debe establecer el atributo **msRTCSIP-GroupingId** de Active Directory en usuarios y contactos si desea continuar agrupar entradas de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="f1bae-111">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="f1bae-112">Es posible que desee para agrupar entradas de la libreta de direcciones para limitar el ámbito de las búsquedas de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="f1bae-112">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="f1bae-113">Para usar el atributo **msRTCSIP-GroupingId** , escribir un script para rellenar el atributo, asignar el mismo valor para todos los usuarios que desea agrupar.</span><span class="sxs-lookup"><span data-stu-id="f1bae-113">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="f1bae-114">Por ejemplo, asignar un valor único para todos los usuarios en una unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="f1bae-114">For example, assign a single value for all the users in an OU.</span></span> 

 <span data-ttu-id="f1bae-115">**Reglas de normalización de la libreta de direcciones**</span><span class="sxs-lookup"><span data-stu-id="f1bae-115">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="f1bae-116">Si ha personalizado las reglas de normalización de la libreta de direcciones en el entorno heredado, debe migrar las reglas personalizadas a su grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="f1bae-116">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="f1bae-117">Si no personalizó las reglas de normalización de la libreta de direcciones, deberá nothing para migrar para el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="f1bae-117">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="f1bae-118">Las reglas de normalización de forma predeterminada para Skype para Business Server 2019 son los mismos que las reglas predeterminadas para la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="f1bae-118">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="f1bae-119">Siga el procedimiento más adelante en esta sección para migrar reglas de normalización personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f1bae-119">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="f1bae-120">Si su organización utiliza control remoto de llamadas y ha personalizado las reglas de normalización de la libreta de direcciones, debe realizar el procedimiento de este tema para poder usar el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f1bae-120">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="f1bae-121">El procedimiento, es necesario pertenecer al grupo RTCUniversalServerAdmins o derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f1bae-121">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="f1bae-122">**UseNormalizationRules en False**</span><span class="sxs-lookup"><span data-stu-id="f1bae-122">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="f1bae-123">Si establece el valor de **UseNormalizationRules** en False para que los usuarios pueden usar los números de teléfono tal y como están definidos en los servicios de dominio de Active Directory sin necesidad de Skype para Business Server 2019 se aplican las reglas de normalización, debe establecer el \*\* UseNormalizationRules\*\* y los parámetros de **IgnoreGenericRules** en True.</span><span class="sxs-lookup"><span data-stu-id="f1bae-123">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="f1bae-124">Siga el procedimiento descrito más adelante en esta sección para establecer estos parámetros en True.</span><span class="sxs-lookup"><span data-stu-id="f1bae-124">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="f1bae-125">Para migrar la libreta de direcciones personalizadas de reglas de normalización</span><span class="sxs-lookup"><span data-stu-id="f1bae-125">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="f1bae-126">Busque el archivo Company_Phone_Number_Normalization_Rules.txt en la raíz de la carpeta compartida de la libreta de direcciones y cópielo a la raíz de la carpeta compartida de la libreta de direcciones en su Skype para el grupo piloto Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f1bae-126">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1bae-127">Las reglas de normalización de ejemplo Libreta de direcciones se han instalado en el directorio de archivos de componente Web ABS.</span><span class="sxs-lookup"><span data-stu-id="f1bae-127">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="f1bae-128">Es la ruta de acceso **$installedDriveLetter: \Program Skype para Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="f1bae-128">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="f1bae-129">Este archivo se puede copiar a cambiar el nombre como **Company_Phone_Number_Normalization_Rules.txt** al directorio raíz de la carpeta Libreta de direcciones compartida.</span><span class="sxs-lookup"><span data-stu-id="f1bae-129">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="f1bae-130">Por ejemplo, la libreta de direcciones compartida en **$serverX**, la ruta de acceso será similar a: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="f1bae-130">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="f1bae-131">Use un editor de texto, como el Bloc de notas para abrir el archivo Company_Phone_Number_Normalization_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="f1bae-131">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="f1bae-132">Ciertos tipos de entradas no funcionarán correctamente en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f1bae-132">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="f1bae-133">Examine el archivo para los tipos de entradas descritos en este paso, editarlos según sea necesario y guardar los cambios en la carpeta compartida de la libreta de direcciones en el grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="f1bae-133">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="f1bae-134">Cadenas que incluyen requiere espacio en blanco o signos de puntuación causa reglas de normalización se lleve a cabo debido a que estos caracteres se eliminan fuera de la cadena que es la entrada a las reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="f1bae-134">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="f1bae-135">Si dispone de las cadenas que incluyen el espacio en blanco obligatorio ni signos de puntuación, debe modificar las cadenas.</span><span class="sxs-lookup"><span data-stu-id="f1bae-135">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="f1bae-136">Por ejemplo, la siguiente cadena hará que la regla de normalización se lleve a cabo:</span><span class="sxs-lookup"><span data-stu-id="f1bae-136">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="f1bae-137">La siguiente cadena no hará que la regla de normalización se lleve a cabo:</span><span class="sxs-lookup"><span data-stu-id="f1bae-137">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="f1bae-138">Para establecer UseNormalizationRules e IgnoreGenericRules en true</span><span class="sxs-lookup"><span data-stu-id="f1bae-138">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="f1bae-139">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="f1bae-139">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f1bae-140">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1bae-140">Do one of the following:</span></span>

   - <span data-ttu-id="f1bae-141">Si la implementación incluye solo Skype para Business Server 2019, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** e **IgnoreGenericRules** a True:</span><span class="sxs-lookup"><span data-stu-id="f1bae-141">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="f1bae-142">Si la implementación incluye una combinación de Skype para Business Server 2019 y una instalación heredada, ejecute el siguiente cmdlet y asígnelo a cada Skype para Business Server 2019 grupo de servidores en la topología:</span><span class="sxs-lookup"><span data-stu-id="f1bae-142">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="f1bae-143">Espere a que se producen en todos los grupos de la replicación de almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="f1bae-143">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="f1bae-144">Modifique el archivo de reglas de normalización de teléfono, "Company_Phone_Number_Normalization_Rules.txt", para la implementación borrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="f1bae-144">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="f1bae-145">El archivo está en el recurso compartido de archivos de cada Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f1bae-145">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f1bae-146">Si el archivo no está presente, a continuación, cree un archivo vacío denominado "Company_Phone_Number_Normalization_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="f1bae-146">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="f1bae-147">Espere varios minutos para todos los grupos de servidores Front-End leer los nuevos archivos.</span><span class="sxs-lookup"><span data-stu-id="f1bae-147">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="f1bae-148">Ejecute el siguiente cmdlet en cada Skype para grupo de negocio Server 2019 en su implementación:</span><span class="sxs-lookup"><span data-stu-id="f1bae-148">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


