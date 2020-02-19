---
title: 'Lync Server 2013: usar config. XML para realizar tareas de instalación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b6b06b270157bc1aa2387662229dbff3eb8f4d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Uso de config. XML para realizar tareas de instalación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Aunque la Herramienta de personalización de Office (OCT) es la principal herramienta de instalación personalizada, los administradores pueden usar el archivo Config.xml para especificar instrucciones de instalación adicionales que no estén disponibles en la OCT. Las personalizaciones que se describen a continuación solo se pueden llevar a cabo mediante el archivo Config.xml:

  - Especifique la ruta de acceso del punto de instalación de red.

  - Seleccione los productos que desea instalar.

  - Configure el registro y la ubicación del archivo de personalización de la instalación y las actualizaciones de software.

  - Especifique las opciones de instalación como, por ejemplo, el nombre de usuario.

  - Copie el origen de instalación local (LIS) en el equipo del usuario sin instalar Office.

  - Agregar o quitar idiomas de la instalación.

Le recomendamos que use el archivo config. XML para configurar la instalación silenciosa de Lync 2013.

De forma predeterminada, el archivo config. XML que se almacena en la carpeta de producto principal (por \\ejemplo, producto. WW) indica al programa de instalación que instale ese producto. Por ejemplo, el archivo config. XML de la siguiente carpeta instala Lync 2013:

  - \\\\Server\\share\\Lync15\\Lync. WW \\config. XML

Los elementos de config. XML que se usan con más frecuencia para la instalación de Lync 2013 se enumeran en la siguiente tabla.

### <a name="configxml-elements"></a>Elementos de Config.xml

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuración</p></td>
<td><p>Elemento de nivel superior (necesario). Contiene el atributo de producto, por ejemplo: Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Especifica cómo las características específicas del producto se controlan durante la instalación. Use los siguientes atributos para impedir la instalación de servicios de conectividad empresarial, que incluye componentes compartidos que interfieren con Outlook 2010:</p>
<ul>
<li><p>ID =&quot;LOBiMain&quot;</p></li>
<li><p>Estado =&quot;ausente&quot;</p></li>
<li><p>Children =&quot;forzar&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Visualización</p></td>
<td><p>El nivel de interfaz de usuario que el programa de instalación muestra al usuario. Los atributos típicos incluyen los siguientes:</p>
<ul>
<li><p>CompletionNotice =&quot;Yes&quot; | &quot;no&quot;(valor predeterminado)</p></li>
<li><p>AcceptEula =&quot;Yes&quot; | &quot;no&quot;(valor predeterminado)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Registro</p></td>
<td><p>Opciones para el tipo de registro que realiza el programa de instalación. Los atributos típicos incluyen los siguientes:</p>
<ul>
<li><p>Tipo =&quot;OFF&quot; | &quot;Standard&quot;(valor predeterminado) | &quot;Verbose&quot;</p></li>
<li><p>Template=”nombredearchivo.txt” (el nombre del archivo de registro)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Configuración</p></td>
<td><p>Especifica los valores de propiedades de Windows Installer. Los atributos típicos incluyen los siguientes:</p>
<ul>
<li><p>Setting ID =&quot;name&quot; (el nombre de la propiedad de Windows Installer)</p></li>
<li><p>Valor =&quot;valor&quot; (el valor para asignar a la propiedad)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>La ruta de acceso completa del punto de instalación de red desde la que se ejecuta la instalación. Incluye el atributo de ubicación:</p>
<ul>
<li><p>Location = "ruta de acceso"</p></li>
</ul></td>
</tr>
</tbody>
</table>


En el ejemplo siguiente se muestra un archivo config. XML para una instalación silenciosa típica de Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Encontrará información detallada sobre cómo usar el archivo config. XML para realizar tareas de instalación y mantenimiento de <https://go.microsoft.com/fwlink/p/?linkid=267514>Office en.

<div>

## <a name="to-customize-the-configxml-file"></a>Para personalizar el archivo Config.xml

1.  Abra el archivo Config.xml usando una herramienta de edición de texto como el Bloc de notas.

2.  Localice las líneas que contienen los elementos que desee cambiar.

3.  Modifique la entrada de elemento con las opciones silenciosas que desea usar. Asegúrese de quitar los delimitadores de comentario, "\<\!--" y "--\>". Por ejemplo, utilice la sintaxis siguiente:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Guarde el archivo Config.xml.

</div>

</div>

<span> </span>

</div>

</div>

</div>

