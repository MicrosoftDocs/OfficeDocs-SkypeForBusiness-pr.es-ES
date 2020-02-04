---
title: 'Lync Server 2013: crear la configuración de la calidad de la experiencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f651da026dcf73253eaccada14332a7f2f5c1f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Crear la configuración de la calidad de la experiencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.

Al instalar Microsoft Lync Server 2013, se crea una única colección global de parámetros de configuración de QoE. Los administradores también tienen la posibilidad de crear opciones personalizadas en el ámbito del sitio. Cuando estas opciones de ámbito de sitio se usan, tienen prioridad frente a la configuración global. Así, por ejemplo, si crea opciones de ámbito de sitio para el sitio de Redmond, serán las opciones que se usen (y no la configuración global) para administrar la calidad de la experiencia en Redmond.

Las opciones de configuración de QoE se pueden crear con el panel de control de Lync Server o el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) . Si está usando el panel de control de Lync Server para crear una nueva configuración, las siguientes opciones estarán disponibles:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor de IU</th>
<th>Parámetro de PowerShell</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>Identidad</p></td>
<td><p>Identificador único de la opción que se va a crear. La opción de configuración de QoE solo se puede crear en el ámbito del sitio.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar supervisión de datos de calidad de la experiencia (QoE)</p></td>
<td><p>EnableQoE</p></td>
<td><p>Especifica si los registros QoE se recopilarán y guardarán en la base de datos de supervisión.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar purgado de datos de calidad de la experiencia (QoE)</p></td>
<td><p>EnablePurging</p></td>
<td><p>Especifica si los registros se van a purgar una vez transcurrida la duración definida en la propiedad <strong>Conservar datos de QoE durante el período de duración máximo (días)</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Conservar datos de calidad de la experiencia (QoE) durante un máximo de (días)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Cantidad de días en que los datos de QoE se almacenarán antes de que se purguen de la base de datos. Este valor se ignora si el purgado está deshabilitado.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> El cmdlet New-CsQoEConfiguration incluye opciones adicionales que no están disponibles en el panel de control de Lync Server. Para obtener más información, vea el tema <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">de ayuda nuevo-CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Para crear la configuración de la calidad de la aplicación con el panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.

4.  En la página **Datos de calidad de la experiencia**, haga clic en **Nuevo**.

5.  En **Seleccionar un sitio**, haga clic en el sitio al que va a aplicar la directiva y, luego, en **Aceptar**.

6.  En **Nueva configuración de calidad de la experiencia**, haga lo siguiente:
    
      - Seleccione **Habilitar supervisión de datos de calidad de la experiencia (QoE)** para activar la supervisión.
    
      - Seleccione **Habilitar purgado de datos de calidad de la experiencia (QoE)** para activar el purgado.
    
      - En **Conservar datos de calidad de la experiencia (QoE) durante un máximo de (días)**, seleccione la cantidad máxima de días durante la que se tienen que conservar los registros de QoE.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de parámetros de configuración de QoE con cmdlets de Windows PowerShell

Puede crear parámetros de configuración de QoE mediante Windows PowerShell y el cmdlet New-CsQoEConfiguration. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para crear una colección de opciones de configuración de QoE

  - Con este comando se crea una colección de opciones de configuración de QoE para usarla en el sitio de Redmond:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para crear una colección de opciones de configuración de QoE cuando la supervisión de QoE está deshabilitada

  - Dado que en el comando anterior no se ha especificado ningún parámetro (aparte del obligado Identity), la nueva colección de opciones de configuración usará los valores predeterminados en todas sus propiedades. Para crear opciones que usen otros valores de propiedad, bastará con incluir el parámetro y los valores que sean adecuados. Por ejemplo, use un comando como el siguiente para crear una colección de opciones de configuración de calidad de la experiencia que permita deshabilitar el registro de QoE de forma predeterminada:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar varios valores de propiedad al crear una colección de opciones de configuración de QoE

  - Si desea especificar varios valores de propiedad, es preciso incluir varios parámetros. Por ejemplo, con este comando se configuran nuevas opciones que permiten conservar los datos de QoE durante 30 días y purgar los datos antiguos a las 3:00 AM:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

