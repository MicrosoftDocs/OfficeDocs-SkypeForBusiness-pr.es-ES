---
title: Migrar la libreta de direcciones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2293b7ad3e5ac14071bae4d5ecb935c24cfbb335
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrar la libreta de direcciones

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

En general, la libreta de direcciones de Lync Server 2010 se migra junto con el resto de la topología. Sin embargo, es posible que tenga que realizar algunos pasos posteriores a la migración si ha personalizado lo siguiente en el entorno de Lync Server 2010:

  - Establezca la propiedad WMI **PartitionbyOU** en agrupar las entradas de la libreta de direcciones por unidad organizativa (OU).

  - Personalizar las reglas de normalización de la libreta de direcciones.

  - Cambió el valor predeterminado del parámetro **UseNormalizationRules** a false.

**Entradas de la libreta de direcciones agrupadas**

Si establece la propiedad WMI de **PartitionbyOU** en true para crear libretas de direcciones para cada ou, tendrá que establecer el atributo **msRTCSIP-GroupingId** de Active Directory en usuarios y contactos si desea continuar agrupando las entradas de la libreta de direcciones. Es posible que desee agrupar las entradas de la libreta de direcciones para limitar el ámbito de las búsquedas en la libreta de direcciones. Para usar el atributo **msRTCSIP-GroupingId** , escriba un script para rellenar el atributo y asigne el mismo valor a todos los usuarios que desee agrupar. Por ejemplo, asigne un único valor para todos los usuarios de una unidad organizativa.

**Reglas de normalización de libreta de direcciones**

Si ha personalizado las reglas de normalización de la libreta de direcciones en el entorno de Lync Server 2010, debe migrar las reglas personalizadas a su grupo piloto. Si no ha personalizado las reglas de normalización de la libreta de direcciones, no tiene nada que migrar para el servicio de libreta de direcciones. Las reglas de normalización predeterminadas para Lync Server 2013 son las mismas que las reglas predeterminadas para Lync Server 2010. Siga el procedimiento más adelante en esta sección para migrar reglas de normalización personalizadas.

<div>


> [!NOTE]  
> Si su organización usa el control remoto de llamadas y ha personalizado las reglas de normalización de la libreta de direcciones, debe realizar el procedimiento de este tema antes de poder usar el control remoto de llamadas. El procedimiento requiere ser miembro del grupo RTCUniversalServerAdmins o derechos equivalentes.



</div>

**UseNormalizationRules establecido en falso**

Si establece el valor de **UseNormalizationRules** en false para que los usuarios puedan usar números de teléfono a medida que se definen en servicios de dominio de Active Directory sin que Lync Server 2013 aplique reglas de normalización, debe establecer la **UseNormalizationRules **y **IgnoreGenericRules** parámetros a true. Siga el procedimiento más adelante en esta sección para establecer estos parámetros en true.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar reglas de normalización personalizadas de la libreta de direcciones

1.  Busque el archivo\_.\_txt\_de\_la normalización de números de teléfono de la empresa en la raíz de la carpeta compartida de la libreta de direcciones y cópiela en la raíz de la carpeta compartida de la libreta de direcciones del grupo de pruebas de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Las reglas de normalización de libreta de direcciones de muestra se han instalado en el directorio de archivos de ABS web Component. La ruta de acceso es <STRONG>$installedDriveLetter: \Archivos de Programa\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>. Este archivo se puede copiar y cambiar de &nbsp;nombre como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;para el directorio raíz de la carpeta compartida de la libreta de direcciones. Por ejemplo, la libreta de direcciones compartida <STRONG></STRONG>en $serverX&nbsp;, la ruta de acceso será similar a: <STRONG> \\$serverX \LyncFileShare\2-webservices-1\ABFiles</STRONG>.

    
    </div>

2.  Use un editor de texto, como el Bloc de notas, para\_abrir\_el\_archivo\_rules. txt de la normalización de números de teléfono de la empresa.

3.  Algunos tipos de entradas no funcionarán correctamente en Lync Server 2013. Busque en el archivo los tipos de entradas que se describen en este paso, edítelo según sea necesario y guarde los cambios en la carpeta compartida de la libreta de direcciones del grupo piloto.
    
    Las cadenas que incluyen el espacio en blanco o la puntuación obligatorios producen errores en las reglas de normalización, ya que estos caracteres se eliminan de la cadena introducida en las reglas de normalización. Si tiene cadenas que incluyen el espacio en blanco o la puntuación necesarios, debe modificar las cadenas. Por ejemplo, la siguiente cadena haría que la regla de normalra fallara:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La cadena siguiente no provocará errores en la regla de normalización:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para establecer UseNormalizationRules y IgnoreGenericRules en true

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Siga uno de estos pasos:
    
      - Si su implementación solo incluye Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de **UseNormalizationRules** y **IgnoreGenericRules** a true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores de Lync Server 2013 en la topología:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Espere a que se produzca la replicación del almacén central de administración en todos los grupos.

4.  Modifique el archivo de reglas de normalización de\_teléfono\_,\_"\_reglas de normalización de número de teléfono de la empresa. txt", para que la implementación borre el contenido. El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de Lync Server 2013. Si el archivo no está presente, cree un archivo vacío con el nombre "\_regla\_de\_normalización\_de números de teléfono de la empresa. txt".

5.  Espere unos minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.

6.  Ejecute el siguiente cmdlet en cada grupo de servidores de Lync Server 2013 de su implementación:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

