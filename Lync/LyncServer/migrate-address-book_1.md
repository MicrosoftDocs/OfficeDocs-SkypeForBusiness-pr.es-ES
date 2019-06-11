---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dff13c31ecf203d6e6e4b60c22a3792475e403f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="e43d8-102">Migrar la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="e43d8-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e43d8-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e43d8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e43d8-104">**Para migrar reglas de normalización personalizadas de la libreta de direcciones**</span><span class="sxs-lookup"><span data-stu-id="e43d8-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="e43d8-105">Busque el archivo\_.\_txt\_de\_la normalización de números de teléfono de la empresa en la raíz de la carpeta compartida de la libreta de direcciones y cópiela en la raíz de la carpeta compartida de la libreta de direcciones del grupo de pruebas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e43d8-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e43d8-106">Las reglas de normalización de libreta de direcciones de muestra se han instalado en el directorio de archivos de ABS web Component.</span><span class="sxs-lookup"><span data-stu-id="e43d8-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="e43d8-107">La ruta de acceso es <STRONG>$installedDriveLetter: \Archivos de Programa\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e43d8-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="e43d8-108">Este archivo se puede copiar y cambiar de &nbsp;nombre como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;para el directorio raíz de la carpeta compartida de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="e43d8-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="e43d8-109">Por ejemplo, la libreta de direcciones compartida <STRONG></STRONG>en $serverX&nbsp;, la ruta de acceso será similar a: <STRONG> \\$serverX \LyncFileShare\2-webservices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e43d8-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="e43d8-110">Use un editor de texto, como el Bloc de notas, para\_abrir\_el\_archivo\_rules. txt de la normalización de números de teléfono de la empresa.</span><span class="sxs-lookup"><span data-stu-id="e43d8-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="e43d8-111">Algunos tipos de entradas no funcionarán correctamente en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e43d8-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="e43d8-112">Busque en el archivo los tipos de entradas que se describen en este paso, edítelo según sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones del grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="e43d8-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="e43d8-113">Las cadenas que incluyen el espacio en blanco o la puntuación obligatorios producen errores en las reglas de normalización, ya que estos caracteres se eliminan de la cadena introducida en las reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="e43d8-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="e43d8-114">Si tiene cadenas que incluyen el espacio en blanco o la puntuación necesarios, debe modificar las cadenas.</span><span class="sxs-lookup"><span data-stu-id="e43d8-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="e43d8-115">Por ejemplo, la siguiente cadena haría que la regla de normalra fallara:</span><span class="sxs-lookup"><span data-stu-id="e43d8-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="e43d8-116">La cadena siguiente no provocará errores en la regla de normalización:</span><span class="sxs-lookup"><span data-stu-id="e43d8-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

