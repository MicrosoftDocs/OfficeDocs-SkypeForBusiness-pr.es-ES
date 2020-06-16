---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee0dc4d50fb3b60d4f6a9581d497df11da630122
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrar la Libreta de direcciones

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

En general, la libreta de direcciones 2010 de Lync Server se migra junto con el resto de la topología. Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno de Lync Server 2010:

  - Estableció la propiedad **PartitionbyOU** de WMI para agrupar entradas de la libreta de direcciones por unidad organizativa.

  - Personalizó las reglas de normalización de la libreta de direcciones.

  - Modificó el valor predeterminado del parámetro **UseNormalizationRules** a False.

**Entradas de la Libreta de direcciones agrupadas**

If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.

**Reglas de normalización de la Libreta de direcciones**

Si ha personalizado las reglas de normalización de la libreta de direcciones en su entorno de Lync Server 2010, debe migrar las reglas personalizadas al grupo piloto. Si no ha personalizado las reglas de normalización de la Libreta de direcciones, no tendrá nada que migrar al servicio de la Libreta de direcciones. Las reglas de normalización predeterminadas para Lync Server 2013 son las mismas que las reglas predeterminadas para Lync Server 2010. Siga el procedimiento que se describe más adelante en esta sección para migrar reglas de normalización personalizadas.

<div>


> [!NOTE]  
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.



</div>

**Definición de UseNormalizationRules en False**

Si establece el valor de **UseNormalizationRules** en false para que los usuarios puedan usar números de teléfono tal y como se definen en servicios de dominio de Active Directory sin tener Lync Server 2013 aplicar reglas de normalización, debe establecer los parámetros **UseNormalizationRules** y **IgnoreGenericRules** en true. Siga el procedimiento que se describe más adelante en esta sección para establecer estos parámetros en True.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar reglas de normalización personalizadas de la libreta de direcciones

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

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para establecer UseNormalizationRules e IgnoreGenericRules en True

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Realice una de las acciones siguientes:
    
      - Si su implementación incluye solo Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** y **IgnoreGenericRules** a true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores de Lync Server 2013 en la topología:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Espere a que se produzca la replicación del almacén de administración central en todos los grupos.

4.  Modifique el archivo de reglas de normalización de teléfono, " \_ \_ \_ normalización \_ de números de teléfono de la empresaRules.txt", para que la implementación borre el contenido. El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de 2013 de Lync Server. Si el archivo no está presente, cree un archivo vacío denominado "normalización del número de teléfono de la compañía \_ \_ \_ \_Rules.txt".

5.  Espere varios minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.

6.  Ejecute el siguiente cmdlet en cada grupo de servidores de Lync Server 2013 de la implementación:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

