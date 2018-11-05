---
title: Usar Config.xml para realizar tareas de instalación
TOCTitle: Usar Config.xml para realizar tareas de instalación
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48274344
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar Config.xml para realizar tareas de instalación

 

_**Última modificación del tema:** 2016-12-08_

Aunque la Herramienta de personalización de Office (OCT) es la principal herramienta de instalación personalizada, los administradores pueden usar el archivo Config.xml para especificar instrucciones de instalación adicionales que no estén disponibles en la OCT. Las personalizaciones que se describen a continuación solo se pueden llevar a cabo mediante el archivo Config.xml:

  - Especifique la ruta de acceso del punto de instalación de red.

  - Seleccione los productos que desea instalar.

  - Configure el registro y la ubicación del archivo de personalización de la instalación y las actualizaciones de software.

  - Especifique las opciones de instalación como, por ejemplo, el nombre de usuario.

  - Copie el origen de instalación local (LIS) en el equipo del usuario sin instalar Office.

  - Agregue o quite idiomas de la instalación.

Se recomienda usar el archivo Config.xml para configurar instalaciones silenciosas de Lync 2013.

De forma predeterminada, el archivo Config.xml almacenado en la carpeta principal del producto (por ejemplo, \\*producto*.WW) dirige el programa de instalación para instalar este producto. Por ejemplo, el archivo Config.xml en la carpeta siguiente instala Lync 2013:

  - \\\\server\\share\\Lync15\\Lync.WW \\Config.xml

Los elementos de Config.xml usados más comúnmente para la instalación de Lync 2013 se incluyen en la tabla siguiente.

### Elementos de Config.xml

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
<td><p>Especifica cómo las características específicas del producto se controlan durante la instalación. Utilice los siguientes atributos para impedir la instalación de Servicios de conectividad empresarial, que incluye componentes compartidos que interfieren con Outlook 2010:</p>
<ul>
<li><p>Id=&quot;LOBiMain&quot;</p></li>
<li><p>State=&quot;Absent&quot;</p></li>
<li><p>Children=&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Visualización</p>
<p></p></td>
<td><p>El nivel de interfaz de usuario que el programa de instalación muestra al usuario. Los atributos típicos incluyen los siguientes:</p>
<ul>
<li><p>CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(predeterminado)</p></li>
<li><p>AcceptEula=&quot;Yes&quot; | &quot;No&quot;(predeterminado)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Registro</p></td>
<td><p>Opciones para el tipo de registro que realiza el programa de instalación. Los atributos típicos incluyen los siguientes:</p>
<ul>
<li><p>Type =&quot;Off&quot; | &quot;Standard&quot;(predeterminado) | &quot;Verbose&quot;</p></li>
<li><p>Template=”<em>nombredearchivo</em>.txt” (el nombre del archivo de registro)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Configuración</p></td>
<td><p>Especifica los valores de propiedades de Windows Installer. Los atributos típicos incluyen los siguientes:</p>
<ul>
<li><p>Setting Id=&quot;<em>nombre</em>&quot; (el nombre de la propiedad de Windows Installer)</p></li>
<li><p>Value=&quot;<em>valor</em>&quot; (el valor para asignar a la propiedad)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>La ruta de acceso completa del punto de instalación de red desde la que se ejecuta la instalación. Incluye el atributo de ubicación:</p>
<ul>
<li><p>Location=”<em>rutadeacceso</em>”</p></li>
</ul></td>
</tr>
</tbody>
</table>


En el ejemplo siguiente se muestra un archivo Config.xml para una instalación silenciosa típica de Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Encontrará información detallada sobre el uso del archivo Config.xml para llevar a cabo tareas de instalación y mantenimiento de Office en [http://go.microsoft.com/fwlink/?linkid=267514\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=267514%26clcid=0xc0a).

## Para personalizar el archivo Config.xml

1.  Abra el archivo Config.xml usando una herramienta de edición de texto como el Bloc de notas.

2.  Localice las líneas que contienen los elementos que desee cambiar.

3.  Modifique la entrada de elemento con las opciones silenciosas que desea usar. Asegúrese de que quita los delimitadores de comentario, "\<\!--" and "--\>". Por ejemplo, utilice la sintaxis siguiente:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Guarde el archivo Config.xml.

