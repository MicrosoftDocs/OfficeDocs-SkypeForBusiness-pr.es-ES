---
title: 'Lync Server 2013: crear opciones de configuración de la calidad de la experiencia'
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
ms.openlocfilehash: 5e2d81f62bb35710d14450aa26f3100ea53021ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Crear opciones de configuración de la calidad de la experiencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.

Al instalar Microsoft Lync Server 2013, se crea una única colección global de opciones de configuración de QoE. Los administradores pueden también crear una configuración personalizada en el ámbito de sitio. Cuando se usa esta configuración en el ámbito del sitio, predomina sobre la configuración global. Por ejemplo, si crea una configuración de ámbito de sitio para el sitio de Redmond, se utilizará esa configuración (en lugar de la configuración global) para administrar el QoE en Redmond.

Las opciones de configuración de QoE se pueden crear mediante el panel de control de Lync Server o el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) . Si está usando el panel de control de Lync Server para crear una nueva configuración, estarán disponibles las siguientes opciones:


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
<td><p>Name</p></td>
<td><p>Identidad</p></td>
<td><p>Identificador único de la configuración que se va a crear. Las opciones de configuración de QoE solo se pueden crear en el ámbito del sitio.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar la supervisión de los datos de QoE</p></td>
<td><p>EnableQoE</p></td>
<td><p>Especifica si los registros QoE se recopilarán y guardarán en la base de datos de supervisión.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar la depuración de datos de QoE</p></td>
<td><p>EnablePurging</p></td>
<td><p>Especifica si los registros se purgarán una vez transcurrida la duración definida en la propiedad <strong>conservar datos de QoE durante el período de duración máximo (días)</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Mantener los datos de QoE durante la duración máxima (días)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Número de días que se almacenarán los datos de QoE antes de que se purguen de la base de datos. Este valor se omite si la depuración está deshabilitada.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> El cmdlet New-CsQoEConfiguration incluye opciones adicionales que no están disponibles en el panel de control de Lync Server. Para obtener más información, vea el tema de ayuda <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Para crear opciones de configuración de QoE mediante el panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.

4.  En la página **datos de calidad de la experiencia** , haga clic en **nuevo**.

5.  En **seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la Directiva y, a continuación, haga clic en **Aceptar**.

6.  En **nueva configuración de calidad de la experiencia**, haga lo siguiente:
    
      - Seleccione **activar la supervisión de los datos de QoE** para activar la supervisión.
    
      - Seleccione **Habilitar la purga de los datos de QoE** para activar la depuración.
    
      - En **conservar QoE durante la duración máxima (días)**, seleccione el número máximo de días que se deben conservar los registros de QoE.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de opciones de configuración de QoE con los cmdlets de Windows PowerShell

Puede crear opciones de configuración de QoE con Windows PowerShell y el cmdlet New-CsQoEConfiguration. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para crear una nueva colección de opciones de configuración de QoE

  - Este comando crea una nueva colección de opciones de configuración de QoE que se aplican al sitio de Redmond:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para crear una nueva colección de opciones de configuración de QoE cuando la supervisión de QoE está deshabilitada

  - Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de opciones de configuración de calidad de la experiencia que, de forma predeterminada, permitir la grabación de QoE, use un comando como este:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar varios valores de propiedad al crear una nueva colección de opciones de configuración de QoE

  - Puede incluir varios parámetros para varios valores de propiedad. Por ejemplo, este comando configura la nueva configuración para conservar los datos de QoE durante 30 días y para depurar los datos antiguos a las 3:00 A.M.:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

