---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'En general, la libreta de direcciones se migra junto con el resto de la topología. Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en su entorno heredado:'
ms.openlocfilehash: 4263ae5bff60859cc9606a3683a3a03b0d2d4c35
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307122"
---
# <a name="migrate-address-book"></a><span data-ttu-id="b78f1-104">Migrar la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="b78f1-104">Migrate Address Book</span></span>

<span data-ttu-id="b78f1-105">En general, la libreta de direcciones se migra junto con el resto de la topología.</span><span class="sxs-lookup"><span data-stu-id="b78f1-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="b78f1-106">Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en su entorno heredado:</span><span class="sxs-lookup"><span data-stu-id="b78f1-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="b78f1-107">Personalizar las reglas de normalización de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="b78f1-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="b78f1-108">Cambió el valor predeterminado del parámetro **UseNormalizationRules** a false.</span><span class="sxs-lookup"><span data-stu-id="b78f1-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="b78f1-109">**Reglas de normalización de libreta de direcciones**</span><span class="sxs-lookup"><span data-stu-id="b78f1-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="b78f1-110">Si ha personalizado las reglas de normalización de la libreta de direcciones en el entorno heredado, debe migrar las reglas personalizadas a su grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="b78f1-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="b78f1-111">Si no ha personalizado las reglas de normalización de la libreta de direcciones, no tiene nada que migrar para el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="b78f1-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="b78f1-112">Las reglas de normalización predeterminadas para Skype empresarial Server 2019 son las mismas que las reglas predeterminadas para la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="b78f1-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="b78f1-113">Siga el procedimiento más adelante en esta sección para migrar reglas de normalización personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b78f1-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="b78f1-114">Si su organización usa el control remoto de llamadas y ha personalizado las reglas de normalización de la libreta de direcciones, debe realizar el procedimiento de este tema antes de poder usar el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b78f1-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="b78f1-115">El procedimiento requiere ser miembro del grupo RTCUniversalServerAdmins o derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="b78f1-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="b78f1-116">**UseNormalizationRules establecido en falso**</span><span class="sxs-lookup"><span data-stu-id="b78f1-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="b78f1-117">Si establece el valor de **UseNormalizationRules** en false para que los usuarios puedan usar números de teléfono a medida que se definen en servicios de dominio de Active Directory sin tener Skype empresarial Server 2019 aplicar reglas de normalización, debe establecer la \*\* \*\*Los parámetros UseNormalizationRules y **IgnoreGenericRules** son true.</span><span class="sxs-lookup"><span data-stu-id="b78f1-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="b78f1-118">Siga el procedimiento más adelante en esta sección para establecer estos parámetros en true.</span><span class="sxs-lookup"><span data-stu-id="b78f1-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="b78f1-119">Para migrar reglas de normalización personalizadas de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="b78f1-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="b78f1-120">Busque el archivo Company_Phone_Number_Normalization_Rules. txt en la raíz de la carpeta compartida de la libreta de direcciones y cópielo en la raíz de la carpeta compartida de la libreta de direcciones en el repositorio piloto de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b78f1-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b78f1-121">Las reglas de normalización de libreta de direcciones de muestra se han instalado en el directorio de archivos de ABS web Component.</span><span class="sxs-lookup"><span data-stu-id="b78f1-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="b78f1-122">La ruta de acceso es **$installedDriveLetter: \Archivos de Programa\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**.</span><span class="sxs-lookup"><span data-stu-id="b78f1-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="b78f1-123">Este archivo se puede copiar y cambiar de nombre como **Company_Phone_Number_Normalization_Rules. txt** para el directorio raíz de la carpeta compartida de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="b78f1-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="b78f1-124">Por ejemplo, la libreta de direcciones compartida en **$serverX**, la ruta de acceso será similar a: \*\* \\$serverX \SkypeForBusiness-FileShare\2-webservices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="b78f1-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="b78f1-125">Use un editor de texto, como el Bloc de notas, para abrir el archivo Company_Phone_Number_Normalization_Rules. txt.</span><span class="sxs-lookup"><span data-stu-id="b78f1-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="b78f1-126">Ciertos tipos de entradas no funcionarán correctamente en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b78f1-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="b78f1-127">Busque en el archivo los tipos de entradas que se describen en este paso, edítelo según sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones del grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="b78f1-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="b78f1-128">Las cadenas que incluyen el espacio en blanco o la puntuación obligatorios producen errores en las reglas de normalización, ya que estos caracteres se eliminan de la cadena introducida en las reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="b78f1-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="b78f1-129">Si tiene cadenas que incluyen el espacio en blanco o la puntuación necesarios, debe modificar las cadenas.</span><span class="sxs-lookup"><span data-stu-id="b78f1-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="b78f1-130">Por ejemplo, la siguiente cadena haría que la regla de normalra fallara:</span><span class="sxs-lookup"><span data-stu-id="b78f1-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="b78f1-131">La cadena siguiente no provocará errores en la regla de normalización:</span><span class="sxs-lookup"><span data-stu-id="b78f1-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="b78f1-132">Para establecer UseNormalizationRules y IgnoreGenericRules en true</span><span class="sxs-lookup"><span data-stu-id="b78f1-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="b78f1-133">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="b78f1-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b78f1-134">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b78f1-134">Do one of the following:</span></span>

   - <span data-ttu-id="b78f1-135">Si su implementación solo incluye Skype empresarial Server 2019, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** y **IgnoreGenericRules** a verdadero:</span><span class="sxs-lookup"><span data-stu-id="b78f1-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="b78f1-136">Si su implementación incluye una combinación de Skype empresarial Server 2019 y una instalación heredada, ejecute el siguiente cmdlet y asígnelo a cada grupo de Skype empresarial Server 2019 en la topología:</span><span class="sxs-lookup"><span data-stu-id="b78f1-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="b78f1-137">Espere a que se produzca la replicación del almacén central de administración en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="b78f1-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="b78f1-138">Modifique el archivo de reglas de normalización de teléfono, "Company_Phone_Number_Normalization_Rules. txt", para que su implementación borre el contenido.</span><span class="sxs-lookup"><span data-stu-id="b78f1-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="b78f1-139">El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="b78f1-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b78f1-140">Si el archivo no está presente, cree un archivo vacío denominado "Company_Phone_Number_Normalization_Rules. txt".</span><span class="sxs-lookup"><span data-stu-id="b78f1-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="b78f1-141">Espere unos minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.</span><span class="sxs-lookup"><span data-stu-id="b78f1-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="b78f1-142">Ejecute el siguiente cmdlet en cada grupo de servidores de Skype empresarial 2019 de su implementación:</span><span class="sxs-lookup"><span data-stu-id="b78f1-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


