---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937bf9dfff07591ea12a2c78604ab82fa34e97f6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrar la Libreta de direcciones

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

**Para migrar reglas de normalización personalizadas de la libreta de direcciones**

1.  Busque el \_ \_ \_ archivoRules.txt de normalización de números de teléfono de la empresa \_ en la raíz de la carpeta compartida de la libreta de direcciones y cópielo en la raíz de la carpeta compartida de la libreta de direcciones en el grupo piloto de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Las reglas de normalización de la libreta de direcciones de muestra se instalaron en el directorio de archivos de componentes web de ABS. La ruta es <STRONG>$installedDriveLetter:\Archivos de programa\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>. Este archivo se puede copiar y cambiar de nombre como &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; al directorio raíz de la carpeta compartida de la libreta de direcciones. Por ejemplo, la libreta de direcciones compartida en <STRONG>$serverX</STRONG>, &nbsp; la ruta de acceso será similar a: <STRONG> \\ $serverX \LyncFileShare\2-webservices-1\ABFiles</STRONG>.

    
    </div>

2.  Use un editor de texto, como el Bloc de notas, para abrir el archivo de normalización de números de teléfono de la compañía \_ \_ \_ \_Rules.txt.

3.  Ciertos tipos de entradas no funcionarán correctamente en Lync Server 2013. Busque en el archivo los tipos de entradas que se describen en este paso, modifíquelos como sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones de su grupo piloto.
    
    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La siguiente cadena no provocará errores en la regla de normalización:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

