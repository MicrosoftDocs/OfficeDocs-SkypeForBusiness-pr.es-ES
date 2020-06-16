---
title: Introducción
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 354f28948578be528787928fd4e0874f6ff8e5fa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction"></a>Introducción

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

La herramienta stress and performance de Lync Server 2013 (denominada LyncPerfTool) puede simular la carga de usuarios de los siguientes tipos:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Mensajería instantánea (MI) y presencia</p></td>
<td><p>Audioconferencia</p></td>
</tr>
<tr class="even">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>Voz sobre IP (VoIP), incluida la simulación de red telefónica conmutada (RTC)</p></td>
</tr>
<tr class="odd">
<td><p>Conferencia de cliente de Web Access</p></td>
<td><p>Operador 2013 de Microsoft Lync</p></td>
</tr>
<tr class="even">
<td><p>Grupos de respuesta</p></td>
<td><p>Expansión de la lista de distribución</p></td>
</tr>
<tr class="odd">
<td><p>Consulta de la libreta de direcciones y de descarga de la libreta de direcciones</p></td>
<td><p>Llamadas mejoradas 9-1-1 (E9-1-1) y Perfil de ubicación (plan de marcado)</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>Ver varias secuencias desde una conferencia</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


La herramienta de esfuerzo y rendimiento de Lync Server 2013 admite la generación de carga entre grupos de servidores y la Federación solo a través de la configuración avanzada.

La herramienta tampoco simula la carga de usuarios para los siguientes clientes:

  - Office Live Meeting 2007

  - Chat persistente de Lync 2013

Como resultado, la herramienta stress and performance de Lync Server 2013 no permitirá probar los siguientes componentes:

  - Chat persistente de Lync 2013

  - Escenarios de integración de Exchange

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Aplicaciones y archivos incluidos con la herramienta de esfuerzo y rendimiento de Lync Server 2013

Las siguientes aplicaciones se incluyen en la herramienta de esfuerzo y rendimiento de Lync Server 2013:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Herramienta</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool.exe</p></td>
<td><p>La herramienta de aprovisionamiento de usuarios de Lync Server 2013. Esta herramienta se usa para crear usuarios y contactos.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator.exe</p></td>
<td><p>Herramienta de configuración de carga de Lync Server 2013. Esta herramienta se usa para configurar las características de la carga de usuarios que se van a simular.</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool.exe</p></td>
<td><p>La herramienta de esfuerzo y rendimiento de Lync Server 2013. LyncPerfTool es la herramienta que simula la carga de usuarios.</p></td>
</tr>
<tr class="even">
<td><p>Default. TMX</p></td>
<td><p>El valor predeterminado. TMX es necesario para usar la herramienta de registro de Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Scripts de aprovisionamiento de ejemplo</p></td>
<td><p>Estos ejemplos se usan para configurar la topología para ejecutar pruebas de carga, en función de escenarios específicos.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

