---
title: Devolución de información de configuración del servidor perimetral de A/V
TOCTitle: Devolución de información de configuración del servidor perimetral de A/V
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49889537
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Devolución de información de configuración del servidor perimetral de A/V

 

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V permite que los usuarios internos (usuarios conectados a la red de la organización) compartan audio y vídeo con usuarios externos (usuarios no conectados a la red de la organización). El servicio perimetral A/V se administra principalmente con las opciones de configuración del servidor perimetral A/V, que se pueden definir en el ámbito de sitio o en el ámbito de servicio (es decir, se pueden definir para un servidor perimetral A/V individual).

Para devolver información sobre las opciones de configuración del servidor perimetral A/V que usa la organización, debe usar el Shell de administración de Lync Server y el cmdlet Get-CsAVEdgeConfiguration. Para más información, vea el tema de ayuda del cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAVEdgeConfiguration).

La información devuelta desde el cmdlet Get-CsAVEdgeConfiguration tendrá un aspecto similar a este:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

## Devolver información para todas las opciones de configuración del servidor perimetral A/V

  - El siguiente comando devuelve información sobre todas las opciones de configuración del servidor perimetral A/V que actualmente usa la organización:
    
        Get-CsAVEdgeConfiguration

## Devolver información para las opciones de configuración del servidor perimetral A/V en el ámbito de sitio

  - Para devolver información sobre una colección específica de opciones de configuración del servidor perimetral A/V, especifique la identidad de esa colección al ejecutar el cmdlet Get-CsAVEdgeConfiguration. Por ejemplo, este comando devuelve información solo para las opciones aplicadas al sitio Redmond:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

## Devolver información para las opciones de configuración del servidor perimetral A/V en el ámbito de servicio

  - Este comando devuelve información solo para las opciones aplicadas a un servidor perimetral A/V específico:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## Vea también

#### Tareas

[Creación o modificación de conjuntos de opciones de configuración del servidor perimetral A/V](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Eliminación de un conjunto existente de opciones de configuración del servidor perimetral A/V](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### Otros recursos

[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)

