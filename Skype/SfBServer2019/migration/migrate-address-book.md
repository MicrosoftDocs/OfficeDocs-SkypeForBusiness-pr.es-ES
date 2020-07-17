---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno heredado:'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752842"
---
# <a name="migrate-address-book"></a><span data-ttu-id="e061b-104">Migrar la Libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="e061b-104">Migrate Address Book</span></span>

<span data-ttu-id="e061b-105">En general, la libreta de direcciones se migra junto con el resto de la topología.</span><span class="sxs-lookup"><span data-stu-id="e061b-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="e061b-106">Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno heredado:</span><span class="sxs-lookup"><span data-stu-id="e061b-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="e061b-107">Personalizó las reglas de normalización de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e061b-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="e061b-108">Modificó el valor predeterminado del parámetro **UseNormalizationRules** a False.</span><span class="sxs-lookup"><span data-stu-id="e061b-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="e061b-109">**Reglas de normalización de la Libreta de direcciones**</span><span class="sxs-lookup"><span data-stu-id="e061b-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="e061b-110">Si ha personalizado las reglas de normalización de la libreta de direcciones en el entorno heredado, deberá migrar las reglas personalizadas al grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="e061b-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="e061b-111">Si no ha personalizado las reglas de normalización de la Libreta de direcciones, no tendrá nada que migrar al servicio de la Libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e061b-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="e061b-112">Las reglas de normalización predeterminadas de Skype empresarial Server 2019 son las mismas que las reglas predeterminadas para la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="e061b-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="e061b-113">Siga el procedimiento que se describe más adelante en esta sección para migrar reglas de normalización personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e061b-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="e061b-p104">Si su organización usa el control remoto de llamadas y personalizó las reglas de normalización de la libreta de direcciones, deberá llevar a cabo el procedimiento que se describe en este tema para poder usar el control remoto de llamadas. El procedimiento requiere pertenecer al grupo RTCUniversalServerAdmins o contar con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="e061b-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="e061b-116">**Definición de UseNormalizationRules en False**</span><span class="sxs-lookup"><span data-stu-id="e061b-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="e061b-117">Si establece el valor de **UseNormalizationRules** en false para que los usuarios puedan usar los números de teléfono tal y como se definen en los servicios de dominio de Active Directory sin que Skype empresarial Server 2019 aplique reglas de normalización, deberá establecer los parámetros **UseNormalizationRules** y **IgnoreGenericRules** en true.</span><span class="sxs-lookup"><span data-stu-id="e061b-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="e061b-118">Siga el procedimiento que se describe más adelante en esta sección para establecer estos parámetros en True.</span><span class="sxs-lookup"><span data-stu-id="e061b-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="e061b-119">Para migrar reglas de normalización personalizadas de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="e061b-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="e061b-120">Busque el archivo Company_Phone_Number_Normalization_Rules.txt en la raíz de la carpeta compartida de la libreta de direcciones y cópielo en la raíz de la carpeta compartida de la libreta de direcciones en el grupo piloto de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e061b-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e061b-121">Las reglas de normalización de la libreta de direcciones de muestra se instalaron en el directorio de archivos de componentes web de ABS.</span><span class="sxs-lookup"><span data-stu-id="e061b-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="e061b-122">La ruta de acceso es **$installedDriveLetter: \Archivos de Programa\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="e061b-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="e061b-123">Este archivo se puede copiar y cambiar de nombre como **Company_Phone_Number_Normalization_Rules.txt** al directorio raíz de la carpeta compartida de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e061b-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="e061b-124">Por ejemplo, la libreta de direcciones compartida en **$serverX**, la ruta de acceso será similar a: \*\* \\ $serverX \SkypeForBusiness-FileShare\2-webservices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="e061b-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="e061b-125">Use un editor de texto (como el Bloc de notas) para abrir el archivo Company_Phone_Number_Normalization_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="e061b-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="e061b-126">Ciertos tipos de entradas no funcionarán correctamente en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e061b-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="e061b-127">Busque en el archivo los tipos de entradas que se describen en este paso, modifíquelos como sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones de su grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="e061b-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="e061b-p108">Las cadenas que contienen puntuación o espacios en blanco necesarios provocan errores en las reglas de normalización, ya que estos caracteres se quitan de la cadena que se incluye en las reglas de normalización. Si tiene cadenas que incluyen puntuación o espacios en blanco necesarios, deberá modificarlas. Por ejemplo, la siguiente cadena generará un error en la regla de normalización:</span><span class="sxs-lookup"><span data-stu-id="e061b-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="e061b-131">La siguiente cadena no provocará errores en la regla de normalización:</span><span class="sxs-lookup"><span data-stu-id="e061b-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="e061b-132">Para establecer UseNormalizationRules e IgnoreGenericRules en True</span><span class="sxs-lookup"><span data-stu-id="e061b-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="e061b-133">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="e061b-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e061b-134">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e061b-134">Do one of the following:</span></span>

   - <span data-ttu-id="e061b-135">Si su implementación solo incluye Skype empresarial Server 2019, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** y **IgnoreGenericRules** a true:</span><span class="sxs-lookup"><span data-stu-id="e061b-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="e061b-136">Si su implementación incluye una combinación de Skype empresarial Server 2019 y una instalación heredada, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores de Skype empresarial Server 2019 en la topología:</span><span class="sxs-lookup"><span data-stu-id="e061b-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="e061b-137">Espere a que se produzca la replicación del almacén de administración central en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="e061b-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="e061b-138">Modifique el archivo de reglas de normalización del teléfono, "Company_Phone_Number_Normalization_Rules.txt", de su implementación para borrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="e061b-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="e061b-139">El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e061b-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e061b-140">Si no encuentra el archivo, cree un archivo vacío con el nombre "Company_Phone_Number_Normalization_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="e061b-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="e061b-141">Espere varios minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.</span><span class="sxs-lookup"><span data-stu-id="e061b-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="e061b-142">Ejecute el siguiente cmdlet en cada grupo de servidores de Skype empresarial Server 2019 en su implementación:</span><span class="sxs-lookup"><span data-stu-id="e061b-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


