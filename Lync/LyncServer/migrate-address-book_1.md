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
ms.openlocfilehash: e2c904a122f781da08c92c6b1123cfeb1944dd2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrar la libreta de direcciones

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

**Para migrar reglas de normalización personalizadas de la libreta de direcciones**

1.  Busque el archivo\_.\_txt\_de\_la normalización de números de teléfono de la empresa en la raíz de la carpeta compartida de la libreta de direcciones y cópiela en la raíz de la carpeta compartida de la libreta de direcciones del grupo de pruebas de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Las reglas de normalización de libreta de direcciones de muestra se han instalado en el directorio de archivos de ABS web Component. La ruta de acceso es <STRONG>$installedDriveLetter: \Archivos de Programa\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt</STRONG>. Este archivo se puede copiar y cambiar de &nbsp;nombre como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;al directorio raíz de la carpeta compartida de la libreta de direcciones. Por ejemplo, la libreta de direcciones compartida <STRONG></STRONG>en $serverX&nbsp;, la ruta de acceso será similar a: <STRONG> \\$serverX \LyncFileShare\2-webservices-1\ABFiles</STRONG>.

    
    </div>

2.  Use un editor de texto, como el Bloc de notas, para\_abrir\_el\_archivo\_rules. txt de la normalización de números de teléfono de la empresa.

3.  Algunos tipos de entradas no funcionarán correctamente en Lync Server 2013. Busque en el archivo los tipos de entradas que se describen en este paso, edítelo según sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones del grupo piloto.
    
    Las cadenas que incluyen el espacio en blanco o la puntuación obligatorios producen errores en las reglas de normalización, ya que estos caracteres se eliminan de la cadena introducida en las reglas de normalización. Si tiene cadenas que incluyen el espacio en blanco o la puntuación necesarios, debe modificar las cadenas. Por ejemplo, la siguiente cadena haría que la regla de normalra fallara:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La cadena siguiente no provocará errores en la regla de normalización:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

