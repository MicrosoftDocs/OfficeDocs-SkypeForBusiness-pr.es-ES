---
title: Usar opciones de línea de comandos de configuración
TOCTitle: Usar opciones de línea de comandos de configuración
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48276110
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar opciones de línea de comandos de configuración

 

_**Última modificación del tema:** 2016-12-08_

La línea de comandos de Setup.exe se utiliza para muy pocas operaciones en la instalación de Office. Normalmente, en vez de usar las opciones de línea de comandos del programa de instalación, utilizará la Herramienta de personalización de Office y el archivo Config.xml para la configuración de productos y personalización de características.

La línea de comandos de Setup.exe de Office reconoce las opciones de línea de comandos que se detallan en la siguiente tabla.

### Opciones de línea de comandos del programa de instalación de Office

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opción de línea de comandos del programa de instalación</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Ejecuta la Herramienta de personalización del Office para crear un archivo de personalización del programa de instalación (archivo .msp).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>Aplica a la instalación el archivo de personalización del programa de instalación especificado. Puede especificar una ruta de acceso a un archivo de personalización (archivo .msp) específico o a la carpeta donde guarde los archivos de personalización.</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>Especifica el archivo Config.xml que el programa de instalación utiliza durante la instalación. Utilice la opción /config para especificar el archivo Config.xml que personalizó para las instalaciones de Lync 2013, como por ejemplo el siguiente: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>Se utiliza con un archivo Config.xml modificado para ejecutar el programa de instalación en modo de mantenimiento y hacer cambios en una instalación de Office existente. Por ejemplo, puede usar la opción /modify para agregar o quitar características de Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>Ejecuta el programa de instalación desde el equipo del usuario para reparar Lync.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>Ejecuta el programa de instalación para quitar Lync desde el equipo del usuario.</p></td>
</tr>
</tbody>
</table>


Para obtener información más detallada acerca de cómo usar las opciones de línea de comandos del programa de instalación, consulte [http://go.microsoft.com/fwlink/?linkid=267515\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=267515%26clcid=0xc0a).

