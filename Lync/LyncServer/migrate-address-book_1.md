---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66b18a747de8461e54b58f07f680b2558359a359
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrar la Libreta de direcciones

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

**Para migrar reglas de normalización personalizadas de la libreta de direcciones**

1.  Busque el archivo\_.\_txt\_de\_reglas de normalización de números de teléfono de la compañía en la raíz de la carpeta compartida de la libreta de direcciones y cópielo en la raíz de la carpeta compartida de la libreta de direcciones en el grupo piloto de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Las reglas de normalización de la libreta de direcciones de muestra se instalaron en el directorio de archivos de componentes web de ABS. La ruta es <STRONG>$installedDriveLetter:\Archivos de programa\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>. Este archivo se puede copiar y cambiar de &nbsp;nombre como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;al directorio raíz de la carpeta compartida de la libreta de direcciones. Por ejemplo, la libreta de direcciones compartida <STRONG></STRONG>en $serverX&nbsp;, la ruta de acceso será similar a: <STRONG> \\$serverX \LyncFileShare\2-webservices-1\ABFiles</STRONG>.

    
    </div>

2.  Use un editor de texto, como el Bloc de notas, para\_abrir\_el\_archivo\_rules. txt de normalización de números de teléfono de la compañía.

3.  Ciertos tipos de entradas no funcionarán correctamente en Lync Server 2013. Busque en el archivo los tipos de entradas que se describen en este paso, modifíquelos como sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones de su grupo piloto.
    
    Las cadenas que contienen puntuación o espacios en blanco necesarios provocan errores en las reglas de normalización, ya que estos caracteres se quitan de la cadena que se incluye en las reglas de normalización. Si tiene cadenas que incluyen puntuación o espacios en blanco necesarios, deberá modificarlas. Por ejemplo, la siguiente cadena generará un error en la regla de normalización:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La siguiente cadena no provocará errores en la regla de normalización:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

