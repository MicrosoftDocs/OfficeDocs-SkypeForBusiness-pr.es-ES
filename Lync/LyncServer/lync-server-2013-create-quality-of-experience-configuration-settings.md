---
title: Creación de opciones de configuración para la calidad de la experiencia
TOCTitle: Creación de opciones de configuración para la calidad de la experiencia
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48275505
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación de opciones de configuración para la calidad de la experiencia

 

_**Última modificación del tema:** 2015-03-09_

Las métricas de calidad de la experiencia (QoE) controlan la calidad de las llamadas de audio y vídeo de la organización, lo que engloba aspectos como el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otros datos, como los registros de detalles de llamadas, lo que permite habilitar y deshabilitar QoE de manera independiente de otros datos registrados.

Al instalar Microsoft Lync Server 2013, se crea automáticamente una colección global y única de opciones de configuración de QoE. Los administradores también tienen la posibilidad de crear opciones personalizadas en el ámbito del sitio. Cuando estas opciones de ámbito de sitio se usan, tienen prioridad frente a la configuración global. Así, por ejemplo, si crea opciones de ámbito de sitio para el sitio de Redmond, serán las opciones que se usen (y no la configuración global) para administrar la calidad de la experiencia en Redmond.

Las opciones de configuración de la calidad de la experiencia se puede crear mediante el Panel de control de Lync Servero el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration). Si usa el Panel de control de Lync Server para crearlas, dispondrá de las siguientes opciones:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Opción de UI</th>
<th>Parámetro de PowerShell</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>Identity</p></td>
<td><p>Identificador único de la opción que se va a crear. La opción de configuración de QoE solo se puede crear en el ámbito del sitio.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar supervisión de datos de calidad de la experiencia (QoE)</p></td>
<td><p>EnableQoE</p></td>
<td><p>Especifica si los registros de QoE se van a recopilar y guardar en la base de datos de supervisión.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar purgado de datos de calidad de la experiencia (QoE)</p></td>
<td><p>EnablePurging</p></td>
<td><p>Especifica si los registros se van a purgar una vez transcurrida la duración definida en la propiedad <strong>Conservar datos de QoE durante el período de duración máximo (días)</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Conservar datos de calidad de la experiencia (QoE) durante un máximo de (días)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Número de días en que los datos de QoE se almacenarán antes de que se purguen de la base de datos. Este valor se ignora si el purgado está deshabilitado.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> El cmdlet New-CsQoEConfiguration incluye más opciones no disponibles en el Panel de control de Lync Server. Para obtener más información, consulte el tema de ayuda de <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A>.



## Para crear opciones de configuración de QoE con el Panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.

4.  En la página **Datos de calidad de la experiencia**, haga clic en **Nuevo**.

5.  En **Seleccionar un sitio**, haga clic en el sitio al que va a aplicar la directiva y, a continuación, en **Aceptar**.

6.  En **Nueva configuración de calidad de la experiencia**, haga lo siguiente:
    
      - Seleccione **Habilitar supervisión de datos de calidad de la experiencia (QoE)** para activar la supervisión.
    
      - Seleccione **Habilitar purgado de datos de calidad de la experiencia (QoE)** para activar el purgado.
    
      - En **Conservar datos de calidad de la experiencia (QoE) durante un máximo de (días)**, seleccione el número máximo de días durante el que se deben conservar los registros de QoE.

7.  Haga clic en **Confirmar**.

## Para crear opciones de configuración de QoE con cmdlets de Windows PowerShell

Las opciones de configuración de QoE también se pueden crear usando Windows PowerShell y el cmdlet New-CsQoEConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para crear una colección de opciones de configuración de QoE

  - Con este comando se crea una colección de opciones de configuración de QoE para usarla en el sitio de Redmond.
    
        New-CsQoEConfiguration -Identity "site:Redmond"

## Para crear una colección de opciones de configuración de QoE cuando la supervisión de QoE está deshabilitada

  - Dado que en el comando anterior no se ha especificado ningún parámetro (aparte del obligado Identity), la nueva colección de opciones de configuración usará los valores predeterminados en todas sus propiedades. Para crear opciones que usen otros valores de propiedad, bastará con incluir el parámetro y los valores que sean adecuados. Por ejemplo, use un comando como el siguiente para crear una colección de opciones de configuración de calidad de la experiencia que permita deshabilitar el registro de QoE de forma predeterminada:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## Para especificar varios valores de propiedad al crear una colección de opciones de configuración de QoE

  - Si desea especificar varios valores de propiedad, es preciso incluir varios parámetros. Por ejemplo, con este comando se configuran nuevas opciones que permiten conservar los datos de QoE durante 30 días y purgar los datos antiguos a las 3:00 AM:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration).

