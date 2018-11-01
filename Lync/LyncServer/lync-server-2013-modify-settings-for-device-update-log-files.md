---
title: 'Modificar la configuración de archivos de registro de actualización de dispositivos'
TOCTitle: Modificar la configuración de los archivos de registro de actualización de dispositivos
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48276133
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificar la configuración de los archivos de registro de actualización de dispositivos

 

_**Última modificación del tema:** 2015-03-09_

Puede cambiar la configuración de cómo se recopila la información de actualización de dispositivos en su organización con Panel de control de Lync Server o Shell de administración de Lync Server. La tabla siguiente muestra las opciones de configuración que se pueden cambiar y las herramientas usadas para tal fin.

La configuración de registros se puede cambiar y aplicar de forma global o por sitio.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para cambiar</th>
<th>Use</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>El tamaño máximo (en bytes) de un archivo de registro</p></td>
<td><p>Panel de control de Lync Server</p>
<p>o bien</p>
<p>Shell de administración de Lync Server</p></td>
</tr>
<tr class="even">
<td><p>La cantidad máxima de información (en bytes) que se puede guardar en la caché</p></td>
<td><p>Panel de control de Lync Server</p>
<p>o bien</p>
<p>Shell de administración de Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>La frecuencia (en minutos) con la que se escribe información de la caché en el archivo de registro</p></td>
<td><p>Panel de control de Lync Server</p>
<p>o bien</p>
<p>Shell de administración de Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Período de tiempo (en días) que se conservan los archivos de registro</p></td>
<td><p>Panel de control de Lync Server</p>
<p>o bien</p>
<p>Shell de administración de Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Hora del día en que se comprueba si hay archivos expirados que se deben eliminar</p></td>
<td><p>Shell de administración de Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Extensiones de archivos de registros permitidos</p></td>
<td><p>Shell de administración de Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Tipos de archivos de registro que se deben conservar</p></td>
<td><p>Shell de administración de Lync Server</p></td>
</tr>
</tbody>
</table>


## Para cambiar la configuración de registros con Panel de control de Lync Server

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de registros de dispositivos**.

3.  En la página **Configuración de registros de dispositivos**, haga doble clic en la configuración que desea cambiar.

4.  En el cuadro de diálogo **Editar configuración de registros**, cambie cualquiera de los parámetros siguientes:
    
      - **Tamaño máximo de archivo (bytes)**   Especifica el tamaño máximo de archivo que puede alcanzar un archivo de registro antes de ser depurado. El valor predeterminado es 1.024.000 (1 MB).
    
      - **Tamaño máximo de caché (bytes)**Indica la cantidad máxima de información (en bytes) que se puede almacenar en la memoria caché del archivo de registro antes de que deba borrarse esa memoria caché y que los datos deban escribirse en un archivo de registro. El valor predeterminado es 512.000 (0,5 MB).
    
      - **Número de minutos antes de vaciar caché (1-60)**   Indica con qué frecuencia se escribe en el archivo de registro la información almacenada en la memoria caché del archivo de registro. Una vez se ha registrado la información, la memoria caché se borra. El valor predeterminado es cinco minutos.
    
      - **Número de días que mantener los archivos de registros (1-365)**   Especifica el número de días que se mantienen los archivos de registro antes de su depuración. El valor predeterminado es 10 días.

5.  Haga clic en **Confirmar**.

## Cambio de la configuración de registros con cmdlets de Windows PowerShell Cmdlets

La configuración del archivo de registro de actualización de dispositivos se puede cambiar con Windows PowerShell y el cmdlet **Set-CsDeviceUpdateConfiguration**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



Los ejemplos siguientes muestran un par de modos en los que puede usar **Set-CsDeviceUpdateConfiguration** para cambiar la configuración.

## Para cambiar el tamaño máximo del archivo de registro y el intervalo de limpieza del registro

  - El siguiente comando cambia la configuración del registro de actualización de dispositivos aplicada al sitio de Redmond. En este ejemplo, el tamaño máximo del archivo de registro está establecido en 204.800 bytes y el intervalo de limpieza del registro está establecido en 14 días.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

## Para cambiar la hora del día en la que se limpia el registro

  - Este comando establece la hora de limpieza del registro para el sitio de Redmond a las 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

Para más información, consulte el tema de ayuda del cmdlet [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration).

